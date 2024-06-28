---
title: "Locate lost or stolen Android Enterprise devices with Intune"
date: 2022-12-21T01:35:16"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>Microsoft Intune allows you to easily &#8220;<strong>locate a device</strong>&#8221; if it&#8217;s lost or stolen. However, this functionality is still unavailable for all devices/platforms. As of today, only this functionality works for the below platforms:</p>



<ul>
<li><strong>Android Enterprise dedicated devices</strong> </li>



<li><strong>iOS/iPadOS 9.3 and later</strong></li>



<li><strong>Windows 10</strong></li>



<li><strong>Windows 1</strong>1</li>
</ul>



<p>Whereas the below-listed platforms do not support this functionality from Intune admin portal, and that&#8217;s the reason that the &#8220;<strong>locate device</strong>&#8221; remote command is greyed out when for these platforms:</p>



<ul>
<li>Android device administrator</li>



<li>Android Enterprise:
<ul>
<li>Corporate-owned work profile</li>



<li>Personally-owned work profile</li>



<li>Fully managed</li>
</ul>
</li>



<li>macOS</li>



<li>Windows Holographic for Business</li>



<li>Windows Phone</li>
</ul>



<p>But there is always a way out 😃. With this post, I will show how you can use Samsung Knox to get device location information. Let&#8217;s get started, then.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Mandatory Requirements</h2>



<p>As we are discussing Android Enterprise devices, I assume you already have a purchased KNOX Enterprise and devices are enrolled with KMS. Apart from this, the other pre-requisites are:</p>



<ul>
<li>Location policy configured in KM and assigned to the device.</li>



<li>Location policy configured and assigned correctly to the device</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Configure Location Policy</h2>



<p>You must configure and assign a policy for getting device locations utilizing Knox Management APIs. </p>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/12/image-16.png?resize=552%2C278&#038;ssl=1" alt="" class="wp-image-964" width="552" height="278" srcset="https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/12/image-16.png?w=736&amp;ssl=1 736w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/12/image-16.png?resize=300%2C151&amp;ssl=1 300w" sizes="(max-width: 552px) 100vw, 552px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Create the API Client</h2>
<!--kg-card-end: html-->