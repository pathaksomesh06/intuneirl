---
title: "Beyond the Basics: Advanced Android Enterprise Management with Microsoft Intune"
date: 2023-08-21T21:08:37"
draft: false
tags: []
---

<p>Are you using Microsoft Intune for Android Enterprise management and wondering how to unleash its full potential? Look no further! In this series, I'll guide you beyond the basics, helping you harness the power of Microsoft Intune to effectively manage your Android devices.</p><p>You will discover how to leverage Intune's capabilities to their fullest extent, ensuring efficient management, enhanced security, and increased productivity across your Android device fleet. Whether you are a beginner or an experienced user, the insights and tips will help you unlock the true potential of Microsoft Intune for Android Enterprise management.</p><p>Don't miss out on this opportunity to elevate your device management strategy to the next level. Let's dive in and harness the full potential of Microsoft Intune for Android Enterprise management. Here's a glimpse of what we'll be exploring:</p><ol><li><a href="#Integrating-Android-Enterprise-Management-and-MDM">Integrating Android Enterprise Management with MDM</a></li><li><a href="#How-an-Android-device-is-enrolled-provisioned">How an Android device is enrolled &amp; provisioned</a></li><li>Enrollment Methods for Android Devices in Intune</li><li>Creating and Managing Policies for Android Devices</li><li>Integrating Samsung Knox with Microsoft Intune</li><li>Automating Android Device Management with PowerShell and Graph API</li><li>Security and Compliance Best Practices in Intune</li><li>Managing App Configurations and Permissions</li><li>Troubleshooting Common Issues in Android Device Management</li><li>Real-world Case Studies of Android Enterprise Management</li><li>The Future of Android Management: Trends and Predictions</li><li>A Comprehensive Guide to Reporting and Analytics in Intune</li><li>End-User Training and Adoption Strategies</li><li>Device and App Lifecycle Management in Intune</li><li>Managing Remote Workforce with Android Devices and Intune</li><li>A Closer Look at Zero-Touch Enrollment for Android Devices</li></ol><hr><h2 id="integrating-android-enterprise-management-with-mdm"><a href="#Integrating-Android-Enterprise-Management-and-MDM">Integrating Android Enterprise Management with MDM</a></h2><p>Android Enterprise Management is a comprehensive solution that allows organizations to effectively manage and secure their Android devices. Microsoft Intune, on the other hand, is a powerful mobile device management (MDM) platform that integrates seamlessly with Android Enterprise, providing a wide range of features and capabilities for managing Android devices.</p><p>By combining Android Enterprise with Microsoft Intune, organizations can take advantage of a robust set of tools to enroll, configure, secure, and manage Android devices. Intune offers a unified management experience, allowing IT administrators to control device settings, deploy applications, enforce security policies, and manage updates, all from a centralized console.</p><p>Intune can be used to manage Android Enterprise devices using a variety of enrollment options, including:</p><ul><li>Work profile for employee-owned devices (BYOD)</li></ul><figure class="kg-card kg-image-card kg-card-hascaption"><img src="__GHOST_URL__/content/images/2023/08/image-6.png" class="kg-image" alt loading="lazy" width="588" height="334"><figcaption>BYOD</figcaption></figure><ul><li>Work profile for mixed-used company-owned devices</li></ul><figure class="kg-card kg-image-card kg-card-hascaption"><img src="__GHOST_URL__/content/images/2023/08/image-5.png" class="kg-image" alt loading="lazy" width="795" height="363" srcset="__GHOST_URL__/content/images/size/w600/2023/08/image-5.png 600w, __GHOST_URL__/content/images/2023/08/image-5.png 795w" sizes="(min-width: 720px) 720px"><figcaption>COPE</figcaption></figure><ul><li>Full management for work-only company-owned devices</li></ul><figure class="kg-card kg-image-card kg-card-hascaption"><img src="__GHOST_URL__/content/images/2023/08/image-7.png" class="kg-image" alt loading="lazy" width="556" height="351"><figcaption>COBO</figcaption></figure><ul><li>Full management for dedicated devices</li></ul><figure class="kg-card kg-image-card kg-card-hascaption"><img src="__GHOST_URL__/content/images/2023/08/image-8.png" class="kg-image" alt loading="lazy" width="939" height="321" srcset="__GHOST_URL__/content/images/size/w600/2023/08/image-8.png 600w, __GHOST_URL__/content/images/2023/08/image-8.png 939w" sizes="(min-width: 720px) 720px"><figcaption>KIOSKs</figcaption></figure><p>An Android Enterprise solution is a combination of three components: EMM solution (MS Intune in our case), Android Device Policy, and managed Google Play.</p><p><strong>Android Device Policy</strong></p><p>Every Android device that an organization manages through its MDM solution must have Android Device Policy installed during the setup process. Android Device Policy, provided by Android itself, is an application that autonomously enforces the management policies established in the MDM console on the respective devices.</p><figure class="kg-card kg-image-card kg-card-hascaption"><img src="__GHOST_URL__/content/images/2023/08/image-9.png" class="kg-image" alt loading="lazy" width="1074" height="629" srcset="__GHOST_URL__/content/images/size/w600/2023/08/image-9.png 600w, __GHOST_URL__/content/images/size/w1000/2023/08/image-9.png 1000w, __GHOST_URL__/content/images/2023/08/image-9.png 1074w" sizes="(min-width: 720px) 720px"><figcaption>Managed Google Play.</figcaption></figure><p>Managed Google Play represents the enterprise edition of Google Play, tailor-made to enhance app management within Android Enterprise solutions. It merges the well-known user interface and app store functions of Google Play with a collection of management features specifically engineered for corporate use. Managed Google Play can be embedded into your <strong>MDM <strong>console</strong></strong> to provide features such as:</p><ul><li>Public app search</li><li>Private app publishing</li><li>Web app publishing</li><li>App organization</li></ul><p>On devices that are managed, Managed Google Play serves as the enterprise app store for users. Its interface bears resemblance to the regular Google Play, allowing users to browse through apps, examine their details, and proceed with the installation. However, in contrast to the public version of Google Play, Managed Google Play restricts users to installing only those apps that have been specifically approved by their organization. This ensures alignment with corporate policies and helps maintain a secure environment.</p><p>Let's dive deeper to understand how Android devices are enrolled &amp; provisioned into MDM.</p><hr><h2 id="how-an-android-device-is-enrolled-provisioned"><a href="#How-an-Android-device-is-enrolled-provisioned">How an Android Device is Enrolled &amp; Provisioned</a></h2><figure class="kg-card kg-image-card kg-card-hascaption"><img src="__GHOST_URL__/content/images/2023/08/image-10.png" class="kg-image" alt loading="lazy" width="1249" height="396" srcset="__GHOST_URL__/content/images/size/w600/2023/08/image-10.png 600w, __GHOST_URL__/content/images/size/w1000/2023/08/image-10.png 1000w, __GHOST_URL__/content/images/2023/08/image-10.png 1249w" sizes="(min-width: 720px) 720px"><figcaption>Android Device Policy communication between MDM and managed devices</figcaption></figure><p>Device provisioning refers to the procedure of configuring a device so that it falls under the control of an enterprise through configured policies. This process involves the installation of Android Device Policy on the device, which then serves as the medium for receiving and enforcing these policies. If the provisioning proves successful, the API forms a device object, thereby linking the device to the enterprise.</p><p>The Android Management API initiates this provisioning process by utilizing enrollment tokens.  When an enrollment token is provided to a device, it triggers the provisioning process. This procedure not only includes the installation of the Android Device Policy but also the addition of a managed Google Play account to the device. Once the device has been successfully provisioned, it is identified within the system as a Devices resource. </p><figure class="kg-card kg-image-card kg-card-hascaption"><img src="__GHOST_URL__/content/images/2023/08/image-11.png" class="kg-image" alt loading="lazy" width="1789" height="795" srcset="__GHOST_URL__/content/images/size/w600/2023/08/image-11.png 600w, __GHOST_URL__/content/images/size/w1000/2023/08/image-11.png 1000w, __GHOST_URL__/content/images/size/w1600/2023/08/image-11.png 1600w, __GHOST_URL__/content/images/2023/08/image-11.png 1789w" sizes="(min-width: 720px) 720px"><figcaption>Device provisioning with enrollment token</figcaption></figure><p>The enrollment token and provisioning method you use establishes a device's ownership (personally-owned or company-owned) and management mode (work profile or fully managed device).</p><blockquote>Enrollment tokens expire after one hour by default, but you can specify a custom expiration time (<code>duration</code>)<strong> up to approximately 10,000 years!</strong></blockquote><figure class="kg-card kg-image-card kg-card-hascaption"><img src="https://media.tenor.com/4CX-pXSoV18AAAAC/oh-really.gif" class="kg-image" alt loading="lazy" width="498" height="370"><figcaption>10,000 Years!</figcaption></figure><p>An example of an enrollment token:</p><pre><code class="language-json">{
  "name": string,
  "value": string,
  "duration": string,
  "expirationTimestamp": string,
  "policyName": string,
  "additionalData": string,
  "qrCode": string,
  "oneTimeOnly": boolean,
  "user": {
    object (User)
  },
  "allowPersonalUsage": enum (AllowPersonalUsage)
}</code></pre><p><strong>Launch an app during setup</strong></p><p>Within policies, it's possible to designate one application for Android Device Policy to initiate during the setup of a device or work profile. For instance, you can have your own T&amp;Cs app that users must accept the Terms and Conditions as part of the setup procedure. To indicate that the process has been completed and to allow Android Device Policy to finish the provisioning of the device or work profile, the app must return a RESULT_OK signal.</p><p>To successfully launch an app during the setup, the following steps must be adhered to:</p><blockquote>The app's 'installType' is set to 'REQUIRED_FOR_SETUP.' If the app fails to install or launch on the device, the provisioning process will be unsuccessful.</blockquote><figure class="kg-card kg-image-card kg-card-hascaption"><img src="__GHOST_URL__/content/images/2023/08/image-12.png" class="kg-image" alt loading="lazy" width="1318" height="263" srcset="__GHOST_URL__/content/images/size/w600/2023/08/image-12.png 600w, __GHOST_URL__/content/images/size/w1000/2023/08/image-12.png 1000w, __GHOST_URL__/content/images/2023/08/image-12.png 1318w" sizes="(min-width: 720px) 720px"><figcaption>Launch an app during setup</figcaption></figure><pre><code class="language-json">{
   "applications":[
      {
         "packageName":"com.my.T&amp;C.",
         "installType":"REQUIRED_FOR_SETUP"
      }
   ]
}</code></pre><pre><code class="language-json">{
   "setupActions":[
      {
         "title":{
            "defaultMessage":"T&amp;C App"
         },
         "description":{
            "defaultMessage":"Please accept T&amp;Cs to proceed."
         },
         "launchApp":{
            "packageName":"com.my.T&amp;C."
         }
      }
   ]
}</code></pre><p>After the app returns <code>RESULT_OK</code>, Android Device Policy will complete any remaining steps required to provision the device or work profile.</p><hr><h2 id="conclusion">Conclusion</h2><p>Till now, we've explored the fundamental principles behind device provisioning and the role of Android Device Policy in managing devices within an enterprise environment. </p><p>As we continue to unravel the complexities of Android Enterprise Management, the upcoming part of our series promises to delve deeper into a crucial aspect of device management: <strong>Enrollment Methods for Android Devices in Intune</strong>. Stay tuned as we guide you through various enrollment options, practical strategies, and insights that can transform the way your organization manages its Android devices.</p><p>Thank you for following along, and I look forward to welcoming you back for the next exciting installment in our comprehensive guide to <strong>Android Enterprise Management with Microsoft Intune.</strong></p><hr>