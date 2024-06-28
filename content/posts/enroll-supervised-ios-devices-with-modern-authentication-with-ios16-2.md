---
title: "Enroll Supervised iOS Devices With Modern Authentication With iOS16"
date: 2022-09-13T15:22:00"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>Apple will remove the Company Portal authentication method for all new and existing iOS/iPadOS ADE enrollment profiles in November 2022. This will include removing the Run Company Portal in Single App Mode until authentication with Comp Portal. in this post, and I will help you switch to modern authentication in enrollment profiles on the latest iOS build &#8211;&nbsp;<strong>iOS16.</strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>Why the change:</h4>



<p><strong>Impact of this change:</strong>&nbsp;If you are currently using a legacy authentication method wherein your users are required to authenticate using the comp portal VPP token, then the devices will not be able to re-enroll until you switch the enrollment authentication method to Setup Assistant with modern authentication.&nbsp;</p>



<p><strong>Plan for Change:&nbsp;</strong>The new enrollment profile will have modern authentication configured so that the users will not get a “<strong>Guided Access App Unavailable</strong>” message. The authentication will occur before the user presses the home screen. This will also reduce the overall time taken to enroll a device.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Assumption</strong></h4>



<p>In this post, I assume you are using the legacy authentication method. During the enrolment process, Company Portal runs in a single App Mode with a “<strong>Guided Access App Unavailable</strong>” message until authentication for ADE is completed.&nbsp;</p>



<h4><strong>Prerequisites</strong>&nbsp;</h4>



<ul><li>Devices purchased in Apple&#8217;s ADE</li><li>Mobile device management (MDM) authority</li><li>An Apple MDM push certificate</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Device Enrollment in Intune</strong></h4>



<p>Before you start to enroll iOS/iPadOS devices with ADE, there are a series of steps that you need to follow.</p>



<ol><li>Create &amp; Upload Apple MDM Push Certificate</li><li>Create &amp; Upload the Apple Automated Device Enrollment token</li><li>Assign devices to the Apple token (MDM server)</li><li>Create an Apple enrollment profile</li></ol>



<p>A few months back, I wrote a post on&nbsp;<a href="https://intuneirl.com/2022/07/company-owned-ios-device-automated-device-enrollment-part-i/" target="_blank" rel="noreferrer noopener"><u><strong>automated device enrollment for corporate-owned devices</strong></u></a>, detailing the first three steps. Now let&#8217;s complete the series by creating an enrollment profile and enrolling an iPhone in Intune with brand new iOS 16.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Create an Apple Enrollment Profile</strong></h4>



<p>The device enrollment profile helps you configure the setting you would like to apply/configure on devices during the enrollment phase. Follow the steps to create an enrollment profile:</p>



<p>1. From the <a rel="noreferrer noopener" href="https://endpoint.microsoft.com/" target="_blank"><u>Microsoft Endpoint Manager</u></a> portal, navigate to <strong>Devices</strong> > <strong>iOS/iPadOS</strong> ><strong> iOS/iPadOS enrollment</strong> > <strong>Enrollment program tokens</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/1-bc55a33.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="346"/></figure>



<p>2. Select a token, and then select&nbsp;<strong>Profiles</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/2-7eb43ed.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="266"/></figure>



<p>3. Select&nbsp;<strong>Create profile</strong>&nbsp;&gt;&nbsp;<strong>iOS/iPadOS or&nbsp;</strong>select the existing profile to modify it<strong>.&nbsp;</strong></p>



<p><em>(If you are modifying an existing profile, then you can skip all steps except step 6)</em></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/2-199394f.png/:/rs=w:1280" alt="" width="640" height="266"/></figure>



<p>4. If you are creating a new profile, then Provide a&nbsp;<strong>Name</strong>&nbsp;and&nbsp;<strong>Description</strong>&nbsp;for the profile<br>&nbsp;&nbsp;&nbsp;(These details will not be visible to users) and click&nbsp;<strong>Next</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/3-e9a85a5.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="662" height="386"/></figure>



<p>5. In the management settings page, select &#8220;<strong>Enroll with User Affinity&#8221; </strong>as we will use this profile to enroll devices associated with users.</p>



<p>6. As we selected <strong>Enroll with User Affinity</strong> for the <strong>User Affinity</strong> field, we can choose the authentication methods to use when authenticating users.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/5-18b4c8a.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="184"/></figure>



<p>Let&#8217;s check both options:</p>



<ul><li><strong>Company Portal</strong>: You can use the Company Portal app to authenticate users if you&nbsp;want to use multi-factor authentication, prompt users to change their&nbsp;passwords after first signing in, or reset their expired passwords&nbsp;during enrollment.</li><li><strong>Setup Assistant with modern authentication:&nbsp;</strong>This authentication method has two&nbsp;major differences. First, only iOS/iPadOS 13.0 and higher devices are eligible for this&nbsp;method. Second, the user can start using the device immediately&nbsp;rather than wait until the company portal installs on the device.</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Annotation%202022-09-13%20094757.png/:/rs=w:1280" alt="" width="590" height="133"/></figure>



<p>Irrespective of which option you choose, the Company Portal app will be installed without user interaction; as such, it must be pushed as a &#8220;<strong>mandatory app</strong>&#8220;.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-2833f22.png/:/rs=w:1280" alt="" width="640" height="365"/></figure>



<p>7. For&nbsp;<strong>locked enrollment,&nbsp;</strong>I would recommend using &#8220;<strong>Yes</strong>&#8221; for supervised devices, as it&nbsp;disables iOS/iPadOS settings for removing the management profile from the device. The&nbsp;only option to remove the profile is to wipe it.</p>



<p>8. If you allow users to sync their devices with any computer, select &#8220;<strong>Allow All</strong>&#8221; from&nbsp;Sync with the Computer option.</p>



<p>9. Configure naming template or cellular data if required and click&nbsp;<strong>Next&nbsp;</strong>to proceed.</p>



<p>10. On the <strong>Setup Assistant</strong> page, update settings for &#8220;Department&#8221; &amp; &#8220;Department Phone Number&#8221;.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Annotation%202022-09-12%20231314.png/:/rs=w:1280" alt="" width="502" height="124"/></figure>



<p>11. Next, you can toggle the options to modify the Setup Assistant screens on the device&nbsp;during user setup.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-cc56cfd.png/:/rs=w:1280" alt="" width="640" height="404"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>&nbsp;<strong>Sync managed devices</strong></p>



<p>&nbsp;Now that Intune has permission to manage your devices, we have to synchronize Intune with Apple to see your managed devices in Intune portal.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/10.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="324"/></figure>



<p>A delta sync runs automatically every 12 hours; however, we can also trigger a delta sync by selecting the&nbsp;<strong>Sync</strong>&nbsp;button (no more than once every 15 minutes). All sync requests are given 15 minutes to finish. The&nbsp;<strong>Sync</strong>&nbsp;button is disabled until a sync is completed.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Assign an enrollment profile to devices</strong></h4>



<p>(If you are modifying an existing profile or if you do not want to add new devices to the profile, then you can skip this step)</p>



<p>If you have multiple enrollment profiles or do not have a default profile set, you will need to assign an enrollment program profile to devices before they can be enrolled.</p>



<ol><li>In Intune portal, navigate to&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>iOS/iPadOS</strong>&nbsp;&gt;&nbsp;<strong>iOS/iPadOS enrollment</strong>&nbsp;&gt;&nbsp;<strong>Enrollment Program Tokens</strong>. Select a token in the list.</li><li>Select&nbsp;<strong>Devices</strong>. Select devices in the list, and then select&nbsp;<strong>Assign profile</strong>.</li><li>Choose a device profile from the Assign profile, then select&nbsp;<strong>Assign</strong>.</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>We have everything in place now to distribute devices to users. However, before that, please take note of the following:</p>



<ul><li>User affinity devices require each user to be assigned an Intune license.</li><li>An activated device needs to be wiped before it can enroll properly using ADE in<br>&nbsp;Intune.&nbsp;</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>End User Experience</strong></h4>



<p>Let&#8217;s have a look at device enrollment flow with both authentication methods.</p>



<p><strong>1. Company Portal Authentication (old method)</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Collage1.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="640"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Collage2.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="640"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>2. Setup Assistant with Modern Authentication (Recommended):</strong></p>



<p>Notice the difference here that authentication with Azure Active Directory (Azure AD) happens in out-of-box experience (OOBE) during enrollment with Setup Assistant before users access the home screen.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Collage3.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="640"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Collage4.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="640"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Collage4%20(1).png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="640"/></figure>
<!--kg-card-end: html-->