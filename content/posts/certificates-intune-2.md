---
title: "Certificates & Intune"
date: 2022-07-07T13:10:00"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>When planning to deploy certificates with Intune, there will be two obvious questions that will pop up:</p>



<ul class="is-style-grigora-list-style-3"><li>Do I need to deploy a user certificate or a device certificate?</li><li>What can I do with these certificates?</li></ul>



<p>The most common scenarios include network authentication using a device or user certificate. Such as authentication to the VPN, corporate Wi-Fi or corporate LAN using the device or user certificate. You can also use these certificates for signing &amp; encrypting emails.</p>



<p><span style="text-decoration: underline;"><em><strong>Some Basics first..</strong></em>.</span></p>



<p>Access any application has to go through two steps-&nbsp;</p>



<ul><li><strong>Authentication&nbsp;</strong>&#8211; The user’s authenticity is checked</li><li><strong>Authorization</strong>&nbsp;&#8211; &nbsp;The user is subjected to some conditions, depending on which a decision is made on whether access should be given or denied. &nbsp;</li></ul>



<p>Think of those conventional times when users were required to enter their credentials to authenticate to corporate connections or resources. The concept of using certificate-based authentication makes it more secure and seamless as users are no longer required to provide their credentials every time to authenticate.</p>



<p>Using Intune, you can deploy two types of certificates, i.e.,&nbsp;<em><strong><span style="text-decoration: underline;">Simple Certificate Enrollment Protocol (SCEP) and Public Key Cryptography Standards (PKCS).&nbsp;</span></strong></em></p>



<p><strong>SCEP or PKCS ???</strong>&nbsp;Both have their own advantages and disadvantages, so please discuss this thoroughly within your teams/organization to decide which one to configure and deploy.&nbsp;</p>



<p>However, there are certain pre-requisites before you deploy the SCEP or PKCS certificate(s); you should have:</p>



<ul class="is-style-grigora-list-style-3"><li><strong>Certification Authority</strong>&nbsp;&#8211; &nbsp;It can be a Microsoft CA or a third-party CA.</li><li><strong>On-premises infrastructure</strong>&nbsp;&#8211; Depending on what type of certificate (PKCS, SCEP, or Imported PKCS) you will deploy.</li><li><strong>Trusted root certificate</strong>&nbsp;&#8211; Trusted certificate profile in Intune</li></ul>



<p>Once a trusted root certificate is deployed, you can deploy certificate profiles to provide users and devices with certificates for authentication.&nbsp;</p>



<h4><strong>Supported platforms for deploying certificate profiles</strong></h4>



<ol class="is-style-grigora-list-style-3"><li>&nbsp;Android Device Administrator (Legacy)</li><li>&nbsp;Android Enterprise &#8211; Fully Managed (Device Owner)&nbsp;</li><li>&nbsp;Android Enterprise &#8211; Dedicated (Device Owner)&nbsp;</li><li>&nbsp;Android Enterprise &#8211; Corporate-Owned Work Profile&nbsp;</li><li>&nbsp;Android Enterprise &#8211; Personally-Owned Work Profile&nbsp;</li><li>&nbsp;Android (AOSP)&nbsp;</li><li>macOS</li><li>&nbsp;iOS/iPadOS</li><li>Windows 10/11&nbsp;</li></ol>
<!--kg-card-end: html-->