---
title: "Keep Me Upadted!"
date: 2022-09-03T09:12:00"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>With iOS/iPadOS 16 scheduled to be released in the next few days, many organizations will put restrictions on deferring software updates to buy in time to get ready with the new OS. At the same, there will be many zero-day vulnerabilities for which you might want to keep your devices updated to a specific version.&nbsp;</p>



<p>Hope this will help you to configure the software update policies and keep your iOS devices updated. The software update policies can only be applied to devices enrolled as&nbsp;<strong>supervised</strong>. This seems straightforward, but practically speaking, it&#8217;s NOT that simple!&nbsp;</p>



<p>Continue reading the post to configure the policy for your tenant.</p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="498" height="249" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/i-want-regular-updates-update-me-1.gif?resize=498%2C249&#038;ssl=1" alt="" class="wp-image-303" data-recalc-dims="1"/></figure>



<p>The software update policies can only be applied to supervised devices with iOS/iPadOS 13 minimum required version.&nbsp;</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Concept:</strong></h4>



<p>With these software update policies, you can:</p>



<ol><li>Either choose to deploy the&nbsp;<em><strong>latest available update</strong></em>&nbsp;or choose to deploy an older update.</li><li>&nbsp;Configure the update to install at a specific time.&nbsp;</li></ol>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="135" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-223629-1.jpg?resize=750%2C135&#038;ssl=1" alt="" class="wp-image-304" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-223629-1.jpg?resize=1024%2C185&amp;ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-223629-1.jpg?resize=300%2C54&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-223629-1.jpg?resize=768%2C139&amp;ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-223629-1.jpg?w=1027&amp;ssl=1 1027w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>If you are configuring software update policies for&nbsp;<strong>Shared iPads,</strong>&nbsp;then the update will only install when no user is signed in to a Shared iPad and the device is charging. Else the update will fail.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Configure The Policy</strong></h4>



<ul><li>Sign in to the&nbsp;<a rel="noreferrer noopener" href="https://endpoint.microsoft.com/" target="_blank">MEM Portal</a>.</li><li>Select&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>Update policies for iOS/iPadOS</strong>&nbsp;&gt;&nbsp;<strong>Create profile</strong>.</li><li>On the&nbsp;<strong>Basics</strong>&nbsp;tab, specify a name for this policy, specify a description (optional), and then select&nbsp;<strong>Next</strong>.</li></ul>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="362" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/1-ca3d191.png?resize=750%2C362&#038;ssl=1" alt="" class="wp-image-306" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/1-ca3d191.png?resize=1024%2C494&amp;ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/1-ca3d191.png?resize=300%2C145&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/1-ca3d191.png?resize=768%2C371&amp;ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/1-ca3d191.png?resize=1536%2C741&amp;ssl=1 1536w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/1-ca3d191.png?w=1627&amp;ssl=1 1627w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<ul><li>On the next page, you have the options to configure the policy options:<ul><li>Select a specific version to install</li><li>Configure the schedule for the policy</li></ul></li></ul>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="367" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-230121-1.jpg?resize=750%2C367&#038;ssl=1" alt="" class="wp-image-307" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-230121-1.jpg?resize=1024%2C501&amp;ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-230121-1.jpg?resize=300%2C147&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-230121-1.jpg?resize=768%2C376&amp;ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-230121-1.jpg?resize=1536%2C752&amp;ssl=1 1536w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-230121-1.jpg?w=1781&amp;ssl=1 1781w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>These options look interesting. But before we apply the policy, let us understand them in detail.</p>



<ul><li><strong>Latest update</strong>: Deploys the most recently released update for iOS/iPadOS.</li><li>If you select a&nbsp;<strong>previous version</strong>, you must also deploy a&nbsp;<strong>device restriction policy</strong>&nbsp;to hide the visibility of software updates from the device.</li><li><strong>Update at next check-in</strong>: The update installs on the device the next time it checks in with Intune. This option requires no extra configurations.</li><li><strong>Update during scheduled time</strong>: You configure one or more windows of time during which the update will install upon check-in.</li><li><strong>Update outside of scheduled time</strong>: You configure one or more windows of time&nbsp;during which updates won&#8217;t install upon check-in.</li><li><strong>Weekly schedule</strong>: If you choose a schedule type other than&nbsp;<em><strong>update at the next check-in</strong></em>, configure the following options.</li></ul>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="523" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/scheduled-time-1.png?resize=750%2C523&#038;ssl=1" alt="" class="wp-image-308" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/scheduled-time-1.png?resize=1024%2C714&amp;ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/scheduled-time-1.png?resize=300%2C209&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/scheduled-time-1.png?resize=768%2C536&amp;ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/scheduled-time-1.png?w=1038&amp;ssl=1 1038w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="132" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-233450-1.jpg?resize=750%2C132&#038;ssl=1" alt="" class="wp-image-309" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-233450-1.jpg?w=1003&amp;ssl=1 1003w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-233450-1.jpg?resize=300%2C53&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-233450-1.jpg?resize=768%2C136&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<ul><li>Configure the policy as required and&nbsp;<strong>assign&nbsp;</strong>it to the respective security group.</li></ul>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="360" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-225938-1.jpg?resize=750%2C360&#038;ssl=1" alt="" class="wp-image-310" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-225938-1.jpg?resize=1024%2C491&amp;ssl=1 1024w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-225938-1.jpg?resize=300%2C144&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-225938-1.jpg?resize=768%2C368&amp;ssl=1 768w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-225938-1.jpg?resize=1536%2C736&amp;ssl=1 1536w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-225938-1.jpg?w=1801&amp;ssl=1 1801w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="132" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-234118-1.jpg?resize=750%2C132&#038;ssl=1" alt="" class="wp-image-311" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-234118-1.jpg?w=997&amp;ssl=1 997w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-234118-1.jpg?resize=300%2C53&amp;ssl=1 300w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/09/Screenshot-2022-09-02-234118-1.jpg?resize=768%2C136&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>End User Experience</strong></h4>



<p>When you assign these policies, you might notice discrepancies between expected and experienced behavior.</p>



<ol><li><strong>Expected behavior when OS update is released to iPad</strong>:</li></ol>



<ul><li>Notification on the device that the new OS is available.</li><li>OS version and &#8220;<strong>Download and Install</strong>&#8221; is displayed in the Settings app.</li><li>Installation is prompted for acceptance with the possibility to Postpone or Install<strong> </strong>during the time window (configured in the policy) if connected to <strong>power</strong>.</li><li>If <strong>accepted</strong>, by entering <strong>Passcode</strong>, the iPad will install new iOS; if connected to power.</li><li>If <strong>postponed</strong>, the iPad will not update, and a new prompt will appear from time to time.</li><li>If <strong>power</strong> is not connected, the iPad will not update</li></ul>



<p>&nbsp;&nbsp;2.&nbsp;<strong>Experienced behavior when new OS is released to iPad:</strong></p>



<ul><li>  Notification on the device that a new OS is available.</li><li>OS version and &#8220;<strong>Download and Install</strong>&#8221; is displayed in Settings.</li><li>Installation is prompted for acceptance with the possibility to Postpone or Install during a limited time (<strong>configured policy</strong>) if connected to power.</li><li>If accepted, by entering Passcode, the iPad will install new iOS; if connected to power.</li><li>If accepted, the iPad will install randomly outside the time frame by entering the Passcode.</li><li>If accepted, by entering the Passcode, the iPad will install even if power is not connected (more than 50% battery).</li><li>If Postponed, the iPad will install after 3 Postponed warnings.</li><li>iPad shows a notification that a new OS is available. When checked in Settings iPad shows the latest MDM released OS. After some time, a warning prompt is displayed.</li><li>&#8220;Pad shows &#8220;<strong>New update available</strong>&#8221; – Installation is accepted.</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Bonus Content: Reasons for Discrepancies</strong></h4>



<p>(Reasons are in chronological order)</p>



<ol><li>When the user checks for the update in Settings Apps, the update can be deleted if it falls within the delay period set on the device. This behavior ties in with most of the other scenarios.</li><li>When the Passcode is stashed, and the MDM uses the &#8216;Download&#8217; and &#8216;InstallASAP&#8221; options in the ScheduleOSUpdate command &#8211; the device will update.</li><li><strong>Update Cadence</strong>. This was introduced in iOS 14.6 and can be configured with the Settings command. </li></ol>



<p>This value defines how the system presents software updates to the user. When there&#8217;s&nbsp;more than one available update for the user, the system behaves as follows:</p>



<p><strong>0: Presents both options to the user.<br>1: Presents the lower numbered (oldest) software update version.<br>2: Presents only the highest numbered (most recent) release available for the device.</strong></p>



<p>Hope this will help you to configure the software update policies and keep your iOS devices updated.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>Share this post:</p>



<ul class="is-layout-flex wp-block-social-links"><li class="wp-social-link wp-social-link-facebook wp-block-social-link"><a href="https://www.facebook.com/"  class="wp-block-social-link-anchor"><svg width="24" height="24" viewBox="0 0 24 24" version="1.1" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false"><path d="M12 2C6.5 2 2 6.5 2 12c0 5 3.7 9.1 8.4 9.9v-7H7.9V12h2.5V9.8c0-2.5 1.5-3.9 3.8-3.9 1.1 0 2.2.2 2.2.2v2.5h-1.3c-1.2 0-1.6.8-1.6 1.6V12h2.8l-.4 2.9h-2.3v7C18.3 21.1 22 17 22 12c0-5.5-4.5-10-10-10z"></path></svg><span class="wp-block-social-link-label screen-reader-text">Facebook</span></a></li>

<li class="wp-social-link wp-social-link-twitter wp-block-social-link"><a href="https://twitter.com/"  class="wp-block-social-link-anchor"><svg width="24" height="24" viewBox="0 0 24 24" version="1.1" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false"><path d="M22.23,5.924c-0.736,0.326-1.527,0.547-2.357,0.646c0.847-0.508,1.498-1.312,1.804-2.27 c-0.793,0.47-1.671,0.812-2.606,0.996C18.324,4.498,17.257,4,16.077,4c-2.266,0-4.103,1.837-4.103,4.103 c0,0.322,0.036,0.635,0.106,0.935C8.67,8.867,5.647,7.234,3.623,4.751C3.27,5.357,3.067,6.062,3.067,6.814 c0,1.424,0.724,2.679,1.825,3.415c-0.673-0.021-1.305-0.206-1.859-0.513c0,0.017,0,0.034,0,0.052c0,1.988,1.414,3.647,3.292,4.023 c-0.344,0.094-0.707,0.144-1.081,0.144c-0.264,0-0.521-0.026-0.772-0.074c0.522,1.63,2.038,2.816,3.833,2.85 c-1.404,1.1-3.174,1.756-5.096,1.756c-0.331,0-0.658-0.019-0.979-0.057c1.816,1.164,3.973,1.843,6.29,1.843 c7.547,0,11.675-6.252,11.675-11.675c0-0.178-0.004-0.355-0.012-0.531C20.985,7.47,21.68,6.747,22.23,5.924z"></path></svg><span class="wp-block-social-link-label screen-reader-text">Twitter</span></a></li>

<li class="wp-social-link wp-social-link-linkedin wp-block-social-link"><a href="https://www.linkedin.com/"  class="wp-block-social-link-anchor"><svg width="24" height="24" viewBox="0 0 24 24" version="1.1" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" focusable="false"><path d="M19.7,3H4.3C3.582,3,3,3.582,3,4.3v15.4C3,20.418,3.582,21,4.3,21h15.4c0.718,0,1.3-0.582,1.3-1.3V4.3 C21,3.582,20.418,3,19.7,3z M8.339,18.338H5.667v-8.59h2.672V18.338z M7.004,8.574c-0.857,0-1.549-0.694-1.549-1.548 c0-0.855,0.691-1.548,1.549-1.548c0.854,0,1.547,0.694,1.547,1.548C8.551,7.881,7.858,8.574,7.004,8.574z M18.339,18.338h-2.669 v-4.177c0-0.996-0.017-2.278-1.387-2.278c-1.389,0-1.601,1.086-1.601,2.206v4.249h-2.667v-8.59h2.559v1.174h0.037 c0.356-0.675,1.227-1.387,2.526-1.387c2.703,0,3.203,1.779,3.203,4.092V18.338z"></path></svg><span class="wp-block-social-link-label screen-reader-text">LinkedIn</span></a></li></ul>
<!--kg-card-end: html-->