---
title: "macOS Management with Intune - The Prologue"
date: 2022-10-19T13:00:03"
draft: false
tags: []
---

<!--kg-card-begin: html--><h2>Overview</h2>


<p>macOS is the operating system that powers every MacBook. As per Apple,<strong>it lets you do things you can't do with other computers</strong>. Yeah, it's a never ending argument but not let's get into it and get those Macs managed with Intune.</p>

<p>Although most laptops/desktops we manage daily are PCs, there will still be a few Macs in your inventory that you want to manage. With Microsoft Intune, you can easily streamline device management for your macOS devices.</p>

<p>Over the coming days, we will explore all the possibilities of enrolling personal and company-owned MacBooks with industry-standard policies; restrictions. Let's get started, then.</p>


<h2>Things to Consider Before Enrolling macOS in Intune</h2>

<p>A few prerequisites must be met before any Apple device can be enrolled in Intune. I have covered them in my previous posts - but let's revisit them again.</p>


<ol><li>Devices purchased in <a href="https://school.apple.com/" target="_blank" rel="noreferrer noopener"> Apple School Manager </a> or <a href= "http://deploy.apple.com/" target="_blank" rel="noreferrer noopener"> Apple's Automated Device Enrollment</a></li><li>A list of serial numbers or a purchase order number. </li><li>Intune configured MDM authority.</li><li>Apple MDM Push certificate</li></ol>



<p>After you enable enrollment, you can also enrol user-owned macOS devices as BYOD in Intune.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong><span style="text-decoration: underline;">Company-owned macOS devices</span></strong></p>

<p>Intune supports the following enrollment methods for company-owned macOS devices</p>

<p>1. Automated Device Enrollment (ADE)</p>

<p>2. Device Enrollment Manager (DEM)</p>

<p>3. Direct Enrollment</p>

<p><strong><span style="text-decoration: underline;">User-approved enrollment</span></strong></p>


<p>All Mac enrollments in Intune are considered user-approved. User-approved enrollment lets you manage macOS devices that aren't part of Apple Business Manager and provides the same level of controlas supervised macOS. Intune automatically turns on supervision for user-approved devices. The only major difference is that the user signs in to the Company Portal app to initiate enrollment.</p>

<hr class="wp-block-separator has-alpha-channel-opacity"/>


<h2>Apple MDM push certificate</h2>

<p>You need an Apple MDM Push certificate to manage your iOS/iPadOS and macOS devices in Microsoft Intune. This token enables devices to enrol via Intune Comp Portal or ADE/ASM/AC2. </p>



<p>Sign in to <a href="https://aka.ms/dmac" target="_blank" rel="noreferrer noopener">Intune Portal</a>, choose<strong> Devices</strong> > <strong>Enroll devices</strong> > <strong>Apple enrollment</strong> > <strong>Apple MDM Push Certificate</strong>, and follow these steps:</p>



<ol><li>Select <strong>I agree </strong>to give Microsoft permission to send data to Apple.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20141555.png/:/rs=w:1280" alt="" width="640" height="265"/></figure></div>


<ol start="2"><li>Select <strong>Download your CSR</strong> to download and save the file locally. The file is used to request a trust relationship certificate from the Apple Push Certificates Portal.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20142101.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="313"/></figure></div>


<ol start="3"><li>Select <strong>Create your MDM push Certificate</strong> to the Apple Push Certificates Portal and sign in with your organization id. <em><strong>(Please use a corporate id as your Apple ID, preferably, it should be a service account. Avoid using your personal Apple ID.</strong></em></li></ol>



<ol start="4"><li>Select <strong>Create a Certificate</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20143818.png/:/rs=w:1280" alt="" width="640" height="286"/></figure></div>


<ol start="5"><li>Read and agree to the terms and conditions. Then select <strong>Accept</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20143854.png/:/rs=w:1280" alt="" width="564" height="418"/></figure></div>


<ol start="6"><li>Select <strong>Choose File</strong> and select the CSR file you downloaded in Intune.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20143920.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="603" height="379"/></figure></div>


<ol start="7"><li>Select <strong>Upload</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20143938.png/:/rs=w:1280" alt="" width="640" height="281"/></figure></div>


<ol start="8"><li>On the confirmation page, select <strong>Download</strong>. The certificate file (.pem) downloads to your device. Save this file as we will upload it in Intune.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20144136.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="265"/></figure></div>


<ol start="9"><li>Return to the admin center and enter your Apple ID as a reminder for when you need to renew the certificate.</li></ol>



<ol start="10"><li>Browse to your Apple MDM push certificate to upload. Select <strong>Upload</strong> to finish configuring the MDM push certificate.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-26%20144337.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="338"/></figure></div>

<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled.png/:/rs=w:1280" alt="" width="640" height="278"/></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



    <h2><strong>Create and Upload the Apple Automated Device Enrollment token</strong></h2>


<p>So the pre-requisite is done, but before you can enrol macOS devices, you would need an Apple Server Token (.p7m) file from Apple. This token syncs information from Intune to ADE devices that your corporation owns. It also allows Intune to assign enrollment profiles to Apple and to assign devices to those profiles.</p>

<p>Follow the steps below to create & upload the ADE token:</p>



<ol><li>In <a href="https://endpoint.microsoft.com/" target="_blank" rel="noreferrer noopener">Intune portal</a>, select <strong>Devices</strong> > <strong>macOS</strong> > <strong>macOS enrollment</strong> > <strong>Enrollment Program Tokens</strong> > <strong>Add</strong>.</li></ol>

    
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/macos_token_create0.jpg"/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="313"/></figure></div>
    
<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img class="wp-image-515" src="https://irlimages.blob.core.windows.net/images/macos_token_create.png?resize=512%2C91&amp;ssl=1" sizes="(max-width: 512px) 100vw, 512px" srcset="https://irlimages.blob.core.windows.net/images/macos_token_create.png?w=1023&amp;ssl=1 1023w, https://irlimages.blob.core.windows.net/images/macos_token_create.png?resize=300%2C53&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/macos_token_create.png?resize=768%2C136&amp;ssl=1 768w" alt="" width="650" height="500" data-recalc-dims="1" /></figure>
</div>

<ol start="2"><li>Select <strong>Download the Intune public key certificate required to create the token</strong>. This step downloads and saves the encryption key (.pem) file locally. The .pem file requests a trust relationship certificate from the Apple Business Manager portal.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img class="wp-image-515" src="https://irlimages.blob.core.windows.net/images/macos_token_create2.png?resize=512%2C91&amp;ssl=1" sizes="(max-width: 512px) 100vw, 512px" srcset="https://irlimages.blob.core.windows.net/images/macos_token_create2.png?w=1023&amp;ssl=1 1023w, https://irlimages.blob.core.windows.net/images/macos_token_create2.png?resize=300%2C53&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/macos_token_create2.png?resize=768%2C136&amp;ssl=1 768w" alt="" width="650" height="300" data-recalc-dims="1" /></figure>
</div>


<ol start="3"><li>Click on <a href="https://business.apple.com/#main" target="_blank" rel="noreferrer noopener">Create a token via Apple Business Manager</a> to open the Apple Business Manager portal for creating your ADE token (MDM server).</li></ol> 


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/macos_token_create3.jpg?resize=512%2C91&#038;ssl=1" alt="" class="wp-image-515" width="650" height="500" srcset="https://irlimages.blob.core.windows.net/images/macos_token_create3.jpg?w=1023&amp;ssl=1 1023w, https://irlimages.blob.core.windows.net/images/macos_token_create3.jpg?resize=300%2C53&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/macos_token_create3.jpg?resize=768%2C136&amp;ssl=1 768w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/macos_token_create_warning.jpg?resize=512%2C91&#038;ssl=1" alt="macos_token_create_warning" class="wp-image-515" width="650" height="500" srcset="https://irlimages.blob.core.windows.net/images/macos_token_create_warning.jpg?w=1023&amp;ssl=1 1023w, https://irlimages.blob.core.windows.net/images/macos_token_create_warning.jpg?resize=300%2C53&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/macos_token_create_warning.jpg?resize=768%2C136&amp;ssl=1 768w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>
    
<ol start="4"><li>Sign in with your company’s Apple ID in Apple Business Manager.</li></ol>


<ol start="4"><li><p>In <strong>Apple Business Manager</strong>, click your account name at the bottom of the sidebar, then choose <strong>Preferences </strong> from the pop-up menu</p>.</li></ol>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/ABM_profile.png?resize=512%2C91&#038;ssl=1" alt="" class="wp-image-515" width="650" height="500" srcset="https://irlimages.blob.core.windows.net/images/ABM_profile.png?w=1023&amp;ssl=1 1023w, https://irlimages.blob.core.windows.net/images/ABM_profile.png?resize=300%2C53&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/ABM_profile.png?resize=768%2C136&amp;ssl=1 768w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>    

<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/Add-MDM-Server.png"/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="Add-MDM-Server" width="650" height="313"/></figure></div>


<ol start="5"><li>Upload the public key you downloaded from Intune in step 2. You can type the server name to identify your MDM tenant quickly;</li></ol>


<ol start="6"><li>After you save the MDM server, select it and download the token (.p7m file).</li></ol>

<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-30.png?resize=512%2C276&#038;ssl=1" alt="ADE-token-warning" class="wp-image-519" width="512" height="276" srcset="https://irlimages.blob.core.windows.net/images/image-30.png?resize=1024%2C551&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-30.png?resize=300%2C161&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-30.png?resize=768%2C413&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-30.png?w=1280&amp;ssl=1 1280w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure>

<p>You&rsquo;ll be informed that download a new server token will reset any existing tokens. This is OK since we are creating a new connection so click the Download Server Token button.</p>


<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/ADE-token-warning.png?resize=512%2C276&#038;ssl=1" alt="ADE-token-warning" class="wp-image-519" width="512" height="276" srcset="https://irlimages.blob.core.windows.net/images/ADE-token-warning.png?resize=1024%2C551&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/ADE-token-warning.png?resize=300%2C161&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/ADE-token-warning.png?resize=768%2C413&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/ADE-token-warning.png?w=1280&amp;ssl=1 1280w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure>


<ol start="7"><li>Now, back to Intune portal – Step 4. Upload the token and click Next and then save.&nbsp;</li></ol>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-31.png?resize=750%2C164&#038;ssl=1" alt="" class="wp-image-520" width="750" height="164" srcset="https://irlimages.blob.core.windows.net/images/image-31.png?resize=1024%2C224&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-31.png?resize=300%2C66&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-31.png?resize=768%2C168&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-31.png?w=1519&amp;ssl=1 1519w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2><strong>Assign devices to the Apple token (MDM server)</strong></h2>



<ol><li>In&nbsp;<a href="https://business.apple.com/" target="_blank" rel="noreferrer noopener">Apple Business Manager</a>&nbsp;&gt;&nbsp;<strong>Devices</strong>, select the devices you want to assign to this token. You can also choose multiple devices simultaneously or define that all devices are, by default, assigned to this token.</li><li>Edit device management and select the MDM server you just added.&nbsp;</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Create an Apple Enrollment Profile</h2>



<p>Once you&#8217;ve installed your token, the next step is creating an enrollment profile for devices. A device enrollment profile defines the settings that will be applied to the devices in this profile.</p>



<ol><li>In the&nbsp;<a href="https://aka.ms/dmac" target="_blank" rel="noreferrer noopener">Intune portal</a>, choose&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>macOS</strong>&nbsp;&gt;&nbsp;<strong>macOS Enrollment</strong>&nbsp;&gt;&nbsp;<strong>Enrollment program tokens</strong>.</li></ol>



<ol start="2"><li>Select a token, choose&nbsp;<strong>Profiles</strong>, and then choose to&nbsp;<strong>Create profile</strong>&nbsp;&gt;&nbsp;<strong>macOS</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-32.png?resize=642%2C210&#038;ssl=1" alt="" class="wp-image-521" width="642" height="210" srcset="https://irlimages.blob.core.windows.net/images/image-32.png?w=856&amp;ssl=1 856w, https://irlimages.blob.core.windows.net/images/image-32.png?resize=300%2C98&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-32.png?resize=768%2C251&amp;ssl=1 768w" sizes="(max-width: 642px) 100vw, 642px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>Provide a&nbsp;<strong>Name</strong>&nbsp;and&nbsp;<strong>Description</strong>&nbsp;for the profile (These details will not be visible to users) and click&nbsp;<strong>Next</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-33.png?resize=599%2C320&#038;ssl=1" alt="" class="wp-image-522" width="599" height="320" srcset="https://irlimages.blob.core.windows.net/images/image-33.png?w=798&amp;ssl=1 798w, https://irlimages.blob.core.windows.net/images/image-33.png?resize=300%2C161&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-33.png?resize=768%2C411&amp;ssl=1 768w" sizes="(max-width: 599px) 100vw, 599px" data-recalc-dims="1" /></figure></div>


<ol start="4"><li>In the management settings page, select “<strong>Enroll with User Affinity”,&nbsp;</strong>as we will use this profile to enrol devices associated with users.</li></ol>



<ol start="5"><li>As we selected&nbsp;<strong>Enroll with User Affinity</strong>&nbsp;for the&nbsp;<strong>User Affinity</strong>&nbsp;field and chose the&nbsp;Setup Assistant with modern authentication as the authentication method. </li></ol>



<p>The advantage of using modern authentication with setup assistance is that until &amp; unless the user signs in to the Company Portal using his/her Azure AD credentials, the device:</p>



<ul><li>Won’t be fully registered with Azure AD.</li><li>Won’t show up in the user’s device list in the Azure AD portal.</li><li>Won’t have access to resources protected by conditional access.</li><li>Won’t be evaluated for device compliance.</li><li>Will be redirected to the Company Portal from other apps if the user tries to open any managed applications that are protected by conditional access.</li></ul>



<p>With locked enrollment, you make the device more secure as it disables macOS settings that allow the management profile to be removed from the&nbsp;<strong>System Preferences</strong>&nbsp;menu or through the&nbsp;<strong>Terminal</strong>. After device enrollment, the user cannot change this setting without wiping the device.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-35.png?resize=626%2C321&#038;ssl=1" alt="" class="wp-image-523" width="626" height="321" srcset="https://irlimages.blob.core.windows.net/images/image-35.png?w=835&amp;ssl=1 835w, https://irlimages.blob.core.windows.net/images/image-35.png?resize=300%2C154&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-35.png?resize=768%2C394&amp;ssl=1 768w" sizes="(max-width: 626px) 100vw, 626px" data-recalc-dims="1" /></figure></div>


<ol start="6"><li>On the&nbsp;<strong>Setup Assistant</strong>&nbsp;page, update settings for “Department” &amp; “Department Phone&nbsp;Number” and choose to show or hide the Setup Assistant screens on the device when the user sets it up.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-36.png?resize=512%2C491&#038;ssl=1" alt="" class="wp-image-525" width="512" height="491" srcset="https://irlimages.blob.core.windows.net/images/image-36.png?resize=1024%2C981&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-36.png?resize=300%2C287&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-36.png?resize=768%2C736&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-36.png?w=1046&amp;ssl=1 1046w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>


<ol start="7"><li>Select&nbsp;<strong>Next</strong>&nbsp;to go to <strong>Review + create</strong>.</li></ol>



<ol start="8"><li>To save the profile, choose to&nbsp;<strong>Create</strong>.</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Sync managed devices</strong></p>



<p>Now that Intune has permission to manage your devices, we have to synchronize Intune with Apple to see your managed devices in Intune portal.</p>



<p><strong>Sync managed devices</strong></p>



<p>Now that Intune has permission to manage your devices, we have to synchronize Intune with Apple to see your managed devices in Intune portal.</p>



<p>We have everything in place. Should we now distribute the devices to users?  No..wait! This was just the initial part; before you roll out any device to your end users, ensure compliance policies, restrictions &amp; mandatory apps are configured in Intune. So, let us move to the next part of the <a href="https://intuneirl.com/2022/10/macos-management-with-intune-part-ii/" title="">series</a> with configuring compliance policies &amp; enforcing restrictions and pushing the mandatory apps to the users/devices. </p>



<p>Stay In(tuned) 👩‍💻👩‍💻 and be #intuneinspired</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>
</body><!--kg-card-end: html-->