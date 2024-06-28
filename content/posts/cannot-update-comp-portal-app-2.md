---
title: "Cannot Update Comp Portal App!"
date: 2022-07-19T21:14:00"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<p>If you enroll iOS/iPad OS devices using Apple&#8217;s ADE method, these devices will not be compatible with the public store version of the Comp Portal app. It requires you to configure the Comp Portal app to support iOS/iPadOS DEP devices using the app configuration policy, failing to which users will report issues with launching the company portal. If you use CA policies, your users may be blocked from accessing corp data on their devices. </p>



<p>Follow the below steps to configure the app configuration policy for the comp portal:</p>



<p>1. Open the Intune portal and navigate to Apps and iOS Apps.</p>



<p>2. Add Intune Comp portal app or use ABM to add the Comp portal to Intune</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/07/Screenshot2022-07-19.jpg" alt="" width="640" height="149"/></figure>



<p>3. Go to Apps -&gt; App Configuration Policies and click Add to create a new policy.</p>



<p>4. Select Managed Devices from the dropdown</p>



<p>5.  On the <strong>Basics</strong> page, set the following details:     </p>



<ul><li><strong>Name</strong>&nbsp;&#8211; The name of the profile</li><li><strong>Description</strong>&nbsp;&#8211; The description of the profile</li><li><strong>Device enrollment type</strong>&nbsp;&#8211; This setting is set to&nbsp;<strong>Managed devices</strong>.</li><li>Select&nbsp;<strong>iOS/iPadOS</strong>&nbsp;as the&nbsp;<strong>Platform</strong>.</li><li>Select&nbsp;<strong>Intune Comp Portal App</strong>&nbsp;from the&nbsp;<strong>Targeted app</strong>&nbsp;pane and click&nbsp;<strong>OK</strong>.</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/07/Screenshot2022-07-19204328.jpg" alt="" width="640" height="289"/></figure>



<p>6. &nbsp;From the dropdown, select&nbsp;<strong>Enter XML data</strong>&nbsp;and enter values for the XML property list as<br>&nbsp;&nbsp;&nbsp;&nbsp;shown below:</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/07/Screenshot2022-07-19205320.jpg" alt="" width="640" height="304"/></figure>



<p>&lt;dict&gt;</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&lt;key&gt;IntuneCompanyPortalEnrollmentAfterUDA&lt;/key&gt;</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&lt;dict&gt;</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;key&gt;IntuneDeviceId&lt;/key&gt;</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;string&gt;{{deviceid}}&lt;/string&gt;</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;key&gt;UserId&lt;/key&gt;</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;string&gt;{{userid}}&lt;/string&gt;</p>



<p>&nbsp;&nbsp;&nbsp;&nbsp;&lt;/dict&gt;</p>



<p>&lt;/dict&gt;</p>



<p>7. Click&nbsp;<strong>Next</strong>&nbsp;and assign the policy to your iOS device group(s).</p>



<p>Tip: If the company portal app is deployed via the VPP token on all your iOS devices, please ensure that you have set the VPP token to&nbsp;<strong>Auto-update the apps.&nbsp;</strong></p>



<p><strong>Otherwise, users will receive an &#8220;Update unavailable with this Apple ID&#8221; error while opening the Comp Portal app.</strong></p>

<!--kg-card-end: html-->
