---
title: "Bring Your Own Device - Plan, Configure and Securely Enrol Your Personal Devices"
date: 2022-10-09T20:21:34"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>This blog post describes the key concepts of the ‘&#8221;Bring Your Own Device&#8221; (BYOD) scenario and will also suggest measures you can use to mitigate the risks associated with allowing BYOD in your organization.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>BYOD</h2>



<p>Bring Your Own Device, commonly known as &#8220;<strong>BYOD</strong>&#8220;, allows employees to use their personally owned device(s) for work purposes that allow them to access corporate data/resources on their personal devices.</p>



<p>Few basic advantages of allowing BYOD in your organization are:</p>



<ul><li>Greater flexibility.</li><li>Increase mobility.</li><li>Improved efficiency and productivity.</li><li>Reduced cost for<span style="color: initial;"> hardware procurement.</span></li><li>No Training Required</li></ul>



<p>Like any other technology, it also has its own disadvantages:</p>



<ul id="block-fc377399-0602-45f5-b45c-6f6936314bc2"><li>High-Security Risk. </li><li>Difficult Data Retrieval. </li><li>Legal Issues.</li><li>Complex IT support</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Drivers for BYOD</h2>



<p>Before allowing your users/employees to enrol their personal devices in your MDM solution, determine what you want to achieve with BYOD. Think over what you want to achieve with it. Few things to consider:</p>



<ul><li>What and how will BYOD be used? Which business functions are you trying to achieve with this concept?</li><li>Who will be the primary users for it? Will you allow for the whole organization or only a subset of users?</li><li>What all platforms (Windows, macOS, Android, iOS) will you allow to enrol? And what will you restrict?</li><li>What will be the minimum OS/hardware requirements?</li><li>How flexible will you be in your security policies/configurations?</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Alternatives</h2>



<p>Before jumping on to BYOD, you must think and plan for the alternatives to allowing users to enrol their personal devices in your MDM solution.</p>



<p>The different platform provides different combinations for this. Android, for example, has the below four options to choose from for configuring &amp; planning your mobile landscape:</p>



<ul><li>Corporately Owned, fully Managed</li><li>Corporately Owned with work profile Enabled</li><li>Corporate Owned, dedicated device</li><li>Personally Owned with work profile</li></ul>



<p>At the same, the iOS family also have its own configurations to support this:</p>



<ul><li>User enrollment</li><li>Device enrollment</li><li>Determine based on the user device</li></ul>



<p>As it is said that ‘<strong>there is no one-size-fits-all</strong>, it is recommended that you carefully plan your BYOD solution by mixing both solutions, i.e. Corporate Owned + Personal Owned.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>List down the Why, What, Who &amp; How?</h2>



<p>Before configuring any policies or profiles in your MDM solution, write down all possible considerations for using BYOD:</p>



<ol><li>What platforms will be allowed?</li><li>What is the minimum standard for operating systems &amp; patches allowed before the device is enrolled?</li><li>What all security policies will be enforced? </li><li>What are the different options for enforcing security controls?</li><li>How restrictive and strict will the security policies be?</li><li>How will you enforce conditional access?</li><li>How will you protect sensitive data?</li><li>How will you protect user identities?</li><li>How will you differentiate corporate data from user data?</li><li>What will be the process for security breaches/incidents?</li><li>Who will use the BYOD services?</li><li>How will user education be driven?</li></ol>



<p>The list is endless, but you might have an overview of how you will plan the rollout of the BYOD service.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Security Controls</h2>



<p>Once you have ironed-out all the aspects for introducing BYOD for your users, the next most important step is too define security controls to ensure that there is no leakage of corporate data from end-user&#8217;s personal devices.</p>



<p>The security measures depend upon how you chose the deployment approach for BYOD. Few mandatory measures to enforce are:</p>



<ul><li>Enforce conditional access.</li><li>Force encryption of corporate data at-rest &amp; in-transit</li><li>Enforce Multi-Factor authentication control to access any corporate resource from personal devices.</li><li>Give access only to corporate resources that the user or group requires on their personal devices. </li><li>Do not expose entire environment/resources on personal devices.</li><li>Block legacy operating systems, browsers, authentication protocols, unpatched &amp; compromised devices.</li><li>Enforce user sign-in risk assessment</li><li>Block transfer of data to &amp; from remote desktop sessions &amp; work profiles on mobile devices.</li><li>Disable clipping data to dashboards in remote dashboard sessions.</li><li>Block sideloading of apps.</li><li>Enforce ‘Terms &amp; Conditions’ from MDM solution so that users cannot use corporate resources without accepting them.</li></ul>



<p>The components that make up the BYOD are illustrated below:</p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="309" src="https://irlimages.blob.core.windows.net/2022-10/image.png?resize=750%2C309&#038;ssl=1" alt="" class="wp-image-469" srcset="https://irlimages.blob.core.windows.net/2022-10/image.png?w=933&amp;ssl=1 933w, https://irlimages.blob.core.windows.net/2022-10/image.png?resize=300%2C123&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image.png?resize=768%2C316&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Use Intune to Secure Your Corp Data on BYOD</h2>



<p>The following components of Microsoft Intune should be used for configuring BYOD</p>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="422" src="https://irlimages.blob.core.windows.net/2022-10/image-1.png?resize=750%2C422&#038;ssl=1" alt="" class="wp-image-470" srcset="https://irlimages.blob.core.windows.net/2022-10/image-1.png?resize=1024%2C576&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-1.png?resize=300%2C169&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-1.png?resize=768%2C432&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-1.png?w=1280&amp;ssl=1 1280w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p><strong>Conditional Access</strong></p>



<p>An example for configuring CA for your BYOD is as below:</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-3.png?resize=750%2C398&#038;ssl=1" alt="" class="wp-image-472" width="750" height="398" srcset="https://irlimages.blob.core.windows.net/2022-10/image-3.png?resize=1024%2C544&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-3.png?resize=300%2C160&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-3.png?resize=768%2C408&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-3.png?resize=1536%2C817&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-10/image-3.png?w=1687&amp;ssl=1 1687w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p></p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-4.png?resize=750%2C319&#038;ssl=1" alt="" class="wp-image-473" width="750" height="319" srcset="https://irlimages.blob.core.windows.net/2022-10/image-4.png?resize=1024%2C436&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-4.png?resize=300%2C128&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-4.png?resize=768%2C327&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-4.png?resize=1536%2C654&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-10/image-4.png?w=1888&amp;ssl=1 1888w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p></p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-5.png?resize=750%2C330&#038;ssl=1" alt="" class="wp-image-474" width="750" height="330" srcset="https://irlimages.blob.core.windows.net/2022-10/image-5.png?resize=1024%2C450&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-5.png?resize=300%2C132&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-5.png?resize=768%2C337&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-5.png?resize=1536%2C675&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-10/image-5.png?w=1903&amp;ssl=1 1903w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p></p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-6.png?resize=750%2C391&#038;ssl=1" alt="" class="wp-image-475" width="750" height="391" srcset="https://irlimages.blob.core.windows.net/2022-10/image-6.png?resize=1024%2C533&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-6.png?resize=300%2C156&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-6.png?resize=768%2C400&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/image-6.png?resize=1536%2C800&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-10/image-6.png?w=1672&amp;ssl=1 1672w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>App Configuration Policies</strong></p>



<p>App protection policies are applied to your corporate apps/data enabling additional layers of security; an example:</p>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-9.png?resize=528%2C705&#038;ssl=1" alt="" class="wp-image-478" width="528" height="705" srcset="https://irlimages.blob.core.windows.net/2022-10/image-9.png?w=704&amp;ssl=1 704w, https://irlimages.blob.core.windows.net/2022-10/image-9.png?resize=225%2C300&amp;ssl=1 225w" sizes="(max-width: 528px) 100vw, 528px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-7.png?resize=523%2C381&#038;ssl=1" alt="" class="wp-image-476" width="523" height="381" srcset="https://irlimages.blob.core.windows.net/2022-10/image-7.png?w=840&amp;ssl=1 840w, https://irlimages.blob.core.windows.net/2022-10/image-7.png?resize=300%2C218&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-7.png?resize=768%2C559&amp;ssl=1 768w" sizes="(max-width: 523px) 100vw, 523px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/image-8.png?resize=556%2C391&#038;ssl=1" alt="" class="wp-image-477" width="556" height="391" srcset="https://irlimages.blob.core.windows.net/2022-10/image-8.png?resize=1024%2C718&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/image-8.png?resize=300%2C210&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/image-8.png?w=1127&amp;ssl=1 1127w" sizes="(max-width: 556px) 100vw, 556px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Device Enrolment Restrictions</strong></p>



<p>Device Enrolment Restrictions can be used to manage enrolment restrictions that define what &amp; how many devices can enrol into management with Intune.</p>



<ul><li>Maximum number of enrolled devices.</li><li>Device platforms that can enrol:<ul><li>Android device administrator</li><li>Android Enterprise work profile</li><li>iOS/iPadOS</li><li>macOS</li><li>Windows</li></ul></li><li>Platform operating system version for iOS/iPadOS, Android device administrator, Android Enterprise work profile, Windows, and Windows Mobile.</li><li>Restrict personally owned devices (iOS, Android device administrator, Android Enterprise work profile, macOS, Windows, and Windows Mobile only).</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Microsoft Cloud App Security</strong></p>



<p>If you have M365 E5 then Microsoft Cloud App Security (MCAS) can be used</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Session Controls</strong></p>



<p>You can use session controls for cloud apps to control in-session activities and can also apply access controls to block the same set of native mobile and desktop client apps, thereby providing comprehensive security for the apps.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Conclusion</h2>



<p>I hope that with this post you will be able to support the use of Bring Your Own Device (BYOD) scenarios in your organisations by allowing the use of personal devices along with securing access to your corporate data. </p>



<p>The next post will be a <strong>step-by-step enrollment guide</strong> for enrolling a personal iOS &amp; Android device in Intune. Stay In(tuned). </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p style="font-size:2px"><a href="https://www.freepik.com/free-vector/byod-concept-illustration_2870658.htm#query=bring%20your%20own%20device&amp;position=0&amp;from_view=keyword">Image by macrovector</a> on Freepik</p>
<!--kg-card-end: html-->