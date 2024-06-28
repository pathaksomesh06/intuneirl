---
title: "Configure Network Protection for Defender for Endpoint for Android and iOS Devices"
date: 2022-11-17T02:37:58"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>As part of its Defender for Endpoint (MDE) enterprise endpoint security platform, Microsoft recently announced that the Mobile Network Protection functionality is generally available to assist organizations in identifying network vulnerabilities affecting Android and iOS devices.  </p>



<p>As soon as the device is onboarded to MDE and network protection is enabled, MDE will provide protection and alerts for all network-related suspicious events and activities. Let&#8217;s configure these features and see how the network protection works.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Network Safety</h2>



<p>The way companies operate has seen a significant transformation in recent years as a result of people working from home or using a hybrid work style. Users are now more dependent on network connections for personal and professional obligations, which expose users &amp; their devices to new security dangers—as such, protecting the data becomes the utmost priority for organizations.</p>



<p>With the addition of network safety capabilities to MDE for mobile devices, you can now protect your enrolled and unenrolled devices from all network attacks. These features include:</p>



<ul>
<li>MITM</li>
</ul>



<ul>
<li>Fake SSL Certificate</li>
</ul>



<ul>
<li>SSL Strip</li>
</ul>



<ul>
<li>Rogue Access Point</li>
</ul>



<ul>
<li>Unsecured Wi-Fi</li>
</ul>



<ul>
<li>Captive Portal</li>
</ul>



<ul>
<li>Malicious certificates</li>



<li>Remediation options to change networks when a network is determined as suspicious</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Configure MDE Network Protection Features for iOS Supervised Devices</h2>



<p>Network protection in Microsoft Defender for Endpoint is disabled by default. You must follow these steps to configure Network protection in iOS devices. (Authenticator device registration is required for MAM configuration) in iOS devices. <strong>Network Protection initialization will require the end user to open the app once.</strong></p>



<ul>
<li>Login to <a href="https://intune.microsoft.com" target="_blank" rel="noopener" title="">Intune </a>portal. </li>
</ul>



<ul>
<li>Navigate to Apps > App configuration policies. </li>
</ul>



<ul>
<li>Click Add and select &#8220;<strong>Managed Apps</strong>&#8221; to create a new App configuration policy</li>
</ul>


<div class="wp-block-image is-style-default">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-53.png?resize=750%2C326&#038;ssl=1" alt="Img: Create policy for managed apps" class="wp-image-868" width="750" height="326" srcset="https://irlimages.blob.core.windows.net/2022-11/image-53.png?resize=1024%2C445&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-53.png?resize=300%2C130&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-53.png?resize=768%2C334&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-53.png?w=1446&amp;ssl=1 1446w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Create a policy for managed app</em></figcaption></figure></div>


<ul>
<li>Provide a name and description to identify the policy uniquely</li>
</ul>



<ul>
<li>Then click on &#8216;Select Public apps&#8217; and choose &#8216;Microsoft Defender&#8217; for Platform iOS/IPadOS</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-54.png?resize=625%2C518&#038;ssl=1" alt="." class="wp-image-869" width="625" height="518" srcset="https://irlimages.blob.core.windows.net/2022-11/image-54.png?w=833&amp;ssl=1 833w, https://irlimages.blob.core.windows.net/2022-11/image-54.png?resize=300%2C248&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-54.png?resize=768%2C636&amp;ssl=1 768w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Select Defender as a public app</em></figcaption></figure></div>


<ul>
<li>In the Settings page, add the following keys:</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-55.png?resize=622%2C517&#038;ssl=1" alt="" class="wp-image-870" width="622" height="517" srcset="https://irlimages.blob.core.windows.net/2022-11/image-55.png?w=829&amp;ssl=1 829w, https://irlimages.blob.core.windows.net/2022-11/image-55.png?resize=300%2C249&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-55.png?resize=768%2C638&amp;ssl=1 768w" sizes="(max-width: 622px) 100vw, 622px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Configuration keys for network protection</em></figcaption></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-57.png?resize=708%2C254&#038;ssl=1" alt="" class="wp-image-872" width="708" height="254" srcset="https://irlimages.blob.core.windows.net/2022-11/image-57.png?w=944&amp;ssl=1 944w, https://irlimages.blob.core.windows.net/2022-11/image-57.png?resize=300%2C107&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-57.png?resize=768%2C275&amp;ssl=1 768w" sizes="(max-width: 708px) 100vw, 708px" data-recalc-dims="1" /><figcaption class="wp-element-caption">Configuration policy</figcaption></figure></div>


<ul>
<li>Assign the policy to the required group.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Configure MDE Network Protection Features for Android Enterprise Device</h2>



<ul>
<li>Login to <a href="https://intune.microsoft.com" target="_blank" rel="noopener" title="">Intune </a>portal. </li>
</ul>



<ul>
<li>Navigate to Apps &gt; App configuration policies. </li>
</ul>



<ul>
<li>Click Add and select &#8220;<strong>Managed Device</strong>&#8221; to create a new App configuration policy</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-58.png?resize=750%2C202&#038;ssl=1" alt="" class="wp-image-873" width="750" height="202" srcset="https://irlimages.blob.core.windows.net/2022-11/image-58.png?resize=1024%2C276&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-58.png?resize=300%2C81&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-58.png?resize=768%2C207&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-58.png?w=1535&amp;ssl=1 1535w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Create a policy for managed devices</em></figcaption></figure></div>


<ul>
<li>Provide a name and description to identify the policy uniquely</li>
</ul>



<ul>
<li>Then click on the platform and select &#8216;Android Enterprise&#8217;; profile type as &#8220;All&#8221; and choose &#8216;Microsoft Defender&#8217; as the target app.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-59.png?resize=750%2C343&#038;ssl=1" alt="" class="wp-image-874" width="750" height="343" srcset="https://irlimages.blob.core.windows.net/2022-11/image-59.png?resize=1024%2C468&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-59.png?resize=300%2C137&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-59.png?resize=768%2C351&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-59.png?resize=1536%2C702&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/image-59.png?w=1566&amp;ssl=1 1566w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Configure device platform</em></figcaption></figure></div>


<ul>
<li>In the settings page, select <strong>&#8216;Use configuration designer&#8217;</strong> and add <strong>&#8216;Enable Network Protection in Microsoft Defender&#8217;</strong> as the key and value as <strong>&#8216;1&#8217;</strong> to enable Network Protection. (Network protection is disabled by default).</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-60.png?resize=623%2C682&#038;ssl=1" alt="" class="wp-image-875" width="623" height="682" srcset="https://irlimages.blob.core.windows.net/2022-11/image-60.png?w=831&amp;ssl=1 831w, https://irlimages.blob.core.windows.net/2022-11/image-60.png?resize=274%2C300&amp;ssl=1 274w, https://irlimages.blob.core.windows.net/2022-11/image-60.png?resize=768%2C840&amp;ssl=1 768w" sizes="(max-width: 623px) 100vw, 623px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Configuration keys for network protection</em></figcaption></figure></div>


<blockquote class="wp-block-quote">
<p>If you push your enterprise CA certificate to your devices then make sure that you use <strong>&#8216;Trusted CA certificate list for Network Protection&#8217;</strong> as the key and in value add the <strong>&#8216;comma separated list of certificate thumbprints (SHA 1)&#8217;</strong> to <em>establish trust for the root CA</em>(s).</p>
</blockquote>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-61.png?resize=745%2C355&#038;ssl=1" alt="" class="wp-image-876" width="745" height="355" srcset="https://irlimages.blob.core.windows.net/2022-11/image-61.png?w=993&amp;ssl=1 993w, https://irlimages.blob.core.windows.net/2022-11/image-61.png?resize=300%2C143&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-61.png?resize=768%2C366&amp;ssl=1 768w" sizes="(max-width: 745px) 100vw, 745px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Configuration profile</em></figcaption></figure></div>


<ul>
<li>Assign the policy to the required group.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>MDE App Permissions On The Device</h2>



<h3>iOS</h3>



<ul>
<li>After successful login to the app, users need to grant pre-existing onboarding permissions for allowing notification permission to enable Defender for Endpoint to notify them when a threat is found. </li>



<li>Once permission is accepted, the user will see a page where permission is asked to collect diagnostic data for future product improvements. If the user opts out, no data will be sent. </li>



<li>Upon successful onboarding, users will see a new card and a tab labelled &#8220;Network Protection&#8221;. If Wi-Fi is OFF – In-app messaging will guide users to turn on the Wi-Fi from within the app. Once the Wi-Fi has been enabled, the Wi-Fi networks are scanned for threats, and the scan results determine the device&#8217;s state. </li>
</ul>



<h3>Android</h3>



<ul>
<li>Users need to enable location permissions; this allows Defender for Endpoint to scan their networks and alert the users when there are WIFI-related threats. If the user denies the location permissions, Defender for Endpoint will only be able to provide limited protection against network threats and will only protect the users from rogue certificates. </li>



<li>Once permission is accepted, the user will see a page where permission is asked to collect diagnostic data for future product improvements. If the user opts out, no data will be sent. </li>



<li>Once the app is installed, users will see a new card and a tab labelled &#8220;Network Protection&#8221;. Tapping on the feature card will take users to a page where they can initiate a scan for all available networks and certificates. </li>



<li>If Wi-Fi is OFF – In-app messaging will guide users to turn on the Wi-Fi from within the app. Once the Wi-Fi has been enabled, the Wi-Fi networks are scanned for threats, and the scan results determine the device&#8217;s state. </li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Network Protection in Action</h2>



<p>By this point, all of the policies have been set up, and users have also logged into the MDE app. The device will be onboarded in Microsoft Defender for Endpoint and visible in the Defender admin console a few minutes after launching the app.</p>



<p>Now, to simulate a network attack, I have not trusted the enterprise root certificate for Android devices. This means that as soon as the MDE policy sync is completed, an alert for a suspicious certificate should be generated, and the device should be reported.</p>



<p>And voila! It&#8217;s immediate and works!</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-62.png?resize=750%2C388&#038;ssl=1" alt="" class="wp-image-877" width="750" height="388" srcset="https://irlimages.blob.core.windows.net/2022-11/image-62.png?resize=1024%2C529&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-62.png?resize=300%2C155&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-62.png?resize=768%2C397&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-62.png?w=1449&amp;ssl=1 1449w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Device in defender admin center</em></figcaption></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-63.png?resize=712%2C134&#038;ssl=1" alt="" class="wp-image-878" width="712" height="134" srcset="https://irlimages.blob.core.windows.net/2022-11/image-63.png?w=949&amp;ssl=1 949w, https://irlimages.blob.core.windows.net/2022-11/image-63.png?resize=300%2C57&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-63.png?resize=768%2C145&amp;ssl=1 768w" sizes="(max-width: 712px) 100vw, 712px" data-recalc-dims="1" /><figcaption class="wp-element-caption">A<em>lert classification</em></figcaption></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Wrapping Up</h2>



<p>As the world continues to make sense of digital transformation, the mobile network protection feature in Defender for Endpoint will help us to identify, assess, and remediate endpoint weaknesses with the help of robust threat intelligence.</p>



<p>And with this new cross-platform coverage, threat and vulnerability management capabilities now support all major device platforms.</p>



<p>It is recommended that you should configure alerts in Defender for this network protection. </p>



<p>I&#8217;d love to know what you think, so do leave your comments below, and if you liked it, then do share it.</p>



<p><strong>Cheers</strong>/</p>



<p>Somesh</p>



<p><em>Ref</em>:</p>



<p class="has-small-font-size"><a href="https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/mobile-network-protection-for-defender-for-endpoint-on-android/ba-p/3559121?WT.mc_id=EM-MVP-5004955"><em>Announcing the public preview of Mobile Network Protection for Microsoft Defender on Android and iOS</em></a></p>



<p class="has-small-font-size"><a href="https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/ios-configure-features?view=o365-worldwide&amp;viewFallbackFrom=o365-worldwide%2F%3FWT.mc_id%3DEM-MVP-5004955"><em>Configure Microsoft Defender for Endpoint on iOS features | Microsoft Learn</em></a></p>



<p></p>



<p> </p>
<!--kg-card-end: html-->