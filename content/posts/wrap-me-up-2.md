---
title: "Wrap Me UP!"
date: 2022-09-13T15:16:00"
draft: false
tags: []
---


<p>Mobile Application Management (MAM) allows you to manage and protect your organization’s data within an application. MAM protects the data within the specific application and enables you to remotely erase the data of the corporate-owned apps from a mobile device. The rest of the device remains unaffected, including all personally owned data. Before proceeding further, the<strong> </strong>key here is to<strong> understand the difference between MDM & MAM</strong>.</p>



<p><strong>Mobile Device Management</strong>, commonly referred to as MDM, is a way of securing the entire mobile device, whereas <strong>Mobile Application Management </strong>(MAM) secures the applications on those devices. </p>



<p>When talking about <strong>MAM</strong>, the device may not be required to enroll. Line of Business apps can be made available in enterprise app stores, and users can install and download them on their personal devices. Apps run in secure containers (look & feel may differ based on hardware) to keep personal and corporate data separate.</p>



<p>There is no hard and fast rule for configuring App Protection Policies (APP) as it depends on you and how restrictive you want your policies to be for BYOD so that your corporate data is not compromised.</p>



<p>You can deploy MAM-enabled apps on the following platforms:</p>



<ol><li>Android</li><li>iOS/iPadOS</li><li>Windows</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Why do I need MAM-enabled Apps?</strong></h4>



<p>Mobile Application Management provides much more control to the organization with secure access to enterprise apps by separating them from personal apps along with restrictions such as copying or transferring app data from a work profile to a personal profile and many more such restrictions.</p>



<p>Benefits of using MAM:</p>



<ol><li>Controlled app deployment</li><li>Managed app</li><li>Controlled & secure distribution</li><li>Enhanced security poster</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Prerequisites for the App Wrapping:</strong></h4>



<p>Before you run the App Wrapping Tool, you need to fulfill some general prerequisites:</p>



<ul><li>Download the <a href="https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios">Microsoft Intune App Wrapping Tool for iOS</a> from GitHub.</li><li>A macOS computer that has the Xcode toolset version 11 or later installed.</li><li>The input iOS app must be developed and signed by your company or an independent software vendor (ISV).</li><li>The input app file must have the extension <strong>.ipa</strong> or <strong>.app</strong>.The input app must be compiled for iOS 12.2 or later.</li><li>The input app should not be encrypted.</li><li>The input app should not have extended file attributes.</li><li>The input app must have the <strong>entitlements plist</strong> before it can be wrapped. Entitlements give the app additional permissions and capabilities. </li></ul>



<p>In my <a href="https://intuneirl.com/2022/08/code-sign-publish-your-ios-apps/" target="_blank" rel="noreferrer noopener"><strong>previous blog post</strong></a>, I explained all the steps required for <strong>code signing </strong>the app as they will be the prerequisites for wrapping the apps. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Download & Install App Wrapping Tool</strong></h4>



<p>Microsoft Intune App Wrapping Tool for iOS helps you modify the behavior of your existing line-of-business (LOB) apps for iOS devices. It helps you manage certain app features without writing the code again.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Annotation%202022-09-12%20163824.png/:/rs=w:1280" alt="" width="392" height="78"/></figure>



<p>1. Download the App Wrapping Tool files from <a href="https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios" rel="noreferrer noopener" target="_blank"><strong>GitHub</strong></a> to a macOS computer.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-09-13%20at%2020.16.39.png/:/rs=w:1280" alt="" width="607" height="384"/></figure>



<p>2. Double-click <strong>Microsoft Intune Application Restrictions Packager for iOS.dmg</strong>. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-09-13%20at%2020.15.49.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="401"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-09-13%20at%2020.22.00.png/:/rs=w:1280" alt="" width="615" height="364"/></figure>



<p>3. Read & Accept the End User License Agreement (EULA).</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Wrap the App</strong></h4>



<p>1.  Launch Terminal and run the following command: </p>



<p><em><code><sup>/Volumes/IntuneMAMAppPackager/IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c "<SHA1 hash of the certificate>" -v true</sup></code></em></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-09-13%20at%2022.00.58.png/:/rs=w:1280" alt="" width="640" height="376"/></figure>



<p>The IntuneMAMPackager tool has many optional parameters you may need to add to wrap your application. Details are documented here – <a rel="noreferrer noopener" href="https://docs.microsoft.com/en-us/mem/intune/developer/app-wrapper-prepare-ios#command-line-parameters" target="_blank"><strong>Command-line parameters</strong></a><strong>.</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-09-13%20at%2022.12.35.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="312"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Post-wrapping</strong></h4>



<p>After the wrapping process, the message “<strong>The application was successfully packaged</strong>” is displayed.</p>



<p>The wrapped app will be saved in the output folder specified in the command. Now, you can upload the app to the Intune portal and assign it to the required groups.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Annotation%202022-09-13%20225232.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="216"/></figure>



<p>Although the app was uploaded as LoB, notice that the app is now “<strong>MAM Enabled</strong>“, which means that now you can assign App Protection Policies to this app.</p>



<p>As the app is now a <strong>managed app, </strong> you can configure <strong>App Protection Policy settings</strong> to:</p>



<ul><li>Protect your corporate data while leaving personal data untouched in the app.</li><li>Restricting data transfer and copy-and-paste functions</li><li>Encrypting corporate data</li><li>Configuring corporate web links to force open inside the managed browser e.g., Microsoft Edge</li><li>Enforcing access requirements to access corporate data</li><li>Enforcing conditional launch behaviors to protect the corporate data</li><li>Applying data loss prevention policies without managing the user’s device</li><li>Enabling app protection without requiring enrollment</li><li>Enabling app protection on devices managed with third-party Unified Endpoint Management Solutions</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>That’s all from my end, and I hope this helps you to protect your corporate data more efficiently and be proud of the feeling of code signing the iOS apps 😁😎😃</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/children-g7d9d4c1a2_1920-1.jpg?resize=750%2C500&ssl=1" alt="" class="wp-image-349" width="750" height="500" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/children-g7d9d4c1a2_1920-1.jpg?resize=1024%2C683&ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/children-g7d9d4c1a2_1920-1.jpg?resize=300%2C200&ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/children-g7d9d4c1a2_1920-1.jpg?resize=768%2C512&ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/children-g7d9d4c1a2_1920-1.jpg?resize=1536%2C1024&ssl=1 1536w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/children-g7d9d4c1a2_1920-1.jpg?resize=360%2C240&ssl=1 360w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/children-g7d9d4c1a2_1920-1.jpg?resize=600%2C400&ssl=1 600w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/children-g7d9d4c1a2_1920-1.jpg?w=1920&ssl=1 1920w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>
