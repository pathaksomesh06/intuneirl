---
title: "Company-Owned iOS Device -Automated Device Enrollment - Part I"
date: 2022-07-26T21:03:00"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<p><strong>Part 3 of the mega-series for managing iOS devices</strong></p>



<p><a rel="noreferrer noopener" href="https://business.apple.com/" target="_blank">Apple Business Manager</a>&nbsp;provides a quick and smooth onboarding process for devices purchased by organizations either directly from Apple or Apple Authorized Resellers or wireless carriers. After signing up for Apple Business Manager, you need to complete four steps before you can start distributing and managing the devices.&nbsp;Automated Device Enrollment&nbsp;(previously known as&nbsp;Device Enrollment Program) helps organizations to enroll large numbers of devices without users ever touching them.</p>



<p>When a user powers on the device, Setup Assistant, which you can easily configure to modify the out-of-box experience for Apple products, runs with the configured settings, and the device enrolls into Intune.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/07/215423.jpg" alt="" width="576" height="121"/></figure>



<p>As we have discussed in the previous post that ADE enrollments aren&#8217;t compatible with the App Store version of the Company Portal app. To fix this, you need to configure the app configuration policy for the comp portal as described&nbsp;<a href="https://intuneirl.se/apple-devices/f/company-portal-version-not-supported" rel="noreferrer noopener" target="_blank">here</a>.</p>



<h4><strong>Prerequisites before using ADE:</strong></h4>



<ol><li>Devices purchased through ADE.</li><li>Valid MDM authority</li><li>Apple MDM Push Certificate</li></ol>



<p>&nbsp;<strong>Max volume supported by Intune &amp; ADE:</strong></p>



<ol><li>Maximum enrollment profiles per token: 1,000 devices.</li><li>Maximum Automated Device Enrollment devices per profile: 200,000 devices per token.</li><li>Maximum Automated Device Enrollment tokens per Intune account: 2,000.</li></ol>



<h4><strong>Create &amp; Upload Apple MDM Push Certificate</strong></h4>



<p>You need an Apple MDM Push certificate to manage your iOS/iPadOS and macOS devices in Microsoft Intune. This token enables devices to enroll via Intune Comp Portal or ADE/ASM/AC2. Follow the steps mentioned in this article to create the Apple MDM push certificate and upload it to Intune Portal.</p>



<p>Sign in to the&nbsp;<a href="https://aka.ms/dmac" rel="noreferrer noopener" target="_blank">MEM Portal</a>, choose&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>Enroll devices</strong>&nbsp;&gt;&nbsp;<strong>Apple enrollment</strong>&nbsp;&gt;&nbsp;<strong>Apple MDM Push Certificate</strong>, and follow these steps:</p>



<p>1. &nbsp;Select&nbsp;<strong>I agree.</strong>&nbsp;to give Microsoft permission to send data to Apple.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/07/Screenshot2024-04-1022.06.42.png" alt="" width="640" height="265"/></figure>



<p>2. &nbsp;Select&nbsp;<strong>Download your CSR</strong>&nbsp;to download and save the file locally. The file is used to request a trust relationship certificate from the Apple Push Certificates Portal.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20142101.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="313"/></figure>



<p>3. &nbsp;&nbsp;Select&nbsp;<strong>Create your MDM push Certificate</strong>&nbsp;to the Apple Push Certificates Portal and sign in with your organization id.&nbsp;<em><strong>(Please use a corporate id as your Apple ID</strong></em><em><strong>&nbsp;</strong></em><em><strong>preferably, it should be a service account. Avoid using your personal Apple ID.)</strong></em></p>



<p>4. &nbsp;&nbsp;&nbsp;Select&nbsp;<strong>Create a Certificate</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20143818.png/:/rs=w:1280" alt="" width="640" height="286"/></figure>



<p>5. &nbsp;&nbsp;Read and agree to the terms and conditions. Then select&nbsp;<strong>Accept</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20143854.png/:/rs=w:1280" alt="" width="564" height="418"/></figure>



<p>&nbsp;6. &nbsp;Select&nbsp;<strong>Choose File</strong>&nbsp;and select the CSR file you downloaded in Intune.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20143920.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="603" height="379"/></figure>



<p>7. &nbsp;&nbsp;Select&nbsp;<strong>Upload</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20143938.png/:/rs=w:1280" alt="" width="640" height="281"/></figure>



<p>8. &nbsp;&nbsp;On the confirmation page, select&nbsp;<strong>Download</strong>. The certificate file (.pem) downloads to&nbsp;your device. Save this file as we will upload it in Intune.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20144136.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="265"/></figure>



<p>9. &nbsp;&nbsp;Return to the admin center and enter your Apple ID as a reminder for when you need to&nbsp;renew the certificate.&nbsp;</p>



<p>10. Browse to your Apple MDM push certificate to upload. Select&nbsp;<strong>Upload</strong>&nbsp;to finish&nbsp;configuring the MDM push certificate.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20144337.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="338"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled.png/:/rs=w:1280" alt="" width="640" height="278"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Create &amp; Upload Apple Automated Device Enrollment token</strong></h4>



<p>So the pre-requisite is done, but before you can enroll iOS/iPadOS devices, you would need an Apple Server Token (.p7m) file from Apple. This token syncs information from Intune to ADE devices that your corporation owns. It also allows Intune to assign enrollment profiles to Apple and to assign devices to those profiles.</p>



<p>Follow the steps below to create &amp; upload the ADE token:</p>



<p>1. &nbsp;In&nbsp;<a rel="noreferrer noopener" href="https://endpoint.microsoft.com/" target="_blank">Intune portal</a>, select&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>iOS/iPadOS</strong>&nbsp;&gt;&nbsp;<strong>iOS/iPadOS enrollment &gt; Enrollment&nbsp;Program Tokens</strong>&nbsp;&gt;&nbsp;<strong>Add</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20152510.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="423" height="222"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20152609.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="272"/></figure>



<p>2. &nbsp;Select&nbsp;<strong>Download the Intune public key certificate required to create the token</strong>. This&nbsp;step downloads and saves the encryption key (.pem) file locally. The .pem file is used to&nbsp;request a trust-relationship certificate from the Apple Business Manager portal.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20154212.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="512" height="91"/></figure>



<p>4. &nbsp;Click on &nbsp;<a rel="noreferrer noopener" href="https://business.apple.com/#main" target="_blank">Create a token via Apple Business Manager</a>&nbsp;to open the Apple Business Manager&nbsp;portal for creating your ADE token (MDM server).&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20152609.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="272"/></figure>



<p>5. Sign in with your company&#8217;s Apple ID in Apple Business Manager.</p>



<p>6. &nbsp;Click your&nbsp;<strong>name&nbsp;</strong>at the bottom of the sidebar &gt; Preferences, then click &#8220;Add&#8221;&nbsp;to add MDM Server.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20163710.png/:/rs=w:1280" alt="" width="640" height="308"/></figure>



<p>7. Upload the public key you downloaded from Intune in step 2. You can type the server name to identify your MDM tenant quickly.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20163840.png/:/rs=w:1280" alt="" width="640" height="288"/></figure>



<p>8. &nbsp;After you save the MDM server, select it and download the token (.p7m file). &nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20165528.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="345"/></figure>



<p>9. Now, back to Intune portal &#8211; Step 4. Upload the token and click Next and then save.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-0001.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="284"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Assign devices to the Apple token (MDM server)</strong>&nbsp;</h4>



<ol><li>In&nbsp;<a href="https://business.apple.com/" rel="noreferrer noopener" target="_blank">Apple Business Manager</a>&nbsp;&gt;&nbsp;<strong>Devices</strong>, select the devices you want to assign to this token. You can also choose multiple devices simultaneously or define that all devices are by default assigned to this token.</li><li>Edit device management and select the MDM server you just added.&nbsp;</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>In the next part of this blog, I will help you with creating Enrollment Profile and will walk you through the entire enrollment process for a supervised device. Stay Tuned&#8230; 🙂</strong></p>

<!--kg-card-end: html-->
