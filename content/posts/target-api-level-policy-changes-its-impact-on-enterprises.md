---
title: "Target API Level Policy Changes & Its Impact on Enterprises"
date: 2022-12-17T02:13:53"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>With the service release 2211 of Intune, password complexity settings for Android Enterprise 12+ devices have been changed. This brings a major change in <strong>Password complexity</strong>&nbsp;settings for Android Enterprise.</p>



<p>The reason for the new password complexity settings is the latest Android OS &#8211; Android 13 &amp; API levels! With the release of the new OS, Google has mandated that all apps published to the Play Store must &#8220;<strong>target</strong>&#8221; or be &#8220;<strong>optimized</strong>&#8221; to work with the previous year&#8217;s API version. Google Play has updated its requirements for Android&#8217;s Target API Levels to increase app security.</p>



<p>In particular, an app must declare an &#8220;<strong>API level</strong>&#8221; released within two years of the most recent major version of Android if it is to be installed by users on the most current version of the Android OS.</p>



<p>Alright, but how this is related to password complexity and how it could impact you as an organization?</p>



<p>It&#8217;s a bit complicated and with this post I will try to explain the reasoning behind it and how it affects your organization.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Android versions &amp; Target API levels</h2>



<p>Whenever a new Android version is released, a unique &#8220;name&#8221; and a unique integer identifier, called &#8220;<em>API level</em>&#8221; is given to it. For eg:</p>



<ul>
<li>The Android version, such as&nbsp;<strong>Android 12.0</strong></li>



<li>A code (or dessert) name, such as&nbsp;<em>Snow Cone</em></li>



<li>A corresponding API level, such as&nbsp;<strong>API level </strong>31</li>
</ul>



<p>An Android code name may correspond to multiple versions and API levels but each Android version corresponds to exactly one API level.</p>



<p>Each Android device runs at exactly&nbsp;<em>one</em>&nbsp;API level – this API level is guaranteed to be unique per Android platform version. The API level precisely identifies the version of the API set that your app can call into; it identifies the combination of manifest elements, permissions, etc. Android&#8217;s system of API levels helps Android determine whether an application is compatible with an Android system image prior to installing the application on a device.</p>



<p>When an application is built, it contains the following API level information:</p>



<ul>
<li>The&nbsp;<em>target</em>&nbsp;API level of Android that the app is built to run on.</li>



<li>The&nbsp;<em>minimum</em>&nbsp;Android API level that an Android device must have to run your app.</li>
</ul>



<p>These settings are used to ensure that the functionality needed to run the app correctly is available on the Android device at installation time. If not, the app is blocked from running on that device. For example, if the API level of an Android device is lower than the minimum API level that you specify for your app, the Android device will prevent the user from installing your app.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-13.png?resize=750%2C376&#038;ssl=1" alt="" class="wp-image-954" width="750" height="376" srcset="https://irlimages.blob.core.windows.net/2022-12/image-13.png?resize=1024%2C513&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-13.png?resize=300%2C150&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-13.png?resize=768%2C384&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-13.png?resize=1536%2C769&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-12/image-13.png?w=1600&amp;ssl=1 1600w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p>The framework API is updated to give new or alternative capabilities with each new iteration of Android. With a few rare exceptions, older Android versions&#8217; API functionality is preserved unchanged in later Android versions. As a result, if your app works on one version of the Android API, it should work without any changes on a later version. </p>



<p>If you also want your app to work on older Android versions then some APIs may be unavailable to your app at runtime and your app may still work on older devices, albeit with limited functionality.</p>



<p><em><strong>Because the Intune company portal is also available on Google Play, Microsoft must also adhere to the new target API level in order to keep the app compliant with Google&#8217;s new privacy policies.</strong></em></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>What does that imply?</h2>



<p>From January 31, 2023, if an application targets API level 29 or lower, it will no longer be discoverable or installable through Google Play for new users with devices running Android 11 or higher, and thus distributing an application with a lower targetSDK will simply never appear on new devices. What this actually means for enterprise &amp; public store applications?</p>



<ul>
<li>Existing devices remain unaffected.</li>



<li>New devices enrolled running Android 10 or lower will receive the application without issue.</li>



<li>New devices enrolled running Android 11 or later will&nbsp;<em>not</em>&nbsp;receive the application and will not see it within managed Google Play either.</li>
</ul>



<p>The earlier deadline was November 2022 but now Google has extend till Jan&#8217;2023 with an extension request also available.</p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="143" src="https://irlimages.blob.core.windows.net/2022-12/image-12.png?resize=750%2C143&#038;ssl=1" alt="" class="wp-image-953" srcset="https://irlimages.blob.core.windows.net/2022-12/image-12.png?w=877&amp;ssl=1 877w, https://irlimages.blob.core.windows.net/2022-12/image-12.png?resize=300%2C57&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-12.png?resize=768%2C146&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2><strong>How this will affect your organization:</strong></h2>



<p>In the API level 31, there are series of changes and updates which impact enterprise apps and devices (work-profile). Few of them are listed below:</p>



<ul>
<li>The password complexity feature sets device-wide password requirements in predefined complexity buckets (<strong>High, Medium, Low, and None</strong>). If required, strict password requirements can instead be placed on the work profile security challenge.</li>
</ul>



<ul>
<li>Onboarding for the work profile security challenge has been eased. Now that setup considers whether the device passcode satisfies admin requirements, it is simple for the user to decide whether to strengthen their device passcode or utilize the security challenges associated with their work profile.</li>
</ul>



<ul>
<li>A factory reset won&#8217;t affect an enrollment-specific ID, which offers a distinct ID that identifies the work profile enrollment in a specific organisation. In Android 12, access to the device&#8217;s&nbsp;hardware identifiers (IMEI, MEID, serial number) is disabled for personal devices with a work profile.</li>
</ul>



<ul>
<li>Company-owned devices, with and without work profiles, can adopt the features listed in the preceding list items, but are not required to adopt them in Android 12.</li>
</ul>



<ul>
<li><code>setPasswordQuality()</code>&nbsp;and&nbsp;<code>getPasswordQuality()</code>&nbsp;are deprecated for setting device-wide passcode on work profile devices that are personal devices rather than company-owned</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2><strong>What to do to comply for your enterprise apps?</strong></h2>



<p>The requirements are quite simple and straightforward:</p>



<ul>
<li>When you publish a new app, make sure to target API 31 or above.</li>



<li>If your existing app’s target API level is 30 or above, then your app is compliant with this policy.</li>



<li>Suppose your existing app’s target is below API 30. In that case, it will stop being discoverable to all Google Play users whose devices run Android OS versions newer than your apps’ target API levels, as your app wasn’t built to meet the safety and quality standards that these users expect from newer Android OS versions.</li>



<li>If you plan to update this app to target API level 31 or above, you can submit an extension request to continue getting distributed to all users on Google Play until May 1, 2023. Impacted apps will receive an extension request form link in their Play Console Inbox message.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2><strong>What you need to do to prepare for Android Enterprise devices:</strong></h2>



<p>There is no impact for existing devices where&nbsp;<strong>Required password type</strong>&nbsp;or&nbsp;<strong>Minimum password length</strong>&nbsp;settings are configured.</p>



<p>If you are using these settings and do not configure the new&nbsp;<strong>Password complexity</strong>&nbsp;setting, devices running Android 12 or higher will default to&nbsp;<strong>Password complexity</strong>&nbsp;<em>High</em>&nbsp;in the following scenarios:</p>



<ul>
<li>When a new Android 12 or higher device is enrolled and is targeted with the existing policy.</li>



<li>When a device updates to Android 12 or higher and the existing policy is edited.</li>



<li>When a new work profile password policy is assigned to Android 12 or higher.</li>
</ul>



<p>Users will receive a prompt to update their password if they do not meet the password requirements.</p>



<p>However, it is recommended that you update the policies in Intune for <strong>Required password type</strong>&nbsp;and&nbsp;<strong>Minimum password length</strong>&nbsp;configurations with the&nbsp;<strong>Password complexity</strong>&nbsp;setting for devices running Android 12 or higher.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Conclusion</h2>



<p>I believe I was able to explain to you why these password policy changes are being enforced and how you can prepare yourself to accommodate them in your Intune tenant.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p class="has-small-font-size">References:</p>



<p class="has-small-font-size"><a href="https://aka.ms/Intune/Android13/?WT.mc_id=EM-MVP-5004955">https://aka.ms/Intune/Android13/?WT.mc_id=EM-MVP-5004955</a></p>



<p class="has-small-font-size"><a href="https://support.google.com/googleplay/android-developer/answer/11926878#exceptions">Target API level requirements for Google Play apps &#8211; Play Console Help</a></p>



<p class="has-small-font-size"><a href="https://learn.microsoft.com/en-us/xamarin/android/app-fundamentals/android-api-levels?tabs=windows/?WT.mc_id=EM-MVP-5004955">https://learn.microsoft.com/en-us/xamarin/android/app-fundamentals/android-api-levels?tabs=windows/?WT.mc_id=EM-MVP-5004955</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!--kg-card-end: html-->