---
title: "What Causes an Android Device To Reboot On It's Own Suddenly?"
date: 2022-08-23T23:10:00"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>In my previous post &#8211;  <a href="https://intuneirl.com/2022/08/android-enterprise-device-reboots-on-its-own/" target="_blank" rel="noreferrer noopener">Android Enterprise Device Reboots On Its Own!</a>, we discussed the weird issue with Android devices rebooting randomly. However, there is more surprise; continue reading further to find the root cause for your devices going spooky!</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Initial Root Cause</strong></h4>



<p>As we discussed previously, a few applications were crashing, causing the device to reboot. On a detailed analysis of the logs, we found &#8220;<strong>mainline_update&#8221;</strong> as the reboot reason. This &#8220;<strong>mainline_update&#8221;</strong> is a request for a reboot due to an update of the Google main line, which is triggered by &#8220;<strong>vending(Play Store)&#8221;</strong> when there is a pkg to update. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20171632.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="804" height="474"/></figure>



<p>This fixed the problem initially for us, but again after a few weeks, the Samsung phones continued to restart on their own!&nbsp;</p>



<p><strong>Seriously???Again?</strong></p>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/jim-carrey-frustrated.gif?resize=374%2C281&#038;ssl=1" alt="" class="wp-image-368" width="374" height="281" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Let&#8217;s Dig It Out</strong></h4>



<p>Alright, something is forcing this reboot, and the only way to find it is to wait for the device to reboot and capture the logs. So wait for a phone to reboot&#8230;.⏱⏰⌚⏱</p>



<p>Luckily one of the Samsung phones rebooted while I was trying out something on it.&nbsp;<strong>And the time starts now!</strong>&nbsp;⌛⏳&nbsp;</p>



<p>You have only 15 minutes to capture the dumpstate logs after a device has restarted. Below are the steps to collect the logs:</p>



<p>&nbsp;<strong>dumpstate Logs:</strong></p>



<p>1. In the Phone Application, enter *#9900#</p>



<p>2. Set the Debug Level to Mid.</p>



<p>3. Wait for the device to restart.</p>



<p>4. Open the app you want to debug and reproduce your issue.</p>



<p>5. After reproducing your issue, enter *#9900# again in the Phone Application</p>



<p>6. Select Run dumpstate/logcat</p>



<p>7. Select Copy to sd card Navigate to the log directory created on the device using&nbsp;the My Files app or a Windows PC with a USB cable connection.</p>



<p>8.&nbsp;<strong>After you have finished, follow steps 1-3 again, delete dumpstate/logcat and return the Debug Level to low.</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-11%20153430-0004.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280/:/rs=w:1280" alt="" width="179" height="317"/></figure>



<p><strong>ADB Logs:</strong></p>



<p><strong>Step 1: Enable developer options on the Android device:</strong></p>



<p>1. Go to Settings -&gt;&nbsp;<strong>About phone</strong>.</p>



<p>2. Tap the Build number button&nbsp;<strong>seven (7) times</strong>.</p>



<p>3. Return to the previous screen to find Developer Options at the bottom. The Developer Options screen might be located or named differently on some devices.</p>



<p>4. Open the&nbsp;<strong>Developer Options</strong>&nbsp;page and scroll until you find USB Debugging and toggle it E<strong>nabled</strong>.</p>



<p>5. Once complete, connect a USB cable from your PC to the device. If this is the first time the device has been connected, a popup will appear asking if it’s&nbsp;<strong>OK</strong>&nbsp;to allow debugging. Select&nbsp;<strong>Allow</strong>&nbsp;and select the box to&nbsp;<strong>Always allow</strong>.</p>



<p>6. This will enable a connection between your computer and the connected Android device.</p>



<p><strong>Step 2: Collect the ADB log through a windows machine:</strong></p>



<p>1. Navigate to&nbsp;<a href="https://developer.android.com/studio/releases/platform-tools#downloads" rel="noreferrer noopener" target="_blank"><u>https://developer.android.com/studio/releases/platform-tools#downloads</u></a>.</p>



<p>2. Select Download SDK platform -&gt;&nbsp;<strong>Tools for Windows</strong>.</p>



<p>3.&nbsp;<strong>Unzip</strong>&nbsp;the downloaded package.</p>



<p>4. Open a&nbsp;<strong>Command Prompt as administrator</strong>&nbsp;(Run as administrator).</p>



<p>5. Type cd &#8220;&lt;location of unzipped package&gt;.&#8221; It should look something like this:</p>



<p><strong>&nbsp;&nbsp;&nbsp;&nbsp;cd &#8220;C:\Firefox\Other\platform-tools_r30.0.5-windows\platform-tools&#8221;</strong></p>



<p>6. Run the following command in the ADB console to enable verbose logging (single line):</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup><em>&nbsp;adb logcat -G 32M; adb shell setprop persist.log.tag.dpcsupport VERBOSE; adb shell<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;setprop persist.log.tag.clouddpc VERBOSE; adb shell setprop persist.log.tag.Finsky<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VERBOSE; adb shell setprop persist.log.tag.Auth VERBOSE; adb shell setprop<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;persist.log.tag.Volley VERBOSE; adb shell setprop persist.log.tag.PackageManager<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VERBOSE;</em></sup></p>



<p>7. adb devices &lt;&#8212;-&nbsp;<strong>Copy the device ID</strong>.</p>



<p>8. Run adb -s &#8220;&lt;paste device id&gt;” bugreport &nbsp;&lt;path for copying the bug report on your PC&gt;. It should look something like this:</p>



<p><strong>&nbsp;&nbsp;adb -s abc123xyz bugreport E:\bugreport</strong></p>



<ul><li>The first step in the troubleshooting was to check for the reason for the device reboot. This time the dumpstate logs had some interesting error messages, but none of them was clear enough to state the reason for the reboot:</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/1-0002.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="665" height="551"/></figure>



<p>2. We know that some application or service is crashing and eventually rebooting the&nbsp;phone. So we have to find that service that crashes with the error code&nbsp;&#8220;<strong>debug0x494d</strong>&#8221; or &#8220;<strong>enterprise</strong>&#8220;.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-18%20180915.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="323"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-18%20180731.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="307"/></figure>



<p>3. We now know the error code, boot reason, and the entire sequence of steps when the&nbsp;service crashes. But what is causing is still not known. When looking for the debug logs, I&nbsp;&nbsp;was able to find that the user toggled the&nbsp;<strong>flight mode</strong>, and then it started crashing:</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/2_debug.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="456"/></figure>



<p>4. I thought, &#8220;Seriously???&#8221; can Wi-Fi cause the device to reboot?&nbsp;</p>



<p>But when I checked another device&#8217;s log, it was the same. So it was evident that it is random behavior that when the device(s) tries to change the Wi-Fi connection, it goes through a&nbsp;<strong>SOFT REBOOT.</strong></p>



<p>When I researched further into this, I found out that it has been a problem with Android 12 since starting, and a few patches were released as OTA, but it didn&#8217;t help.&nbsp;</p>



<p>What confirms this more is the recent release notes of Android 13, which confirm that this was a problem and has been fixed in the new release.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20133725.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="509" height="163"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>Please try to find the logs in your Android devices, and please let me know if you also find the same.&nbsp;</p>
<!--kg-card-end: html-->