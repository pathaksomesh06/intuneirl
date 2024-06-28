---
title: "Just in Time Registration for iOS/iPadOS"
date: 2022-10-30T11:49:19"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<h2>Overview</h2>



<p>Just in Time, more commonly referred to as JIT, is a management philosophy used in several industries for decades. “<strong>Waste” is taken in its most general sense and includes time, resources, and</strong> <strong>materials</strong>. There are many elements to JIT in production; however, when referring to Mobile Device Management, the key features are:</p>



<ul><li>Continuous Improvement</li></ul>



<ul><li>Set-up time reduction</li></ul>



<ul><li>Automation</li></ul>



<ul><li>Eliminating waste</li></ul>



<p>Waste here refers to the total “non-value-addition time” in the device enrollment activity, i.e. from powering on the device to completing its enrollment. And with this new JIT device registration, it no longer requires the Company Portal app for Azure Active Directory (Azure AD) registration or compliance checking. Microsoft has removed the Non-VA steps; removed required app downloads that can’t be changed, and put an end to switching between apps to get the device compliant, thereby streamlining the user flow and reducing the overall enrollment time.</p>



<p>So, let us check what has changed and how it will help with device enrollment.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>The Move to Modern Authentication</h2>



<p>A few months back, we all received a notification that Apple will remove the Company Portal authentication method for all new and existing iOS/iPadOS ADE enrollment profiles in November 2022. </p>



<p>I have also written a post on it with all the steps needed to enrol the device with modern authentication. You can follow the steps in this article to configure the DEP profiles to use Setup Assistant with modern authentication.</p>



<p><a href="https://intuneirl.com/2022/09/enroll-supervised-ios-devices-with-modern-authentication-with-ios16/" target="_blank" rel="noopener" title="">Enrol Supervised iOS Devices With Modern Authentication With iOS16 – Intune – In Real Life (intuneirl.com)</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Behind the Scene : The Magic of SSO</h2>



<p>Single sign-on is a way of communications between services to which end-users want access and an identity providers that can confirm whether or not those end-users are who they say they are. Once enabled, SSO lets users access multiple services after providing their credentials only once—rather than requiring them to sign in to each service individually.</p>



<p>With the new approach, as soon as the user completes enrollment during Setup Assistant and lands on the home screen of the device, the user authentication has to be completed in any Microsoft Office application to register the device with Azure AD and kick off compliance. The compliance checks are integrated into the Office app so as soon as the user authentication is completed the device will be evaluated for complaince. Which removes the unnecessary step of switching between multiple apps to make the device compliant.</p>



<p>The enrollment SSO is based on Apple’s extensible SSO and on account-driven user enrollment, which was introduced in iOS and iPadOS 15.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-90.png?resize=530%2C346&ssl=1" alt="" class="wp-image-653" width="530" height="346" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-90.png?w=706&ssl=1 706w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-90.png?resize=300%2C196&ssl=1 300w" sizes="(max-width: 530px) 100vw, 530px" data-recalc-dims="1" /></figure></div>


<p>After the enrollment profile is downloaded, the first authentication happens in Setup Assistant and it completes enrollment with establishing the user device affinity while the next authentication handles Azure AD registration within a pre-authorized Office app. This ensures that SSO is fully established across the device.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-91.png?resize=750%2C506&ssl=1" alt="" class="wp-image-654" width="750" height="506" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-91.png?resize=1024%2C691&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-91.png?resize=300%2C202&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-91.png?resize=768%2C518&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-91.png?resize=1536%2C1036&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-91.png?w=1748&ssl=1 1748w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Configure JIT  Registration for ADE </h2>



<p>Create a device configuration policy under <strong>Device features</strong> > <strong>Category</strong> > <strong>Single sign-on app extension</strong>.</p>



<ul><li>Set the SSO app extension type to Microsoft Azure AD.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-92.png?resize=688%2C238&ssl=1" alt="" class="wp-image-655" width="688" height="238" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-92.png?w=917&ssl=1 917w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-92.png?resize=300%2C104&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-92.png?resize=768%2C265&ssl=1 768w" sizes="(max-width: 688px) 100vw, 688px" data-recalc-dims="1" /></figure></div>


<ul><li>Add the App bundle IDs for all the apps including Microsoft Office apps you want the SSO extension to apply to.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-93.png?resize=713%2C329&ssl=1" alt="" class="wp-image-656" width="713" height="329" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-93.png?w=951&ssl=1 951w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-93.png?resize=300%2C138&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-93.png?resize=768%2C355&ssl=1 768w" sizes="(max-width: 713px) 100vw, 713px" data-recalc-dims="1" /></figure></div>


<pre class="wp-block-code"><code>The first sign in must go through an app that is configured with the SSO extension so that Azure AD registration can be completed. After that, the user will be signed into any app that’s part of the SSO extension policy.</code></pre>



<ul><li>Add the required key value pair under the additional configuration.<ul><li><strong>Key</strong>: device_registration</li><li><strong>Type</strong>: String</li><li><strong>Value</strong>: {{DEVICEREGISTRATION}}</li></ul></li></ul>



<ul><li><strong>Key</strong>: browser_sso_interaction_enabled<ul><li><strong>Type</strong>: Integer</li></ul><ul><li><strong>Value</strong>: 1</li></ul></li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-94.png?resize=727%2C155&ssl=1" alt="" class="wp-image-657" width="727" height="155" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-94.png?w=969&ssl=1 969w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-94.png?resize=300%2C64&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-94.png?resize=768%2C163&ssl=1 768w" sizes="(max-width: 727px) 100vw, 727px" data-recalc-dims="1" /></figure></div>


<ul><li>Assign the profile to the required group</li></ul>



<p>Once these configuration steps are complete, the user will be able to complete setup and authentication on the device. They simply need to turn on the device, go through the Setup Assistant screens, and authenticate with their Azure AD credentials to fully enroll the device with Intune and establish user device affinity. When the user opens a managed Microsoft Office app that has an established SSO extension, the app automatically establishes SSO.</p>



<pre class="wp-block-code"><code><strong><span style="text-decoration: underline;">Please ensure that Microsoft Authenticator app is deployed as a required app the user group.</span></strong></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Wrapping Up</h2>



<p>This new feature of JIT device registration all super cool and you should try it out and implement it as it will change the way we have been enrolling ADE devices till now. And will also make the user productive quickly within minutes.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>

<!--kg-card-end: html-->
