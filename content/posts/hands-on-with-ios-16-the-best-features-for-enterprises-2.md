---
title: "Hands-On With iOS 16 - The Best Features For Enterprises"
date: 2022-09-23T14:54:00"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>iOS 16 is two weeks old, and iPad OS 16 is expected to be released in the next few weeks. There are so many new MDM functionality coming to the new iOS many of them are pretty cool features. They will change the way for iOS device management.</p>



<p>I will walk you through some of these new features in this blog post with a few demos.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Sign in with Apple at Work &amp; School</strong></h4>



<p>Sign-in with Apple is a new thing that allows a fast and easy way for users to sign in to apps with their Apple ID. Users can create an account within the app with a simple tap.</p>



<p>Apple has now extended the capabilities of &#8220;Sign-in with Apple ID&#8221; to support Managed Apple IDs, i.e., it allows the same benefits for a fast and easy sign-in experience with Managed Apple ID.</p>



<p>For example, the user just downloaded JIRA to his iPhone and has the following sign-in options.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_200434000_iOS.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="585" height="1015"/></figure>



<p>To use Sign in with Apple, the user can tap Continue with Apple and will see the welcome screen for Sign in with Apple.</p>



<p>Now, with the new settings, users will see the welcome screen for Sign in with Apple at Work &amp; School if they use a Managed Apple ID.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_201824000_iOS.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="290" height="590"/></figure>



<p>You can notice a difference in the welcome screen.&nbsp;</p>



<p>Generally, when the users use their Apple ID with Sign in with Apple, they see the account creation screen where they may edit their name and choose whether to share or hide their email.</p>



<p>But now, with this new feature, the organizational context will be used, which forces the app to understand that the user is logging in with corporate (managed applied id), and accordingly level of access will change.</p>



<p>So this is an example, the app will provide access control using the name and email shared with their app when using Sign in with Apple at Work &amp; School. It also means that when a user uses Sign in with Apple at Work &amp; School, the name and email fields will always be accessible.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Support for OAuth</strong></h4>



<p>Both iOS 16 and iPadOS 16 have added support for OAuth 2.0. This allows MDM solutions to implement solutions that support OAuth for user authentication. Enrollment SSO will also work with any SSO technology, including OAuth 2.0.&nbsp;</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Corp v/s Personal Data Separation</strong></h4>



<p>When users sign in with their Managed Apple ID on iOS/iPad OS 16 or higher devices, the Calendar and Reminder apps will create a second database containing all of the events and metadata for the organization’s calendars. This will allow full data separation for devices enrolled with User Enrollment to secure organizational data.&nbsp;</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>New Software Update Features</strong></h4>



<p>With the new OS, Apple has introduced a new mechanism to ship security fixes to users more frequently.&nbsp;</p>



<p>If we want to configure it manually, then a new priority key can be passed when sending the OS update. Sending this command with a “High” priority key will be similar to a user-initiated update. This is only supported for minor OS updates.&nbsp;</p>



<p>This new mechanism is called&nbsp;<strong>Rapid Security Response</strong>.</p>



<p>Rapid Security Responses don’t adhere to the managed software update delay; however, because they apply only to the latest minor operating system version if that minor operating system update is delayed, the response is also effectively delayed.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/thumbnail_image001-dfdfd7d.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="290" height="590"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Apple Configurator for iPhone</strong></h4>



<p>This is the best feature of iOS 16.&nbsp;</p>



<p>In iOS 16 or iPadOS 16, Administrators, Site Managers (Apple School Manager only), and Device Enrollment Managers can add iPhone and iPad devices to their Apple School Manager, Apple Business Manager, or Apple Business Essentials organization with Apple Configurator for iPhone. To do so, the Setup Assistant must be at the Choose a Wi-Fi Network pane. This can be very useful for users at remote locations where an organization cannot ship hardware.</p>



<p>The process is super simple:</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/1-d9d20d9.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="516" height="772"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/3-6d243c9.jpg/:/rs=w:1280" alt="" width="516" height="917"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/2.jpg/:/rs=w:1280" alt="" width="531" height="774"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_202439000_iOS-0.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="540" height="960"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_202439000_iOS-1.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="540" height="960"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_202303000_iOS-3.jpg/:/rs=w:1280" alt="" width="540" height="960"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_202439000_iOS-2.jpg/:/rs=w:1280" alt="" width="540" height="960"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_202618587_iOS.jpg/:/rs=w:1280" alt="" width="542" height="407"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_202719196_iOS.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="547" height="410"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Identity management&nbsp;</strong></h4>



<p>Apple Business Manager now supports the federation of Managed Apple IDs with Google Workspace. “Apple Business Manager and Apple School Manager will also support the ability to configure an “allow list” of apps that Managed Apple IDs can be used to sign in to.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Screenshot%202022-09-22%20235738.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="233"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Enrollment Single Sign-On&nbsp;</strong></h4>



<p>Enrollment SSO is designed to make the User Enrollment flow faster and easier by reducing the number of sign-ins required during enrollment into MDM. This is accomplished by installing an identity app, then using it to handle repeated authentication during—and after—the enrollment process.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_220352000_iOS.png/:/rs=w:1280" alt="" width="488" height="651"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_220056000_iOS.png/:/rs=w:1280" alt="" width="490" height="653"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_220131000_iOS.png/:/rs=w:1280" alt="" width="489" height="652"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_220117000_iOS.png/:/rs=w:1280" alt="" width="496" height="661"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_220341000_iOS.png/:/rs=w:1280" alt="" width="496" height="661"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_220406000_iOS-b38008f.png/:/rs=w:1280" alt="" width="492" height="656"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_220359000_iOS.png/:/rs=w:1280" alt="" width="492" height="656"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_220500000_iOS.png/:/rs=w:1280" alt="" width="492" height="656"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/20220922_220524000_iOS.png/:/rs=w:1280" alt="" width="492" height="656"/></figure>



<p>Once the user verifies with managed apple id, the enrollment will be complete.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Managed Device Attestation&nbsp;</strong></h4>



<p>Managed Device Attestation uses the&nbsp;<strong>Secure Enclave</strong>&nbsp;and cryptographic attestations to secure communications by managed devices when connecting to services such as MDM, VPN, and 802.1X.&nbsp;</p>



<p>The MDM server issues a device information query for device information attestation and specifies some new keys. The device obtains an attestation from Apple’s servers and returns it to the MDM server. Then the MDM server evaluates the attestation.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Default Domains &amp; Remote Authentication</strong></h4>



<p>Save your users time by using the ManagedAppleIDDefaultDomains key so users will see a suggestion quickly to authenticate. After entering the user name portion of a Managed Apple ID, users can select their account’s domain from a list on the QuickType keyboard.</p>



<p>And, with the new iPadOS 16, the shared iPad will, by default, use the local passcode for existing users on the device, requiring no network connection. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Managing Network Traffic&nbsp;</strong></h4>



<p>With the new OS, Apple has also expanded DNS Proxy and Web Content Filter profiles to BYOD devices, which is quite similar to per-app VPN. These profiles can only be installed via MDM. All existing apps that require DNS Proxies or Web Content Filters will still work. However, you cannot mix system-wide and per-app proxies.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>There are many more interesting features in the new Apple Operating System, but it won&#8217;t be possible to cover them all in this post. There will be a few more posts covering these features in much more detail. Till then, be&nbsp;<strong>#mempowered</strong>&nbsp;&amp; enjoy&nbsp;<strong>#membeer</strong>. Stay In(tuned).</p>



<p></p>
<!--kg-card-end: html-->