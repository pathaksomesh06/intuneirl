---
title: "Code Sign & Publish Your iOS Apps"
date: 2022-08-24T22:16:00"
draft: false
tags: []
---


<p>Code signing is the process of digitally signing the app before it can be deployed to your user’s devices, and before any app can be installed on an iOS device, it should be code signed by its developer. Code signing your app assures users that it’s from a known source and hasn’t been modified since it was last signed. Before your app can integrate app services, be installed on a device, or be submitted to the App Store, it must be signed with a certificate issued by Apple.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/wat-you-think-ure-an-ios-developer.jpg/:/rs=w:1280" alt="" width="281" height="307"/></figure>



<p><strong>Sounds simple?</strong></p>



<p>The entire code signing process is one of the most complex and complicated tasks in managing and distributing your iOS apps. It’s certainly a different experience than compiling and running your code.</p>



<p>Let’s simplify this without getting into iOS development. In this article, I’ll walk you through the process of code signing & distributing iOS apps.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Basics & Pre-requisites:</strong></h4>



<ol><li><strong>MacBook</strong></li><li><strong>Xcode</strong></li><li><strong>Apple Developer Program</strong></li><li><strong>CSR (Certificate Signing Request)</strong></li><li><strong>Certificates</strong></li><li><strong>App Identifier </strong></li><li><strong>Provisioning profiles</strong></li><li><strong>IPA to be signed</strong></li></ol>



<p>Let’s get going, then…</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Xcode</strong></h4>



<p>For developing any iOS or macOS app, you will usually require <strong>Xcode</strong>. It has everything you need to develop, test, or distribute apps across all Apple platforms or if you want to publish your apps to the Apple Appstore<em>.</em> Check out this link to learn more about <a rel="noreferrer noopener" href="https://developer.apple.com/xcode/" target="_blank"><u><strong>Xcode</strong></u></a>. Alright then, grab your MacBook and download Xcode from <a rel="noreferrer noopener" href="https://apps.apple.com/us/app/xcode/id497799835?mt=12" target="_blank"><strong>Appstore</strong></a>.</p>



<p><strong>Patience is a virtue here: </strong><em><strong>Xcode is around 13Gigs and will take time to download and install on your Mac. </strong></em></p>



<p>Minimum requirements for Xcode: <a href="https://developer.apple.com/support/xcode/" rel="noreferrer noopener" target="_blank">https://developer.apple.com/support/xcode/</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Certificates</strong></h4>



<p><strong>CSR (Certificate Signing Request)</strong><strong>: </strong>The first step in code signing iOS apps is creating a certificate signing request (CSR). You will need the development and distribution certificates to build and deliver your apps. A <strong>Certificate Signing Request (CSR)</strong> must be generated to accomplish that. You can use your MacBook to generate a CSR file and a set of private and public keys. This certificate allows you to sign and distribute apps to your end users/devices. Follow the steps to create a CSR on your Mac:</p>



<ul><li> Launch <strong>Keychain Access </strong>on the Mac</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/blob-0014.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="416"/></figure>



<ul><li> Choose Keychain Access > Certificate Assistant > Request a Certificate from a Certificate Authority.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/10/Untitled.png?resize=750%2C456&ssl=1" alt="" class="wp-image-641" width="750" height="456" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/10/Untitled.png?resize=1024%2C623&ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/10/Untitled.png?resize=300%2C183&ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/10/Untitled.png?resize=768%2C467&ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/10/Untitled.png?w=1280&ssl=1 1280w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li> In the Certificate Assistant page, enter an email address in the U<strong>ser Email Address field</strong>.</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-08-21%20at%2003.32.59.png/:/rs=w:1280/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="487"/></figure>



<ul><li>  In the <strong>Common Name field</strong>, enter a name for the key.</li><li>  Leave the CA Email Address field <strong>empty</strong>.</li><li>  Choose “<strong>Saved to Disk</strong>” then click Continue.</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-08-21%20at%2003.34.13.png/:/rs=w:1280/:/rs=w:1280" alt="" width="640" height="487"/></figure>



<ul><li>  Click on <strong>Done</strong>. You will have a CSR on your local machine at the end of this process.</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Apple Developer Program</strong></h4>



<p>The <strong>“Code to customer”</strong> pipeline that’s what Apple defines as the Apple Developer Program.  Membership to the Apple Developer Program is paid, giving developers everything they need to build, test and deploy apps for Apple platforms. When you sign-up for this, you get a hell lot of features & benefits, to list a few:</p>



<ul><li> Beta OS Releases</li><li> Gain full access to a wide variety of tools</li><li> Services and Capabilities</li><li> Developer Events</li><li> Support, etc</li></ul>



<p>It is recommended that you purchase <a href="https://developer.apple.com/programs/enterprise/" rel="noreferrer noopener" target="_blank"><u><strong>Enterprise Program</strong></u></a> as it gives you additional benefits as enterprise customers to develop and deploy proprietary, internal-use apps to your users/devices. I will not go into details about Apple Developer Enterprise Program.</p>



<p><strong>Create enterprise distribution certificates</strong></p>



<p>A distribution certificate identifies your team/organization within a distribution provisioning profile. It allows you to submit your app to the Apple App Store or distribute it within your organization through MDM or a secure website. </p>



<p>1. In <a href="https://developer.apple.com/account/resources/certificates/list" rel="noreferrer noopener" target="_blank">Certificates, Identifiers & Profiles</a>, click Certificates.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled%202.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="388"/></figure>



<p>2. Click the add button (+) on the top left.</p>



<p>3. Under Software, select “<strong>iOS Distribution</strong>” then click Continue.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-0006.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="320"/></figure>



<p>4. Click on <strong>Choose File</strong> to upload the <strong>CSR</strong> file we generated previously in <strong>Step 2 –<br>   Certificates.</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-08-21%20at%2006.32.01.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="177"/></figure>



<p>5. Click <strong>Continue</strong>.</p>



<p>6. Click <strong>Download, </strong>and it will download a certificate (with <strong>.cer extension</strong>).</p>



<p>7. To install the certificate in your keychain, double-click the <strong>downloaded certificate file</strong>.</p>



<p>8.  The certificate appears in the My Certificates category in Keychain Access.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Create App Identifier</strong></h4>



<p>To make the app uniquely identifiable, you must register an App Identifier (App ID). Follow the septs to create an app identifier:</p>



<p>1. In <a href="https://developer.apple.com/account/resources" rel="noreferrer noopener" target="_blank">Certificates, Identifiers & Profiles</a>, click Identifiers in the sidebar, then click the add button (+) on the top left.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/a.jpg/:/rs=w:1280" alt="" width="640" height="341"/></figure>



<p>2. Select <strong>App IDs</strong> from the list of options and click continue. Confirm App ID type is automatically selected from the options, then click Continue.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20231745.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="323"/></figure>



<p>3. Enter a <strong>name or description</strong> for the App ID in the Description field. (<strong>The bundle id should be unique.</strong>)</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20231942.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="358"/></figure>



<p>4. Select the corresponding checkboxes to enable the app capabilities you want to use.</p>



<p>5. Click Continue, review the registration information and click Register. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Create Provisioning Profile</strong></h4>



<p>A provisioning profile authorizes your app to use certain app services and ensures that you’re a known developer developing, uploading, or distributing your app. A provisioning profile contains a single App ID that matches one or more of your apps and a distribution certificate. Follow the steps below to create a provisioning profile for your app:</p>



<p>1. In <a href="https://developer.apple.com/account/resources/certificates/list" rel="noreferrer noopener" target="_blank">Certificates, Identifiers & Profiles</a>, click Profiles in the sidebar.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20232255.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="193"/></figure>



<p>2. Under Distribution, select Ad Hoc or tvOS Ad Hoc as the distribution method, then click <strong>Continue</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20232411.jpg/:/rs=w:1280" alt="" width="577" height="382"/></figure>



<p>3. Choose the App ID you used for development, which matches your bundle ID, from the App ID pop-up menu, then click Continue.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20232532.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="248"/></figure>



<p>4.  Select the distribution certificate you want to use, then click Continue.</p>



<p>5. Provide a name for the <strong>Provisioning Profile</strong> for identifying the profile in the Apple Developer Portal. Click on <strong>Generate</strong>.</p>



<p>6. Click Download.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Codesign the App</strong></h4>



<p>Now the fun stuff starts! <strong>To recap</strong>– we have the <strong>distribution certificate</strong> and installed it in the keychain; we have also registered our app in Apple Developer Program and downloaded the <strong>provisioning profile</strong>. Good, then let us get going!</p>



<p><em>(</em><em><strong>Assumptions:</strong></em><em> You have a MacBook,</em> and you have received the xArchives for the iOS app from your iOS developer, or they have shared the <em>.app file of the app with you.</em>)</p>



<p><strong>A. </strong><strong>Update info.plist</strong><strong>:</strong></p>



<p>1. On your MacBook, Download the xArchives zip file you may receive from your iOS developer and copy the .app file.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20232838.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="241"/></figure>



<p>2. Create a folder on your Mac and paste the .app file here.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20233116.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="287"/></figure>



<p>3. Right-click on the .app file and select “<strong>Show Package Contents</strong>.”</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20233233.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="493" height="395"/></figure>



<p>4. Once you are inside the package, locate <strong>info.plist</strong> file and open it in <strong>Xcode</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-08-23%20at%2022.05.04.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="459"/></figure>



<p>5. Now, in Xcode, update the <strong>value</strong> for “<strong>Bundle Identifier</strong>” in the info.plist and make sure it matches the app identifier we created for this app.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/b.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="596"/></figure>



<p>6. In the same info.plist, if required, update the app version.</p>



<p>7. Click File->Save to save the changes.</p>



<p><strong>B. </strong><strong>Create Entitlement file:</strong></p>



<p>Entitlements specify which resources of the system an app is allowed to use and under what conditions. It is a configuration list of what you allow or deny for your app. You can use Xcode to create the entitlements.plist file. The format looks like this:</p>



<p>Save this file in the same folder where you have copied the .app file.</p>



<p>Download the provisioning profile from Apple Developer Portal and copy it to the same folder. Rename it to <strong>embedded.mobileprovision. So, your folder structure should look like this:</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/c..png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="600"/></figure>



<p><strong>C. </strong><strong>Codesign</strong><strong>:</strong></p>



<p>Open Terminal at the folder location and follow the below steps to sign the app with your distribution certificate and provisioning profile:</p>



<p>1. Remove the code signature from the original app:</p>



<p>   <strong> rm -rf  my.app/_CodeSignature/</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/121.png/:/rs=w:1280" alt="" width="500" height="323"/></figure>



<p>2. Copy your provisioning profile to the app:</p>



<p>    <strong>cp embedded.mobileprovision my.app/embedded.mobileprovision</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/lwk.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="570" height="329"/></figure>



<p>3. Codesign app with your distribution certificate and entitlements plist. If the app has frameworks from the developers, you can delete them. Else, skip the “Frameworks” parameter. This will replace the signature and update the app with your signatures.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20234519.jpg/:/rs=w:1280" alt="" width="560" height="266"/></figure>



<p>4. Create a sub-folder eg. Payload and move the .app file into this folder.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20234625.jpg/:/rs=w:1280" alt="" width="640" height="245"/></figure>



<p>5. In Xcode, build the .ipa</p>



<p><strong>    zip -qr myapp.ipa Payload/</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-23%20235041.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="359"/></figure>



<p>and Voila! <strong>You have successfully signed the app.</strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Distribute the App</strong>:</h4>



<p>1. Sign in to the <a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank">Microsoft Endpoint Manager admin center</a>.</p>



<p>2. Select <strong>Apps</strong> > <strong>All apps</strong> > <strong>Add</strong>.</p>



<p>3. In the <strong>Select app type</strong> pane, select <strong>Line-of-business</strong> app under the Other app types.</p>



<p>4. Click <strong>Select</strong>. The <strong>Add app</strong> steps are displayed.</p>



<ul><li>In the <strong>Add app</strong> pane, click <strong>Select app package file</strong>.</li><li>In the <strong>App package file</strong> pane, select the browse button. Then, select an iOS/iPadOS<br> .<strong>ipa </strong>we just build. The app details will be displayed.</li><li>When you’re finished, select <strong>OK</strong> on the <strong>App package file</strong> pane to add the app.</li><li>On the <strong>App information</strong> page, add the details for your app. </li></ul>



<p>5. Select the <strong>installation intent </strong>for the app and assign it to the groups accordingly<strong>.</strong></p>
