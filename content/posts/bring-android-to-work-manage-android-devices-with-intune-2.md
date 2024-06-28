---
title: "Bring Android To Work - Manage Android Devices With Intune"
date: 2022-07-27T20:57:00"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<p>Intune allows you to enroll both personal and organization-owned devices with the following options: </p>



<ul><li><strong>BYOD</strong>: Android Enterprise personally owned devices with a work profile</li><li>Android Enterprise corporate-owned dedicated devices (<strong>COSU</strong>)</li><li>Android Enterprise corporate owned fully managed (<strong>COBO</strong>)</li><li>Android Enterprise corporate-owned work profile (<strong>COPE</strong>)</li><li>Android Open Source Project (preview) (<strong>AOSP</strong>)</li><li>Android device administrator (<strong>DA</strong>)</li></ul>



<p>There is an excellent Visio guide from MS that can be downloaded <a href="https://download.microsoft.com/download/e/6/2/e6233fdd-a956-4f77-93a5-1aa254ee2917/msft-intune-enrollment-options.pdf" rel="noreferrer noopener" target="_blank">here</a>.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>Before enrolling in the Android devices, you must connect your Intune tenant account to your Managed Google Play account, also called Enterprise Google Play Store. Once you connect your tenant to Google Play, the below four Android Enterprise apps will be automatically added to “Android Apps” in your Intune portal:</p>



<ul><li>Microsoft Intune</li><li>Microsoft Authenticator</li><li>Intune Company Portal</li><li>Managed Home Screen</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Pre-requisites:  Connect your Intune tenant to your Managed Google Play account</strong></h4>



<p>1. <a rel="noreferrer noopener" href="https://endpoint.microsoft.com/" target="_blank">MEM Admin Center</a>, navigate to <strong>Devices </strong>> <strong>Android </strong>> <strong>Android Enrollment > Managed Google Play</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-27%20163259.png/:/rs=w:1280" alt="" width="640" height="260"/></figure>



<p>2. Click on <strong>I agree</strong> and then on <strong>Launch Google to connect </strong>to launch the Managed Google Play website. It will open in a new window.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-27%20163537.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="249"/></figure>



<p>3.  Click <strong>Get started</strong> </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-27%20163601.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="422"/></figure>



<p>4. Enter your enterprise account details and click <strong>Next. (</strong> <em><strong>(Please use a corporate id as</strong></em><em><strong> </strong></em><em><strong>preferably, it should be a service account. Avoid using your personal Gmail ID.)</strong></em> </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-27%20164219.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="245"/></figure>



<p>5.  The next step is <strong>optional</strong>; you can proceed to set up the Managed Google Play by agreeing to Google Play T&Cs.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-27%20164431.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="317"/></figure>



<p>6.  Click <strong>Complete Registration, and the connection is made 👍</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-27%20164458.png/:/rs=w:1280" alt="" width="640" height="247"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-27%20165348.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="307"/></figure>



<p>7. Now, you will notice that all the Enrollment Profile options are enabled for Android Enrollment.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-27%20165450.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="315"/></figure>

<!--kg-card-end: html-->
