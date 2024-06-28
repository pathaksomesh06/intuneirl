---
title: "Bring Your Own Devices (BYOD) - Configure It The Right Way!"
date: 2022-10-12T00:31:40"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<p><a href="https://intuneirl.com/2022/10/bring-your-own-device-plan-configure-and-enrol-your-personal-devices-securely/" target="_blank" rel="noreferrer noopener">Earlier</a>, we discussed the pros and cons of having personal devices enrolled in MDM and the best practices to avoid any possible data leakage. In this post, I will help you with configuring your Intune tenant to allow enrollment of personal devices and will also make it an automated process.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Overview</h2>



<p>We all know that there are multiple options available in Intune for enrolling and managing Android devices, but for this post, I will stick to “<strong>Personally-Owned Devices with Work Profile</strong>“.</p>



<p>Personally-owned devices with work profiles are used to manage corporate data and apps on user-owned “<strong>personal” </strong>Android devices. By default, enrollment of personally-owned work profile devices is enabled, and no specific configuration is required. However, I <span style="text-decoration: underline;"><em>personally believe</em></span> that if you do not have all security measures like MAM, Zero-Trust and MFA, then it should be allowed in a controlled way.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Sometimes Restrictions Are Helpful</h2>



<p>Don’t use the Bing-Bang approach if you are planning for the BYOD rollout or starting with it. Thankfully, Microsoft allows you to restrict enrollment based on device attributes. When restrictions are applied, users on restricted devices are blocked from enrolling their devices in Microsoft Intune. </p>



<p>For BYOD, you need to use “<strong><span style="text-decoration: underline;">Device platform restrictions</span></strong>” to allow or block devices based on platforms, versions, and management types.</p>



<p>You can apply this restriction to devices running:</p>



<ul><li>Android device administrator</li><li>Android Enterprise work profile</li><li>iOS/iPadOS</li><li>macOS</li><li>Windows 10/11</li></ul>



<p>You can further enforce restrictions based on these platforms’ maximum/minimum OS versions. To configure the device platform restriction policy, log in to your Microsoft Endpoint Manager admin center and navigate to <strong>Devices</strong> > <strong>Enroll devices</strong> > <strong>Enrollment device platform restrictions</strong> and select the required platform and then <strong>Create restriction</strong>.</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-12.png?resize=750%2C395&ssl=1" alt="" class="wp-image-490" width="750" height="395" srcset="https://irlimages.blob.core.windows.net/2022-10/image-12.png?resize=1024%2C539&ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-12.png?resize=300%2C158&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-12.png?resize=768%2C404&ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-12.png?resize=1536%2C808&ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-10/image-12.png?w=1599&ssl=1 1599w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>Provide the name and description of the restriction.</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-13.png?resize=571%2C287&ssl=1" alt="" class="wp-image-491" width="571" height="287" srcset="https://irlimages.blob.core.windows.net/2022-10/image-13.png?resize=1024%2C514&ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-13.png?resize=300%2C151&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-13.png?resize=768%2C386&ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-13.png?w=1101&ssl=1 1101w" sizes="(max-width: 571px) 100vw, 571px" data-recalc-dims="1" /></figure>



<p>Configure the restrictions for the selected platform based on the requirement:</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-14.png?resize=750%2C232&ssl=1" alt="" class="wp-image-492" width="750" height="232" srcset="https://irlimages.blob.core.windows.net/2022-10/image-14.png?resize=1024%2C317&ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-14.png?resize=300%2C93&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-14.png?resize=768%2C237&ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-14.png?resize=1536%2C475&ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-10/image-14.png?w=1588&ssl=1 1588w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>Similarly, the restrictions can be configured for the iOS family also:</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-15.png?resize=750%2C204&ssl=1" alt="" class="wp-image-493" width="750" height="204" srcset="https://irlimages.blob.core.windows.net/2022-10/image-15.png?resize=1024%2C279&ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-15.png?resize=300%2C82&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-15.png?resize=768%2C209&ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-15.png?resize=1536%2C419&ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-10/image-15.png?w=1592&ssl=1 1592w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption>On the <strong>Assignments</strong> page, <strong>Search </strong>and <strong>Add groups</strong> only allow users in these groups to enrol device their personal devices in Intune.</figcaption></figure>



<h2>Conditional Access</h2>



<p>The next layer of security is conditional access. </p>



<p><b><u>If you are not using Multi-Factor Authentication, make a U-Turn; configure and enable it </u></b><strong><span style="text-decoration: underline;">before proceeding further.!</span></strong></p>



<p>As MAM is the recommended approach with BYOD for securing corporate data on personal devices without Conditional Access, the corporate data remains vulnerable on users’ personal devices.</p>



<p>Conditional Access is a gatekeeper that checks for user identity, location, and device health and can allow or deny access based on conditions configured.</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-17.png?resize=750%2C142&ssl=1" alt="" class="wp-image-496" width="750" height="142" srcset="https://irlimages.blob.core.windows.net/2022-10/image-17.png?resize=1024%2C193&ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-17.png?resize=300%2C56&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-17.png?resize=768%2C144&ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-17.png?w=1106&ssl=1 1106w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>Configure device compliance policies to ensure the device meets your configuration and security requirements. The compliance policy evaluation will determine the device’s compliance status, which will be reported to Intune and Azure AD. Based on the CA & compliance policy evaluation, the device will be allowed or blocked access to your corporate data/resources.</p>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-16.png?resize=666%2C268&ssl=1" alt="" class="wp-image-494" width="666" height="268" srcset="https://irlimages.blob.core.windows.net/2022-10/image-16.png?w=888&ssl=1 888w, https://irlimages.blob.core.windows.net/2022-10/image-16.png?resize=300%2C121&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-16.png?resize=768%2C309&ssl=1 768w" sizes="(max-width: 666px) 100vw, 666px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Mobile Application Management</h2>



<p>The next layer for securing your corporate data on personal devices is – MAM. MAM allows you to manage and protect your organization’s data within an application. Many public store apps, such as the Microsoft Office apps, can be managed by Intune MAM.</p>



<p>There are two scenarios for which MAM can be used:</p>



<ul><li>Managed devices (MDM) – devices that are enrolled and managed through Intune</li><li>Un-enrolled devices – devices that are not enrolled in Intune </li></ul>



<p>The app management capabilities are well documented in <a href="http://MAM allows you to manage and protect your organization's data within an application. Many productivity apps, such as the Microsoft Office apps, can be managed by Intune MAM." target="_blank" rel="noreferrer noopener">MS Docs</a>.</p>



<p>With Intune, different app configuration policy channels are:</p>



<ol><li>Managed Devices – The entire device is managed by Intune</li><li>Managed Apps – For the app that has either integrated the Intune App SDK or has been wrapped using the Intune Wrapping Tool and supports App Protection Policies (APP).</li></ol>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-18.png?resize=401%2C159&ssl=1" alt="" class="wp-image-497" width="401" height="159" srcset="https://irlimages.blob.core.windows.net/2022-10/image-18.png?w=535&ssl=1 535w, https://irlimages.blob.core.windows.net/2022-10/image-18.png?resize=300%2C119&ssl=1 300w" sizes="(max-width: 401px) 100vw, 401px" data-recalc-dims="1" /></figure>



<p>To protect corporate data in your LoB apps with MAM policies, you must wrap them. I have written a post on wrapping the app. Pull up the article and <a href="https://intuneirl.com/2022/09/wrap-me-up/" target="_blank" rel="noreferrer noopener">wrap up your app</a>. </p>



<p>Now, the app protection policies can differ based on your requirement. This is what I have configured in my tenant:</p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="301" src="https://irlimages.blob.core.windows.net/2022-10/image-21.png?resize=750%2C301&ssl=1" alt="" class="wp-image-500" srcset="https://irlimages.blob.core.windows.net/2022-10/image-21.png?w=996&ssl=1 996w, https://irlimages.blob.core.windows.net/2022-10/image-21.png?resize=300%2C120&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-21.png?resize=768%2C308&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption>Define how you want to apply the policy</figcaption></figure>



<p></p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-19.png?resize=750%2C597&ssl=1" alt="" class="wp-image-498" width="750" height="597" srcset="https://irlimages.blob.core.windows.net/2022-10/image-19.png?resize=1024%2C814&ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-19.png?resize=300%2C238&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-19.png?resize=768%2C610&ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-19.png?w=1067&ssl=1 1067w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption>Configure Data Transfer restrictions</figcaption></figure>



<p><strong>Make sure you force encryption</strong> and restrict web content transfer with Edge as managed browser.</p>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-20.png?resize=750%2C346&ssl=1" alt="" class="wp-image-499" width="750" height="346" srcset="https://irlimages.blob.core.windows.net/2022-10/image-20.png?w=1021&ssl=1 1021w, https://irlimages.blob.core.windows.net/2022-10/image-20.png?resize=300%2C138&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-20.png?resize=768%2C354&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>TIP</h2>



<p>If you can push & enforce Microsoft Defender for Endpoint, combining it with CA, it will give you full-proof security. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Scope of Automation</h2>



<p>By now, everything is configured, and you are ready to roll out BYOD. If your organization doesn’t allow everyone to enrol their personal devices in Intune, you can automate the entire process. </p>



<p>It ensures no scope for human errors and automates the enrollment</p>



<p>You have multiple options to automate your BYOD rollout using the following:</p>



<ul><li>PowerApps </li></ul>



<ul><li>ServiceNow</li></ul>



<p>The flow could be somewhat like this:</p>



<p>You simply need to create a form where users requests to enrol their personal devices. </p>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-22.png?resize=447%2C567&ssl=1" alt="" class="wp-image-501" width="447" height="567" srcset="https://irlimages.blob.core.windows.net/2022-10/image-22.png?w=596&ssl=1 596w, https://irlimages.blob.core.windows.net/2022-10/image-22.png?resize=237%2C300&ssl=1 237w" sizes="(max-width: 447px) 100vw, 447px" data-recalc-dims="1" /><figcaption>Flow for automating BYOD in a controlled way</figcaption></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>In the next post, I will share the enrollment guides for Android & iOS and discuss “User Enrollment” and “Device Enrollment” features for iOS devices. Do share your feedback & suggestions.</p>

<!--kg-card-end: html-->
