---
title: "Android Enterprise: Are your phones slowed down?"
date: 2022-09-30T11:08:24"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>Welcome to the new site! It was the reason I didn&#8217;t post anything, as I was busy building up the new site and migrating content to it. </p>



<p>With this post, I continue to look into the issues faced with fully managed Android Enterprise devices. Like any other enterprise, we also enroll and distribute these devices to our user base. However, since we started rolling out these devices, the feedback from the user community was not that good.</p>



<p>Users reported that they are not happy with the performance of their phones. M365 apps like Outlook, Teams, and PowerApps were opening very slowly. Initially, we assumed a particular phone model was slow, but even high-end phones reported similar behavior.</p>



<p>Troubleshooting was not easy as it required a deeper level of troubleshooting and parallelly learning to debug Android devices. It involved comparing performances for all possible enrollment scenarios, i.e., Fully Managed User Device; Corporate Owned &#8211; Dedicated Device; Corporate Owned &#8211; Work Profile; Personal Owned &#8211; Work Profile. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>Device Policy Controller</h4>



<p>In an Android enterprise deployment, an enterprise maintains control over various aspects of user devices, such as isolating work-related information from users&#8217; personal data, pre-configuring approved apps for the environment, or disabling device capabilities (for example, the camera). </p>



<p>The DPC creates and manages the <em>work profile</em> on the device on which it is installed. The work profile encrypts work-related information and keeps it separate from the user&#8217;s personal apps and data. Before creating the work profile, the DPC can also provision a managed Google Play Account for use on the device.</p>



<p>When a device is enrolled in an MDM, it uses the Device Policy Controller (DPC), which is automatically installed during enrollment. The DPC app can be accessed by navigating to Google Play and selecting and opening the Android Device Policy app. You can sync the device, view which apps were installed, and policy settings.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Collecting Logs</strong></h4>



<p style="font-size:15px"><strong>Enable developer options on the Android device:</strong></p>



<ol><li>Go to Settings -> <strong>About phone</strong>.</li><li>Tap the Build number button <strong>seven (7) times</strong> until it says, “You are now a developer!”</li><li>Return to the previous screen to find Developer Options at the bottom. The Developer Options screen might be located or named differently on some devices.</li><li>Open the <strong>Developer Options</strong> page and scroll down until you find USB Debugging and toggle it to <strong>Enabled</strong>.</li></ol>



<p>Once everything is in place, connect a USB cable from your PC to the device. If this is the first time the device has been connected, a popup will appear asking if it’s&nbsp;<strong>OK&nbsp;</strong>to allow debugging. Select&nbsp;<strong>Allow&nbsp;</strong>and select the box to&nbsp;<strong>Always allow</strong>. This will enable a connection between your computer and the connected Android device.</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot_20220930-092802_Settings.jpg?resize=231%2C512&#038;ssl=1" alt="" class="wp-image-424" width="231" height="512" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot_20220930-092802_Settings.jpg?resize=461%2C1024&amp;ssl=1 461w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot_20220930-092802_Settings.jpg?resize=135%2C300&amp;ssl=1 135w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot_20220930-092802_Settings.jpg?resize=768%2C1707&amp;ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot_20220930-092802_Settings.jpg?resize=691%2C1536&amp;ssl=1 691w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot_20220930-092802_Settings.jpg?resize=922%2C2048&amp;ssl=1 922w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot_20220930-092802_Settings.jpg?w=1080&amp;ssl=1 1080w" sizes="(max-width: 231px) 100vw, 231px" data-recalc-dims="1" /></figure>



<p>Open a command prompt and navigate to the directory where the SDK was installed and follow the below steps:</p>



<p>Type in <strong>adb.exe devices -l,</strong> and you should see your Android device listed:</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-093952-1.png?resize=512%2C196&#038;ssl=1" alt="" class="wp-image-427" width="512" height="196" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-093952-1.png?resize=1024%2C391&amp;ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-093952-1.png?resize=300%2C115&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-093952-1.png?resize=768%2C293&amp;ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-093952-1.png?w=1082&amp;ssl=1 1082w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure>



<p>If you don&#8217;t see the device or receive any error message, then run the following commands:</p>



<p><strong>adb kill-server</strong></p>



<p><strong>adb start-server</strong></p>



<p>and then try again with <strong>adb.exe devices -l</strong></p>



<p>You will need to collect logcat and dumpsys logs from the connected devices.</p>



<ol><li><strong>Logcat</strong></li></ol>



<p>Logcat is a command-line tool that dumps a log of system messages, including stack traces when the device throws an error and messages that you have written from your app with the&nbsp;<code>Log</code>&nbsp;class</p>



<p>From the command prompt, run the following command with replicating the slowness issue/behavior on the connected device : </p>



<p><strong>adb.exe logcat -v threadtime [device ID] &gt; C:\temp\fully_managed.log</strong></p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-095441.png?resize=512%2C153&#038;ssl=1" alt="" class="wp-image-426" width="512" height="153" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-095441.png?resize=1024%2C305&amp;ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-095441.png?resize=300%2C89&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-095441.png?resize=768%2C229&amp;ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Annotation-2022-09-30-095441.png?w=1102&amp;ssl=1 1102w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure>



<ol start="2"><li> <strong>Dumpsys</strong></li></ol>



<p>A few weeks back, I have written a post on the <a rel="noreferrer noopener" href="https://intuneirl.com/2022/08/android-enterprise-device-reboots-on-its-own/" target="_blank">Android reboot issue</a>, and it has step-by-step instructions for collecting dumpsys logs. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Reading the Device Logs</strong></h4>



<p>Android device logs are not that hard to read as they are in .txt format. The logs exported in the previous step will have information like app crashes, deadlocks, activities, memory &amp; CPU utilization, power consumption, etc.&nbsp;</p>



<p>However, I recommend that before you start reading the logs, you go through<a rel="noreferrer noopener" href="https://developer.android.com/studio/command-line" target="_blank"> Google Documents </a>for developers, as it will help you familiarize yourself with these queries and the logs.</p>



<p>Let&#8217;s get started and dig through the logs for some useful info.</p>



<p>The logcat I just exported from the device is around 40MB, and I am using Android Studio to open it. </p>



<p>This log file will have a lot of information with all the details of what is going on with the device. But for now, I am more interested in finding out what is causing the M365 apps to go unresponsive.</p>



<p>There are multiple ways to look for this info, either you go line-by-line through the log file &#8211; which will take days as it has thousands of lines with details of numerous processes &amp; services, or the smart way by looking directly for impacted processes.</p>



<p>You have to export the list of all apps installed on the device (hidden or not) run so that you have the data to look for:</p>



<p>In the command prompt, execute the below command:</p>



<p><strong>adb.exe pm list packages -s</strong> &gt;<strong>C:\temp\fully_managed_packages.log</strong></p>



<p>I found that Microsoft Apps are the top memory-intensive apps in this log file. Now with this info, I just need to filter out the logcat log for these packages.</p>



<h4>Connection Refused!</h4>



<p>The logs had consistent entries for connections getting dropped for M365 apps. Whenever the device-based sign-in was attempted, the query failed. </p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/fully_managed_powerapps_slowness.png?resize=750%2C443&#038;ssl=1" alt="" class="wp-image-429" width="750" height="443" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/fully_managed_powerapps_slowness.png?resize=1024%2C605&amp;ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/fully_managed_powerapps_slowness.png?resize=300%2C177&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/fully_managed_powerapps_slowness.png?resize=768%2C454&amp;ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/fully_managed_powerapps_slowness.png?w=1341&amp;ssl=1 1341w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<h4>Reason for the Refused Connections</h4>



<p>The ADAL may generate this error message whenever any application(M365 apps) cannot communicate with the broker application (Microsoft Authenticator or Company Portal). You might also see error messages like &#8220;<code>BROKER_AUTHENTICATOR_NOT_RESPONDING</code>&#8220;. This is well documented by Microsoft that it is due to the OEM limiting inter-app communication on their hardware.</p>



<p>The bound service is expected to perform an interactive and silent auth for ADAL in brokered scenarios. If this communication between ADAL and brokers fails, ADAL will return the &#8220;connection refused&#8221; back to the app. In silent authentication scenarios, this fails to get a token. This will result in an error in interactive authentication scenarios even before the user sees a prompt.</p>



<h4>Impacted Devices</h4>



<p>Several device manufacturers are impacted by this issue, including Samsung, Huawei, OnePlus, and Vivo. It&#8217;s generally built-in in the devices exposing battery settings but often is only exposed in a subset of the OEM&#8217;s device lineup.</p>



<h4>Remediation</h4>



<p>It depends on OEMs on how they allow the end users to limit the operating system&#8217;s ability to launch secondary apps. Each device may expose a different setting to do this. </p>



<p>In this case, it is related specifically to M365 apps such as Outlook, Power Apps &amp; OneDrive, and these apps require background activity, so the users need to configure the Battery Optimization settings on their devices:</p>



<p>1. Go to Settings on your Android device</p>



<p>2. Search for Apps and tap on them</p>



<p>3. Search for the app having an issue and Tap on that app</p>



<p>4. Now, search for Battery and top on it.</p>



<p>5. Turn the switch ON for “<strong>Allow background activity</strong>”</p>



<p>6. Tap “<strong>Optimise battery usage</strong>” and turn <strong>Switch OFF</strong> for the app having an issue.</p>



<p>7. In case you don’t find the app, from the top select All rather than “<strong>Apps not optimized</strong>”.</p>



<p>Also, the Adaptive battery settings under Device Care app &gt; More battery settings has to be disabled – in case there are apps that user use often and still don’t want to avoid disconnection issues.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>After making these changes, you will notice an improvement in the device performance, and if you go through the device logs, you will not find these errors anymore. However, as these settings allow the app to run in the background without battery optimization, users may receive a prompt on their devices to switch on the battery optimization. This prompt needs to be ignored!</p>



<p>That&#8217;s all for today..have a great weekend..cheers 🍻🥂</p>
<!--kg-card-end: html-->