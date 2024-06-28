---
title: "It's Time To Move To Modern Authentication!"
date: 2022-08-19T23:21:00"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>In about 42 days, Microsoft will disable the ability to use basic authentication for Outlook, Exchange Web Services, POP, IMAP, Remote PS &amp; EAS protocols for Exchange Online. This means you&nbsp;<strong>have&nbsp;</strong>to change your apps &amp; scripts to use OAuth (modern authentication). It will also impact mobile devices where users are using legacy authentication (EWS) is used for mail sync. If you have configured the native mail client on your managed Apple devices to use basic authentication, continue reading further to move to modern auth using Intune easily.&nbsp;</p>



<h4><strong>What is Basic Authentication &amp; Why is Microsoft disabling it?</strong></h4>



<p>Basic authentication means the application&nbsp;<strong>sends user names and passwords over the Internet as text</strong>&nbsp;<strong>that is Base64 encoded, and the target server is not authenticated.&nbsp;</strong>In most cases, these credentials are also stored locally on the device/servers/systems. It increases the risk of compromised accounts as MFA is hard to be forced when basic authentication is enabled. &nbsp;</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Background</strong></h4>



<p>As you might know, Apple has supported OAuth on clients in iOS/iPad OS &amp; macOS devices for many years, so if you are configuring a &#8220;<strong>new&#8221;&nbsp;</strong>Exchange Online account in the&nbsp;<strong>native mail client app</strong>&nbsp;on these devices, then it should use the&nbsp;<strong>modern auth</strong>. However, it is important to note that the Exchange Online account will use modern auth only if it was added to the device after OAuth support was added to the mail app. For iOS/iPad OS, Apple confirmed to include it as a part of the iOS 15.6 upgrade, which means if your devices are on a lower version than iOS 15.6, you will have to use the MDM solution to push this configuration for a native mail client.&nbsp;</p>



<p><strong>Catch-22: On a device with old iOS, ff modern auth is not configured or pushed from MDM:&nbsp;</strong>When you restore a backup from an old device to a new one or use the built-in migration process to move your data and settings to a new one, your mail settings might still be configured to use Basic auth.</p>



<h4><strong>Solution</strong></h4>



<p><em>Please note: If you are blocking basic authentication using Azure AD Conditional Access, then you don&#8217;t need to worry because the clients on your devices using EAS connections will use modern authentication.</em></p>



<p>However, if you currently allow your users to use basic authentication for EAS, then it&#8217;s time you should start using modern authentication!</p>



<p>The easiest way to find these details for users still using basic auth is to look into your Azure AD sign-in logs and filter it for&nbsp;<strong>Client-Apps -&gt; Exchange ActiveSync,&nbsp;</strong>and here you will get details of devices on which basic auth is being used.&nbsp;</p>



<p>Microsoft &amp; Apple helps you to do a smooth transition to OAuth for thousands of users in your organization by simply using the Azure AD service principal (enterprise app) called &#8220;<strong>iOS accounts</strong>.&#8221; With the help of Graph APIs, Apple uses this service principal to retrieve account information and access user mailboxes with EAS. As the device is managed and already has the user&#8217;s credentials, this ROPC workflow allows the application to sign in by directly handling their password, giving you an added advantage.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-14%20203459-0001.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="319"/></figure>



<p><em>Please ensure that you grant consent to allow the app to use the three Graph permissions it needs on behalf of the organization else, users will have to consent while they configure the native mail client.</em></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>MDM as an Exception</strong></h4>



<p>If you are using Intune or any other MDM solution to configure the native mail client on your iOS/iPad OS or macOS devices, then this enterprise app&nbsp;<strong>will NOT update</strong>&nbsp;the mail app profile on your managed devices.</p>



<p><strong>A. Update existing email profiles to use OAuth</strong>:</p>



<p>Follow the steps below to&nbsp;<strong>update the existing email profile</strong>&nbsp;for your iOS and iPadOS devices to&nbsp;<strong>switch to</strong>&nbsp;modern authentication.</p>



<p>1. Sign in to the&nbsp;<a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank"><u>Microsoft Endpoint Manager admin center</u></a>.</p>



<p>2. Select&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>iOS/iPad OS Devcies &gt;</strong>&nbsp;<strong>Configuration profiles</strong></p>



<p>3. Search for the email profile that you have configured &amp; pushed to the devices.</p>



<p>4. Scroll down to&nbsp;<strong>Configuration Settings</strong>&nbsp;and click&nbsp;<strong>Edit</strong>.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-18%20114242.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="314"/></figure>



<p>5. Toggle for OAuth to &#8220;Enable&#8221; to force the connection to switch to Modern&nbsp;Authentication.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-18%20122244.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="310"/></figure>



<p>6. Click &#8220;Review &amp; Save&#8221; and then Save on the next page to save the configurations.</p>



<p>The following steps show you the sequence of changes on the user&#8217;s end &#8211;&nbsp;</p>



<p>&#8211; &nbsp;As soon as the iOS device sync with Intune and gets the new policy, the user will get a pop-up message on the device screen to&nbsp;<em><strong>Enter the password for<br>&nbsp;Exchange Account.</strong></em></p>



<figure class="wp-block-image"><img decoding="async" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-18%20123759.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt=""/></figure>



<p>&#8211; Click&nbsp;<strong>Edit Settings</strong><em><strong>,&nbsp;</strong></em>which will automatically take you to the iPad Settings, then into the configured email account. Where it will open the web-based modern authentication login. Enter your password and press&nbsp;<strong>Sign in</strong><em><strong>.</strong></em></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-18%20124724.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="365" height="271"/></figure>



<p>&#8211; &nbsp;&nbsp;It will then automatically verify everything and step through a couple of screens before completing it.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-19%20124057.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="318" height="424"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-19%20161857.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="602" height="120"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>B. Create an email device profile for iOS/iPadOS</strong>:</p>



<p>Follow the steps below to automatically configure email device profiles on your end user&#8217;s device and let them access company email on their devices without any required setup on their part. You can also use these pre-configured email profiles to evaluate device compliance and Conditional Access (CA) to block any non-compliant devices from accessing corporate email.</p>



<p><strong>P.S: You have forced &#8220;</strong><em><strong>Require</strong></em><strong>&#8221; for &#8220;</strong><em><strong>Unable to set up email on the device</strong></em><strong>&#8221; in the Compliance policy if you want to use it with Conditional Access.</strong></p>



<p>1. Sign in to the&nbsp;<a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank">Microsoft Endpoint Manager admin center</a>.</p>



<p>2. Select and go to&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>iOS/iPad OS Devcies &gt;</strong>&nbsp;<strong>Configuration profiles &gt;</strong>&nbsp;<strong>Create profile</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-19%20175004.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="410" height="258"/></figure>



<p>3. Select&nbsp;<strong>Email&nbsp;</strong>as&nbsp;<strong>Profile&nbsp;</strong>from the&nbsp;<strong>Templates&nbsp;</strong>menu.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-19%20175400.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="350"/></figure>



<p>4. &nbsp;In&nbsp;<strong>Basics</strong>, enter the&nbsp;<strong>Name&nbsp;</strong>&amp;&nbsp;<strong>Description&nbsp;</strong>for the profile and click&nbsp;<strong>Next.</strong></p>



<p>5. In&nbsp;the <strong>Configuration settings page,&nbsp;</strong>enter the required configurations and click&nbsp;<strong>Create:</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-19%20175812.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="407" height="452"/></figure>



<p>6. On the next page,&nbsp;<strong>Assign&nbsp;</strong>the policy to the required groups.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>Awesome&#8230;Job done and your iOS devices are now using modern authentication for exchange mail services.&nbsp;</p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="220" height="167" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/ntc-cheers-1.gif?resize=220%2C167&#038;ssl=1" alt="" class="wp-image-372" data-recalc-dims="1"/></figure>
<!--kg-card-end: html-->