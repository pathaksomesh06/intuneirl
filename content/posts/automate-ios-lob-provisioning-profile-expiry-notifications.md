---
title: "Automate iOS LOB Provisioning Profile Expiry Notifications"
date: 2022-11-11T14:16:12"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Background</h2>



<p>The line-of-business Apple iOS/iPadOS apps assigned to iPhones and iPads are created with a provisioning profile that is included and is code signed with a certificate. IOS/iPadOS verifies its integrity and applies any provisioning profile-defined policies when the app runs. The following validations happen:</p>



<ul><li><strong>Installation file integrity</strong>&nbsp;&#8211; iOS/iPadOS compares the app&#8217;s details with the enterprise signing certificate&#8217;s public key. If they differ, the app&#8217;s content might have changed, and it is not allowed to run.</li><li>Capabilities enforcement&nbsp;&#8211; iOS/iPadOS attempts to enforce the app&#8217;s capabilities from the enterprise provisioning profile (not individual developer provisioning profiles) in the app installation (.ipa) file.</li></ul>



<p>The enterprise signing certificate used to sign the apps typically lasts three years. However, the provisioning profile expires after a year, and the app needs to be packaged again with the new provisioning profile. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>The Pain Area</h2>



<p>There is now out of the box solution to set-up alerting to notify about the expiry of the provisioning profiles for the iOS apps. Intune portal has the functionality to the show the alert if provisioning profile or certificate is about to expire. The alert is just displayed as informational message, so that you know that one part of the LOB app is expired or close to expire and then you can take the required action.</p>



<p>Due this missing functionality, there are high chances of human error and it quite evident that the team managing Intune infrastructure may miss these notifications, leading to non-functioning apps on end user&#8217;s devices.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>The Options</h2>



<p>There multiple ways to achieve this functionality of creating automated email notifications few days prior to the provisioning profile expiry so that you have ample time to react and get the new build created.</p>



<p>The possible options you have to automate it are:</p>



<ul><li>Automate the flow using ServiceNow</li><li>Automate the flow using Power Automate</li><li>Automate the flow using Logic Apps</li></ul>



<p>Which ever option you choose, you will be relying on Graph API calls to get the data about managed apps and their properties.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>The Solution</h2>



<p>For this article, I have used Power Automate to create the flow and get automatic emails for notifying on the provisioning profile.</p>



<ol><li>Sign in to&nbsp;<a href="https://flow.microsoft.com/" target="_blank" rel="noopener" title="">Power Automate</a>.</li></ol>



<ol start="2"><li>Select&nbsp;<strong>My flows</strong>&nbsp;&gt;&nbsp;<strong>New flow</strong>&nbsp;&gt;&nbsp;<strong>Scheduled cloud flow</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-34.png?resize=292%2C237&#038;ssl=1" alt="" class="wp-image-758" width="292" height="237" srcset="https://irlimages.blob.core.windows.net/2022-11/image-34.png?w=389&amp;ssl=1 389w, https://irlimages.blob.core.windows.net/2022-11/image-34.png?resize=300%2C244&amp;ssl=1 300w" sizes="(max-width: 292px) 100vw, 292px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>In the fields next to&nbsp;<strong>Starting</strong>, specify the date and time when your flow should start.</li></ol>



<ol start="4"><li>In the fields next to <strong>Repeat every</strong>, specify the flow&#8217;s recurrence.</li></ol>



<ol start="5"><li>Select <strong>Create</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-35.png?resize=512%2C326&#038;ssl=1" alt="" class="wp-image-759" width="512" height="326" srcset="https://irlimages.blob.core.windows.net/2022-11/image-35.png?resize=1024%2C651&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-35.png?resize=300%2C191&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-35.png?resize=768%2C488&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-35.png?w=1082&amp;ssl=1 1082w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>


<ol start="6"><li>Select <strong>Recurrence</strong> > <strong>Show advanced options</strong>. When you select <strong>Show advanced options</strong>, the dropdown name changes to <strong>Hide advanced options</strong> and then configure the time/days to run the flow.</li></ol>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-36.png?resize=560%2C149&#038;ssl=1" alt="" class="wp-image-760" width="560" height="149" srcset="https://irlimages.blob.core.windows.net/2022-11/image-36.png?w=746&amp;ssl=1 746w, https://irlimages.blob.core.windows.net/2022-11/image-36.png?resize=300%2C80&amp;ssl=1 300w" sizes="(max-width: 560px) 100vw, 560px" data-recalc-dims="1" /></figure>



<ol start="7"><li>Click on &#8220;Add Action&#8221; and search for &#8220;<strong>Get Secret&#8221;</strong> and the connection can be with a managed identity</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-37.png?resize=557%2C92&#038;ssl=1" alt="" class="wp-image-761" width="557" height="92" srcset="https://irlimages.blob.core.windows.net/2022-11/image-37.png?w=742&amp;ssl=1 742w, https://irlimages.blob.core.windows.net/2022-11/image-37.png?resize=300%2C49&amp;ssl=1 300w" sizes="(max-width: 557px) 100vw, 557px" data-recalc-dims="1" /></figure></div>


<ol start="8"><li>Click on add action and add HTTP connection to make a Graph request in which we will query LOB apps.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-39.png?resize=559%2C320&#038;ssl=1" alt="" class="wp-image-763" width="559" height="320" srcset="https://irlimages.blob.core.windows.net/2022-11/image-39.png?w=745&amp;ssl=1 745w, https://irlimages.blob.core.windows.net/2022-11/image-39.png?resize=300%2C172&amp;ssl=1 300w" sizes="(max-width: 559px) 100vw, 559px" data-recalc-dims="1" /></figure></div>


<ol start="9"><li>Next, In the search box under <strong>Choose an operation</strong>, enter <strong>variable</strong> as your filter. From the <strong>Actions</strong> list, select <strong>Initialize variable &#8211; Variable</strong>. I will use this variable for comparing the expiry date of provisioning profile.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-38.png?resize=565%2C160&#038;ssl=1" alt="" class="wp-image-762" width="565" height="160" srcset="https://irlimages.blob.core.windows.net/2022-11/image-38.png?w=753&amp;ssl=1 753w, https://irlimages.blob.core.windows.net/2022-11/image-38.png?resize=300%2C85&amp;ssl=1 300w" sizes="(max-width: 565px) 100vw, 565px" data-recalc-dims="1" /></figure></div>


<ol start="10"><li>Save the flow right here and execute it as we need the response from the GET request. Run the flow and then copy the body from the result. It will be like this</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-40.png?resize=489%2C360&#038;ssl=1" alt="" class="wp-image-764" width="489" height="360" srcset="https://irlimages.blob.core.windows.net/2022-11/image-40.png?w=977&amp;ssl=1 977w, https://irlimages.blob.core.windows.net/2022-11/image-40.png?resize=300%2C221&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-40.png?resize=768%2C565&amp;ssl=1 768w" sizes="(max-width: 489px) 100vw, 489px" data-recalc-dims="1" /></figure></div>


<ol start="11"><li>As a next step, again initialize a variable to call for expiry date value from the response.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-41.png?resize=562%2C164&#038;ssl=1" alt="" class="wp-image-765" width="562" height="164" srcset="https://irlimages.blob.core.windows.net/2022-11/image-41.png?w=749&amp;ssl=1 749w, https://irlimages.blob.core.windows.net/2022-11/image-41.png?resize=300%2C88&amp;ssl=1 300w" sizes="(max-width: 562px) 100vw, 562px" data-recalc-dims="1" /></figure></div>


<ol start="12"><li>Now, map the properties using expressions.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-42.png?resize=560%2C187&#038;ssl=1" alt="" class="wp-image-766" width="560" height="187" srcset="https://irlimages.blob.core.windows.net/2022-11/image-42.png?w=747&amp;ssl=1 747w, https://irlimages.blob.core.windows.net/2022-11/image-42.png?resize=300%2C100&amp;ssl=1 300w" sizes="(max-width: 560px) 100vw, 560px" data-recalc-dims="1" /></figure></div>


<ol start="13"><li>Click Add step and add condition to compare and validate provisioning profile expiry date with a check that if the expiry date is less than 90 days from today then an auto-generated email should be sent to concerned team.</li></ol>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="322" src="https://irlimages.blob.core.windows.net/2022-11/image-43.png?resize=750%2C322&#038;ssl=1" alt="" class="wp-image-767" srcset="https://irlimages.blob.core.windows.net/2022-11/image-43.png?resize=1024%2C440&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-43.png?resize=300%2C129&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-43.png?resize=768%2C330&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-43.png?resize=1536%2C660&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/image-43.png?w=1574&amp;ssl=1 1574w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>All done! Save the flow and execute it.</p>



<p>You will receive the email with details of the app&#8217;s provisioning profile.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Wrapp Up</h2>



<p>The idea behind this post was to show how easily you can automate the notifications for expiry of your business critical applications. There are endless possibilities to modify the requirements as per your business requirements. Feel free to use it and modify it.</p>
<!--kg-card-end: html-->