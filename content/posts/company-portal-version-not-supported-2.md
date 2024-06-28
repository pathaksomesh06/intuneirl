---
title: "Company Portal Version Not Supported!"
date: 2022-07-23T21:11:00"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<p>This blog update will help you to troubleshoot the error “Company portal version not supported” when opening the Comp portal app on iOS or iPadOS devices.</p>



<p>When the users open the Comp portal, they receive a message asking them to update the app, and when they click the update button, it redirects them to the App Store. As the users are signed with their personal Apple ID, they receive the message&nbsp;<strong>“Update is not available with this Apple ID.”</strong></p>



<p>Since the app is purchased through Apple Business Manager with a VPP token so the app cannot be updated using a personal Apple ID.</p>



<p>This is expected behavior as the device tries to update the app via the end user’s personal Apple store. To avoid this, you have to keep the VPP apps auto-updated. Follow the below steps to configure the auto-update settings for the VPP app: </p>



<ol><li>Sign in to the&nbsp;<a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank">Microsoft Endpoint Manager admin center</a>.</li><li>Select&nbsp;<strong>Tenant administration</strong>&nbsp;&gt;&nbsp;<strong>Connectors and tokens</strong>&nbsp;&gt;&nbsp;<strong>Apple VPP tokens</strong>.</li><li>On the list of VPP tokens pane, select&nbsp;<strong>Create</strong>. The&nbsp;<strong>Create VPP token</strong>&nbsp;process is displayed.</li><li>On the&nbsp;<strong>Basics</strong>&nbsp;page, specify the following information:<ul><li><strong>Token Name</strong>&nbsp;&#8211; The token name.</li><li><strong>Apple ID</strong>&nbsp;&#8211; Enter the Managed Apple ID of the account used to create the token.</li><li><strong>VPP token file</strong>&nbsp;&#8211; Download the Apple Business Manager location token (Apple VPP<br>&nbsp;&nbsp;token) for your account and upload it here.</li></ul></li></ol>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/07/Screenshot2022-07-23110252.jpg" alt="" width="640" height="208"/></figure>



<p>5. &nbsp;Click&nbsp;<strong>Next</strong>&nbsp;to display the&nbsp;<strong>Settings</strong>&nbsp;page.</p>



<p>6. &nbsp;On the&nbsp;<strong>Settings</strong>&nbsp;page, specify the following information:</p>



<ul><li><strong>Take control of token from another MDM</strong> &#8211; Set this option to <strong>yes</strong> to allow the token to be reassigned to Intune from another MDM solution.</li><li><strong>Country/Region</strong> &#8211; Select the VPP country/region store. Intune synchronizes VPP apps for all locales from the specified VPP country/region store.</li></ul>



<figure class="wp-block-image"><img decoding="async" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/07/110023.jpg" alt=""/></figure>



<p>7.<strong>&nbsp;&nbsp;Type of VPP account</strong>&nbsp;&#8211; Choose from&nbsp;<strong>Business</strong>&nbsp;or&nbsp;<strong>Education</strong>.</p>



<p>8.<strong>  Automatic app updates</strong> &#8211; Choose from <strong>Yes</strong> to enable automatic updates. When enabled, Intune detects the VPP app updates inside the app store and automatically pushes them to the device when it checks in.</p>



<p>9.  <strong>I grant Microsoft permission to send user and device information to Apple.</strong> You must select <strong>I agree</strong> to proceed. </p>



<p>10.&nbsp;<strong>Review and create</strong>&nbsp;the token.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Synchronise a VPP token</strong></h4>



<p>You can synchronize the app names, metadata, and license information for your purchased apps in Intune by choosing <strong>Sync</strong> for a selected token.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/07/111154.jpg" alt="" width="640" height="245"/></figure>

<!--kg-card-end: html-->
