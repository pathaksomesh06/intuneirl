---
title: "Android Enterprise Device Reboots On Its Own!"
date: 2022-08-29T20:19:00"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>In the last few days, many people have complained about the strange behavior of their Android Enterprise Devices, wherein the user&#8217;s devices suddenly reboot on their own. I also faced the same issue with one of my customers, and it was hard to find what made the devices go crazy. Continue reading this blog post to find the reason for the sudden restarts with the steps to fix them.&nbsp;</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Skarmbild-2022-08-11-171955.png?resize=311%2C242&#038;ssl=1" alt="" class="wp-image-381" width="311" height="242" srcset="https://irlimages.blob.core.windows.net/2022-10/Skarmbild-2022-08-11-171955.png?w=622&amp;ssl=1 622w, https://irlimages.blob.core.windows.net/2022-10/Skarmbild-2022-08-11-171955.png?resize=300%2C233&amp;ssl=1 300w" sizes="(max-width: 311px) 100vw, 311px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>As these devices are being managed through Intune, so first thought was to check for the maintenance window in Intune for the impacted profiles.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20135828-0001.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="627" height="400"/></figure>



<p>This looks good as it is expected that the device can reboot between 00:00 &amp; 05:00, but the problem was that devices were unexpectedly rebooting outside this window. The problem started with only a couple of users, and eventually, every user reported the sudden restarts, and we were clueless.&nbsp;</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Get device logs</strong></h4>



<p>When you are experiencing anything strange with your devices, the first thing you should do is export the logs.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20152256.png/:/rs=w:1280" alt="" width="671" height="136"/></figure>



<p><strong>dumpstate Logs:</strong></p>



<p>1. In the Phone Application, enter *#9900#</p>



<p>2. Set the Debug Level to Mid.</p>



<p>3. Wait for the device to restart.</p>



<p>4. Open the app you want to debug and reproduce your issue.</p>



<p>5. After reproducing your issue, enter *#9900# again in the Phone Application</p>



<p>6. Select Run dumpstate/logcat</p>



<p>7. Select Copy to sd card Navigate to the log directory created on the device using&nbsp;the My Files app or a Windows PC with a USB cable connection.</p>



<p>8.&nbsp;<strong>After you have finished, follow steps 1-3 again, delete dumpstate/logcat and return the Debug Level to low.</strong></p>



<figure class="wp-block-image"><img decoding="async" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20153430-0004.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt=""/></figure>



<p><strong>ADB Logs:</strong></p>



<p><strong>Step 1: Enable developer options on the Android device:</strong></p>



<ol><li>Go to Settings -&gt;&nbsp;<strong>About phone</strong>.</li><li>Tap the Build number button&nbsp;<strong>seven (7) times</strong>.</li><li>Return to the previous screen to find Developer Options at the bottom. The Developer Options screen might be located or named differently on some devices.</li><li>Open the&nbsp;<strong>Developer Options</strong>&nbsp;page and scroll down until you find USB Debugging and toggle it to&nbsp;<strong>Enabled</strong>.</li><li>Once complete, connect a USB cable from your PC to the device. If this is the first time the device has been connected, a popup will appear asking if it’s&nbsp;<strong>OK&nbsp;</strong>to allow debugging. Select&nbsp;<strong>Allow&nbsp;</strong>and select the box to&nbsp;<strong>Always allow</strong>.</li><li>This will enable a connection between your computer and the connected Android device.</li></ol>



<p><strong>Step 2: Collect the ADB log through a windows machine:</strong></p>



<ol><li>Navigate to&nbsp;<a rel="noreferrer noopener" href="https://developer.android.com/studio/releases/platform-tools#downloads" target="_blank">https://developer.android.com/studio/releases/platform-tools#downloads</a>.</li><li>Select Download SDK platform -&gt;&nbsp;<strong>Tools for Windows</strong>.</li><li><strong>Unzip&nbsp;</strong>the downloaded package.</li><li>Open a&nbsp;<strong>Command Prompt as administrator</strong>&nbsp;(Run as administrator).</li><li>Type cd &#8220;&lt;location of unzipped package&gt;.&#8221; It should look something like this:</li></ol>



<p><code>&nbsp;&nbsp;&nbsp;&nbsp;<strong>&nbsp;&nbsp;&nbsp;&nbsp;cd "C:\Firefox\Other\platform-tools_r30.0.5-windows\platform-tools"</strong></code></p>



<p>    6. Run the following command in the ADB console to enable verbose logging (single line):</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;adb logcat -G 32M; adb shell setprop persist.log.tag.dpcsupport VERBOSE; adb shell<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;setprop persist.log.tag.clouddpc VERBOSE; adb shell setprop persist.log.tag.Finsky<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VERBOSE; adb shell setprop persist.log.tag.Auth VERBOSE; adb shell setprop<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;persist.log.tag.Volley VERBOSE; adb shell setprop persist.log.tag.PackageManager<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VERBOSE;</p>



<p>   7. adb devices &lt;&#8212;-&nbsp;<strong>Copy the device ID</strong>.</p>



<p>    8. Run adb -s &#8220;&lt;paste device id&gt;” bugreport &nbsp;&lt;path for copying the bug report on your PC</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<strong>&nbsp;&nbsp;adb -s abc123xyz bugreport E:\bugreport</strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Read Device Logs</strong></h4>



<p>Android bug reports are not that hard to read as they are in .txt format. The logs exported in the previous step will have information like app crashes, deadlocks, activities, memory &amp; CPU utilization, power consumption, etc.&nbsp;</p>



<p>For now, we will only focus on&nbsp;<strong>ANR (Application Not Responding) &amp; Deadlocks and Power,</strong>&nbsp;as this will give us the details of the apps that are crashing and causing unexpected system reboots.&nbsp;</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Root Cause:</strong></h4>



<p>From these logs, you will identify that &#8220;<strong>vending(Play Store)&#8221;</strong>&nbsp;is causing most of the reboots. On a detailed analysis of the logs, you will also see &#8220;<strong>mainline_update&#8221;</strong>&nbsp;as a reboot cause. This &#8220;<strong>mainline_update&#8221;&nbsp;</strong>is a request for a reboot due to an update of the Google main line, which is triggered by &#8220;<strong>vending(Play Store)&#8221;&nbsp;</strong>when there is a pkg to update.</p>



<p>There were&nbsp;<strong>EIGHT (8) mainline APKs</strong>&nbsp;for which update failed, then rollback occurred, and this caused a reboot.&nbsp;<em><strong>That&#8217;s why reboot occurs</strong></em>.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20171632.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="804" height="474"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Solution:</strong></h4>



<p>The best way to get this fixed is to add the identified problematic mainline APKs in Intune by creating these applications in Intune and deploying them to affected devices.&nbsp;<strong>It could be that, in your case, different APKs are causing this.&nbsp;</strong></p>



<p>&nbsp;<strong>[ mainline APKs identified in the ANR logs]</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20172955.png/:/rs=w:1280" alt="" width="395" height="165"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>Enable a System App in Intune</h4>



<p>Let&#8217;s add these APKs as system apps and deploy them to the group of affected devices:</p>



<p>1. Sign in to the&nbsp;<a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank">Microsoft Endpoint Manager admin center</a>.</p>



<p>2. Select&nbsp;<strong>Apps</strong>&nbsp;&gt;&nbsp;<strong>All apps</strong>&nbsp;&gt;&nbsp;<strong>Add</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20173657.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="151"/></figure>



<p>3. In the&nbsp;<strong>Select app type</strong>&nbsp;pane, select Android Enterprise System App from the available options, and click&nbsp;<strong>Select</strong>.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20173856.png/:/rs=w:1280" alt="" width="640" height="373"/></figure>



<p>4. On the&nbsp;<strong>App information</strong>&nbsp;page, add the app details:</p>



<ul><li><strong>App Name</strong>: Enter the name of the app.</li><li><strong>Publisher</strong>: Enter the name of the publisher of the app.</li><li><strong>Package Name</strong>: Enter a package name. Intune will validate that the package name is valid.</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20174209.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="583" height="332"/></figure>



<p>5. Assign the app to the required group.</p>



<p>6. Repeat the same steps for adding the mainline APKs.</p>



<p><strong>This will not install any app but will whitelist the mentioned APKs, and the devices should no longer reboot on their own. Once you have verified that this is working, you can create a dynamic group of all Android Enterprise Devices and assign these apps to that group).&nbsp;</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/everything-is-fixed-now.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="360"/></figure>
<!--kg-card-end: html-->