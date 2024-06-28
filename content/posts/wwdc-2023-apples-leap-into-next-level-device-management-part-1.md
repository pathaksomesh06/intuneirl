---
title: "WWDC 2023: Apple's Leap into Next-Level Device Management - Part 1"
date: 2023-06-23T08:51:34"
draft: false
tags: []
---

<p>This year's Apple Worldwide Developers Conference (WWDC2023) was marked by numerous groundbreaking announcements. Yet, amid the buzz about the new Apple Vision Pro, iOS/iPad OS 17, macOS Sonoma, and app updates, Apple's leap into next-level device management is an understatement. A significant shift from traditional management paradigms, this advancement is set to redefine the way we interact with and manage our Apple devices.</p>
<p>I have divided this into three parts for simplicity and better understanding. In this first part, I have covered the major announcements with macOS &amp; iOS/iPadOS management.</p>
<hr>
<h3 id="apples-device-management-evolution">Apple's Device Management Evolution</h3>
<p>Apple has constantly improved its device management approach over the past years. The tech giant has constantly streamlined the user experience while granting more control over individual devices, from iCloud backups to Family Sharing. The adjustments made public at WWDC 2023, however, go beyond that; they take a comprehensive, user-centered strategy that seamlessly ties into Apple's ecosystem.</p>
<p>Here is a summary of the device management-related WWDC announcements made by Apple. In the next weeks and months, I'll be delving deeper into many of these subjects.</p>
<h2 id="awesome-new-device-management-features-in-macos-14">Awesome New Device Management Features in macOS 14</h2>
<p>Apple's new features aim to streamline user enrollment and setup while maintaining robust security measures. This year, Apple has refined the Automated Device Enrollment process. Beginning with FileVault, macOS Sonoma will now allow MDM to necessitate FileVault activation during the Setup Assistant phase. As an Intune admin, we will have the option to display the FileVault recovery key during Setup Assistant or alternatively escrow it to Intune.</p>
<p>Moreover, as an Intune admin, you will now be able to enforce the device to be on a specific operating system version in order to enroll. This will ensure that devices are using the required OS version before being operational. If a higher OS version is required, users will be guided through an automatic update process for their Mac, which will then restart automatically. After completion, the Mac returns to the Setup Assistant, and users can conclude the enrollment and setup process.</p>
<p>Apple has also implemented safeguards to confirm that the user completes the Automated Device Enrollment as soon as network connectivity is established. This allows you to postpone enrollment by 8 hours with a “not now” capability.</p>
<p>Coming to the most awaited feature - <em><u>Platform Single Sign-On (SSO), </u></em>Apple unveiled several exciting enhancements for macOS 14 to platform SSO, such as:</p>
<ul><li>The introduction of a fresh menu item within System Settings. This enables users to register their device or user account for utilization with SSO.</li></ul>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-18.png" class="kg-image" alt="" loading="lazy" width="1424" height="1252" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-18.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-18.png 1000w, __GHOST_URL__/content/images/2023/06/image-18.png 1424w" sizes="(min-width: 720px) 720px"></figure>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-19.png" class="kg-image" alt="" loading="lazy" width="1424" height="1252" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-19.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-19.png 1000w, __GHOST_URL__/content/images/2023/06/image-19.png 1424w" sizes="(min-width: 720px) 720px"></figure>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-20.png" class="kg-image" alt="" loading="lazy" width="1424" height="1252" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-20.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-20.png 1000w, __GHOST_URL__/content/images/2023/06/image-20.png 1424w" sizes="(min-width: 720px) 720px"></figure>
<ul><li>The capability for users, with accounts managed by an organizational identity provider or smart cards, to create local user accounts.</li><li>Refreshing group memberships at the moment of authentication with the identity provider.</li></ul>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-12.png" class="kg-image" alt="" loading="lazy" width="946" height="508" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-12.png 600w, __GHOST_URL__/content/images/2023/06/image-12.png 946w" sizes="(min-width: 720px) 720px"></figure>
<ul><li>The ability to fulfill authorization prompts using Identity Provider (IdP) user accounts that don't exist locally.</li></ul>
<p>Some other impressive features announced were:</p>
<ul><li>Password policies can now be delivered as regular expressions if needed and password change notification prompts occur at every logon.</li></ul>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-13.png" class="kg-image" alt="" loading="lazy" width="912" height="226" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-13.png 600w, __GHOST_URL__/content/images/2023/06/image-13.png 912w" sizes="(min-width: 720px) 720px"></figure>
<ul><li>System Settings management can now prevent several settings modifications at a granular level.</li></ul>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-21.png" class="kg-image" alt="" loading="lazy" width="1424" height="1256" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-21.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-21.png 1000w, __GHOST_URL__/content/images/2023/06/image-21.png 1424w" sizes="(min-width: 720px) 720px"></figure>
<ul><li>Managed Device Attestation is NOW on macOS</li></ul>
<p>Below is the snapshot of all the changes coming to macOS management.</p>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-15.png" class="kg-image" alt="" loading="lazy" width="989" height="552" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-15.png 600w, __GHOST_URL__/content/images/2023/06/image-15.png 989w" sizes="(min-width: 720px) 720px"></figure>
<hr>
<h2 id="the-latest-developments-in-iosipados-management">The Latest Developments in iOS/iPadOS Management</h2>
<p>For iOS &amp; iPadOS - "Return to Service" is one of the major announcements and it will definitely be a game changer. Let's understand more about this.</p>
<p>In the case of supervised device deployment scenarios, devices are frequently passed from one user to another. Although remote device wipe is possible, re-engagement of these devices has always necessitated a manual process, including physical interaction with the device and navigation through the Setup Assistant.</p>
<p>The introduction of a new feature called <em><u>Return to Service</u></em> for iOS and iPadOS, will eliminate this extra manual step. </p>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-16.png" class="kg-image" alt="" loading="lazy" width="959" height="541" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-16.png 600w, __GHOST_URL__/content/images/2023/06/image-16.png 959w" sizes="(min-width: 720px) 720px"><figcaption><span>Return to Service</span></figcaption></figure>
<p>Here's how it operates: From Intune, you send an Erase command to the device. The command includes additional information which allows the device to reset, securely erase all data, connect to Wi-Fi, enroll into MDM, and get back to the Home Screen, ready to be used.</p>
<pre><code class="language-plist">&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"&gt;
&lt;plist version="1.0"&gt;
&lt;dict&gt;
    &lt;key&gt;Command&lt;/key&gt;
    &lt;dict&gt;
        &lt;key&gt;DisallowProximitySetup&lt;/key&gt;
        &lt;false/&gt;
        &lt;key&gt;PreserveDataPlan&lt;/key&gt;
        &lt;true/&gt;
        &lt;key&gt;RequestType&lt;/key&gt;
        &lt;string&gt;EraseDevice&lt;/string&gt;
    &lt;/dict&gt;
    &lt;key&gt;CommandUUID&lt;/key&gt;
    &lt;string&gt;0001_EraseDevice&lt;/string&gt;
&lt;/dict&gt;
&lt;/plist&gt;</code></pre>
<p>To implement this behavior, an additional dictionary can be added to the EraseDevice command. This dictionary needs to include the profile of a Wi-Fi configuration to allow the device to connect, once erased.<br></p>
<pre><code class="language-json">EraseDeviceCommand.Command.ReturnToService
-&gt; Enabled - boolean
-&gt; MDMProfileData - data
-&gt; MDMProfileData - data
</code></pre>
<p>As an alternative, the device can also connect to the Internet by different means, like a tethered connection. Secondly, the dictionary should include a profile with the necessary enrollment information.</p>
<p>Other features are:</p>
<ul><li>Shared iPads will now support “AwaitUserConfiguration” key.</li><li>SkipLanguageAndLocaleSetupforNewUsers during the setup wizard</li><li>Configuring a quote for temp users on the Shared iPad</li></ul>
<p>Snapshot of upcoming changes to iOS &amp; iPadOS<br></p>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-17.png" class="kg-image" alt="" loading="lazy" width="963" height="514" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-17.png 600w, __GHOST_URL__/content/images/2023/06/image-17.png 963w" sizes="(min-width: 720px) 720px"></figure>
<hr>
<h2 id="to-be-continued">To be continued...</h2>
<p>It's indeed a challenge to postpone discussing other thrilling topics, like Apple Watch management, declarative device management, managed Apple IDs, and passkeys. However, the sheer volume of exhilarating content warrants this delay.</p>
<p>Till then happy learning. </p>