---
title: "What is AOSP? How to use Android Emulators to configure, manage & enroll AVDs in Intune? - Part1"
date: 2023-01-20T10:00:09"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<h2>Scenarios</h2>



<p>Have you been in situations where you need to give demos on different Android OS or models and do not have actual hardware running Android to show different scenarios programs? The Android emulator provides almost all the capabilities of a real Android device. You can simulate incoming phone calls and text messages, specify the device’s location, simulate different network speeds, simulate rotation and other hardware sensors, access the Google Play Store, and much more.</p>



<h2>Overview</h2>



<p>Android is an open-source operating system for mobile devices and a corresponding project led by Google. This site and the Android Open Source Project (AOSP) repository offer the information and source code needed to create custom variants of the Android OS, port devices and accessories to the Android platform, and ensure devices meet the compatibility requirements that keep the Android ecosystem a healthy and stable environment for millions of users. Sounds complicated?</p>



<p>Simply put, AOSP is an open-source operating system development project maintained by Google. Since it’s open-source, anyone can review and contribute code and fixes to the project repository. </p>



<p>As an open-source project, Android seeks to avoid any single point of failure where one participant in the industry might limit or regulate the innovations of any other participant. To achieve this, Android is a complete, high-quality operating system for consumer goods, complete with customisable source code that can be ported to almost any device and openly available documentation.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Where is AOSP used?</h2>



<p>Any smartphone company that manufactures Android devices uses the Android Open Source Project. AOSP code is used by almost everyone who makes a smartphone. Although each Android version differs in how it looks, feels, and performs, they are all built using the same body of code known as the Android Open Source Project (AOSP). Every year, Google updates the Android Open Source Project repository with new codebase versions.</p>



<h2>Development of AOSP</h2>



<p>Android is developed by Google until the latest changes and updates are ready to be released. At this point, the source code is made available to the Android Open Source Project (AOSP), an open-source initiative led by Google. The first source code release happened as part of the initial release in 2007. All releases are under the Apache License.</p>



<p>The AOSP code can be found with minimal modifications on select devices, mainly the former Nexus and the current Android One series. However, most original equipment manufacturers (OEMs) customize the source code to run on their hardware.</p>



<p class="has-text-align-left">Android’s source code does not contain the device drivers, often proprietary, that are needed for certain hardware components and does not contain the source code of Google Play Services, which many apps depend on. As a result, most Android devices, including Google’s own, ship with a combination of free and open source and proprietary software, with the software required for accessing Google services falling into the latter category. In response to this, some projects build complete operating systems based on AOSP as free software, the first being CyanogenMod.</p>


<div class="wp-block-image is-style-default">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-17.png?resize=464%2C322&ssl=1" alt="" class="wp-image-1056" width="464" height="322" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-17.png?w=618&ssl=1 618w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-17.png?resize=300%2C208&ssl=1 300w" sizes="(max-width: 464px) 100vw, 464px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>The Android Operating System (https://source.android.com/source/)</em></figcaption></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Configure Intune enrollment for Android (AOSP) corporate-owned devices</h2>



<p>Intune offers an <em>Android (AOSP)</em> device management solution for corporate-owned Android devices that are:</p>



<ul>
<li>Not integrated with Google Mobile Services.</li>



<li>Intended to be shared by more than one user.</li>



<li>Used to accomplish a specific set of tasks at work.</li>
</ul>



<p>In this blog post, I will use Android Studio to create an AVD and will use it to enrol it as an AOSP dedicated device.</p>



<h3>Create an enrollment profile</h3>



<ol>
<li>Sign in to the <a href="https://endpoint.microsoft.com/" target="_blank" rel="noopener" title="">Microsoft Endpoint Manager admin center</a> and select <strong>Devices</strong> > <strong>Android</strong> > <strong>Android enrollment</strong> > <strong>Corporate-owned, <strong>user-associated devices</strong></strong>.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-18.png?resize=381%2C366&ssl=1" alt="" class="wp-image-1057" width="381" height="366" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-18.png?w=762&ssl=1 762w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-18.png?resize=300%2C288&ssl=1 300w" sizes="(max-width: 381px) 100vw, 381px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-57.png?resize=750%2C358&ssl=1" alt="" class="wp-image-1097" width="750" height="358" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-57.png?resize=1024%2C489&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-57.png?resize=300%2C143&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-57.png?resize=768%2C367&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-57.png?resize=1536%2C734&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-57.png?w=1539&ssl=1 1539w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="2">
<li>Select <strong>Create</strong> and fill out the required fields.










<ul>
<li><strong>Name</strong>: Type a name for the profile.</li>



<li><strong>Description</strong>: Add a profile description (optional).</li>
</ul>



<ul>
<li><strong>Token expiration date</strong>: The date when the token expires. Intune enforces a maximum of 90 days.</li>



<li><strong>SSID</strong>: Identifies the network that the device will connect to.</li>



<li><strong>Hidden Network</strong>: Choose whether this is a hidden network. By default, this setting is disabled.</li>



<li><strong>Wi-Fi Type</strong>: Select the type of authentication needed for this network. </li>
</ul>
</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-20.png?resize=611%2C203&ssl=1" alt="" class="wp-image-1059" width="611" height="203" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-20.png?w=814&ssl=1 814w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-20.png?resize=300%2C100&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-20.png?resize=768%2C255&ssl=1 768w" sizes="(max-width: 611px) 100vw, 611px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-63.png?resize=749%2C496&ssl=1" alt="" class="wp-image-1103" width="749" height="496" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-63.png?w=999&ssl=1 999w, https://irlimages.blob.core.windows.net/2023-01/image-63.png?resize=300%2C198&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-63.png?resize=768%2C508&ssl=1 768w" sizes="(max-width: 749px) 100vw, 749px" data-recalc-dims="1" /></figure></div>


<ol start="3">
<li>Select <strong>Next,</strong> and optionally, select scope tags.</li>
</ol>



<ol start="4">
<li>Select <strong>Next</strong>. Review your profile details and then select <strong>Create</strong> to save the profile.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-63.png?resize=750%2C450&ssl=1" alt="" class="wp-image-1099" width="750" height="450" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-63.png?resize=1024%2C615&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-63.png?resize=300%2C180&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-63.png?resize=768%2C462&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-63.png?w=1133&ssl=1 1133w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<h3>Access enrollment token</h3>



<p>After creating a profile, Intune generates a token needed for enrollment. To access the token:</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-60.png?resize=750%2C313&ssl=1" alt="" class="wp-image-1100" width="750" height="313" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-60.png?resize=1024%2C428&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-60.png?resize=300%2C125&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-60.png?resize=768%2C321&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-60.png?w=1323&ssl=1 1323w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<h3>Create a device group</h3>



<p>You can create <em>assigned device groups</em> or <em>dynamic device groups</em> in Intune. Complete the following steps to create a dynamic Azure AD device group for devices enrolled with an Android (AOSP) corporate-owned, userless enrollment profile.</p>



<ol>
<li>Sign in to the <a href="https://endpoint.microsoft.com/" target="_blank" rel="noopener" title="">Microsoft Endpoint Manager admin center</a> and choose <strong>Groups</strong> > <strong>All groups</strong> > <strong>New group</strong>.</li>
</ol>



<ol start="2">
<li>In the <strong>Group</strong> blade, fill out the required fields as follows:
<ul>
<li><strong>Group type</strong>: Security</li>



<li><strong>Group name</strong>: Type an intuitive name</li>



<li><strong>Membership type</strong>: Dynamic device</li>
</ul>
</li>
</ol>



<ol start="3">
<li>Click <strong>Add dynamic query</strong>.</li>
</ol>



<ol start="4">
<li>In the <strong>Dynamic membership rules</strong> blade, fill out the fields as follows:
<ul>
<li><strong>Add dynamic membership rule</strong>: Simple rule</li>



<li><strong>Add devices where</strong>: enrollmentProfileName</li>



<li>In the middle box, choose <strong>Equals</strong>.</li>



<li>In the last field, enter the enrollment profile name that you created earlier.</li>
</ul>
</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-61.png?resize=750%2C516&ssl=1" alt="" class="wp-image-1101" width="750" height="516" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-61.png?resize=1024%2C704&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-61.png?resize=300%2C206&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-61.png?resize=768%2C528&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-61.png?w=1171&ssl=1 1171w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-62.png?resize=750%2C280&ssl=1" alt="" class="wp-image-1102" width="750" height="280" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-62.png?resize=1024%2C382&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-62.png?resize=300%2C112&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-62.png?resize=768%2C286&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-62.png?resize=1536%2C573&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-62.png?w=1617&ssl=1 1617w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p class="has-text-align-center"><em>Create a dynamic membership query</em></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Create Android Virtual Devices</h2>



<p>An Android Virtual Device (AVD) is a configuration that defines the characteristics of an Android phone, tablet, Wear OS, Android TV, or Automotive OS device that you want to simulate in the <a href="https://developer.android.com/" target="_blank" rel="noopener" title="">Android Emulator</a>. The Device Manager is a tool you can launch from Android Studio that helps you create and manage AVDs. To create an AVD, you need Android Studio. Follow the steps to install and configure Android Studio:</p>



<h3>Download and Install Android Studio</h3>



<ul>
<li>Visit the official <a href="https://developer.android.com/studio/" target="_blank" rel="noopener" title="">Android Studio</a> website in your web browser.</li>
</ul>



<ul>
<li>Click on the “<strong>Download Android Studio</strong>” option and accept the EULA.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-26.png?resize=750%2C355&ssl=1" alt="" class="wp-image-1065" width="750" height="355" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-26.png?resize=1024%2C485&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-26.png?resize=300%2C142&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-26.png?resize=768%2C364&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-26.png?resize=1536%2C728&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-26.png?w=1660&ssl=1 1660w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Double-click on the downloaded “android-studio-2022.1.1.19-windows” file.</li>
</ul>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="127" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-27.png?resize=750%2C127&ssl=1" alt="" class="wp-image-1066" srcset=" v/image-27.png?resize=1024%2C174&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-27.png?resize=300%2C51&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-27.png?resize=768%2C130&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-27.png?resize=1536%2C260&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-27.png?w=1605&ssl=1 1605w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<ul>
<li>“Android Studio Setup” will appear on the screen and click “<strong>Next</strong>” to proceed.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-30.png?resize=467%2C364&ssl=1" alt="" class="wp-image-1069" width="467" height="364" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-30.png?w=622&ssl=1 622w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-30.png?resize=300%2C234&ssl=1 300w" sizes="(max-width: 467px) 100vw, 467px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Select the components you want to install and click on the “<strong>Next</strong>” button.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-31.png?resize=467%2C364&ssl=1" alt="" class="wp-image-1070" width="467" height="364" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-31.png?w=622&ssl=1 622w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-31.png?resize=300%2C234&ssl=1 300w" sizes="(max-width: 467px) 100vw, 467px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Browse the location where you want to install the Android Studio and click “<strong>Next</strong>” to proceed.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-32.png?resize=467%2C364&ssl=1" alt="" class="wp-image-1071" width="467" height="364" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-32.png?w=622&ssl=1 622w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-32.png?resize=300%2C234&ssl=1 300w" sizes="(max-width: 467px) 100vw, 467px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Choose a start menu folder for the “<strong>Android Studio</strong>” shortcut and click the “<strong>Install</strong>” button to proceed.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-33.png?resize=467%2C364&ssl=1" alt="" class="wp-image-1072" width="467" height="364" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-33.png?w=622&ssl=1 622w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-33.png?resize=300%2C234&ssl=1 300w" sizes="(max-width: 467px) 100vw, 467px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Once the installation is completed, click on the “<strong>Next</strong>” button.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-34.png?resize=467%2C364&ssl=1" alt="" class="wp-image-1073" width="467" height="364" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-34.png?w=622&ssl=1 622w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-34.png?resize=300%2C234&ssl=1 300w" sizes="(max-width: 467px) 100vw, 467px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-35.png?resize=467%2C364&ssl=1" alt="" class="wp-image-1074" width="467" height="364" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-35.png?w=622&ssl=1 622w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-35.png?resize=300%2C234&ssl=1 300w" sizes="(max-width: 467px) 100vw, 467px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Click “<strong>Finish</strong>” to proceed.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-36.png?resize=467%2C364&ssl=1" alt="" class="wp-image-1075" width="467" height="364" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-36.png?w=622&ssl=1 622w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-36.png?resize=300%2C234&ssl=1 300w" sizes="(max-width: 467px) 100vw, 467px" data-recalc-dims="1" /></figure></div>


<ul>
<li>“<strong>Android Studio Setup Wizard</strong>” will appear on the screen with the welcome wizard. Click on the “<strong>Next</strong>” button.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-38.png?resize=508%2C380&ssl=1" alt="" class="wp-image-1077" width="508" height="380" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-38.png?w=677&ssl=1 677w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-38.png?resize=300%2C224&ssl=1 300w" sizes="(max-width: 508px) 100vw, 508px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Select (check) the “<strong>Standard</strong>” option. It will install the most common settings and options for you. Click “<strong>Next</strong>” to proceed.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-40.png?resize=505%2C377&ssl=1" alt="" class="wp-image-1079" width="505" height="377" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-40.png?w=673&ssl=1 673w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-40.png?resize=300%2C224&ssl=1 300w" sizes="(max-width: 505px) 100vw, 505px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Now, select the user interface theme. Then, click on the “<strong>Next</strong>” button.</li>
</ul>



<ul>
<li>Click “<strong>Finish</strong>” to download all the SDK components.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-42.png?resize=506%2C380&ssl=1" alt="" class="wp-image-1081" width="506" height="380" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-42.png?w=674&ssl=1 674w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-42.png?resize=300%2C226&ssl=1 300w" sizes="(max-width: 506px) 100vw, 506px" data-recalc-dims="1" /></figure></div>


<ul>
<li>The downloading and installation process of components gets started.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-43.png?resize=502%2C377&ssl=1" alt="" class="wp-image-1082" width="502" height="377" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-43.png?w=669&ssl=1 669w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-43.png?resize=300%2C226&ssl=1 300w" sizes="(max-width: 502px) 100vw, 502px" data-recalc-dims="1" /></figure></div>


<ul>
<li>After downloading all the necessary components, click on the “<strong>Finish</strong>” button.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-44.png?resize=501%2C371&ssl=1" alt="" class="wp-image-1083" width="501" height="371" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-44.png?w=668&ssl=1 668w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-44.png?resize=300%2C222&ssl=1 300w" sizes="(max-width: 501px) 100vw, 501px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-37.png?resize=750%2C446&ssl=1" alt="" class="wp-image-1076" width="750" height="446" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-37.png?resize=1024%2C609&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-37.png?resize=300%2C178&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-37.png?resize=768%2C457&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-37.png?resize=1536%2C913&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-37.png?w=1909&ssl=1 1909w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3>Create Android Virtual Devices</h3>



<ul>
<li>From the Android Studio, select <strong>Tools > Device Manager</strong>.</li>
</ul>



<ul>
<li>Click <strong>Create Device</strong>.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-47.png?resize=750%2C222&ssl=1" alt="" class="wp-image-1086" width="750" height="222" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-47.png?resize=1024%2C302&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-47.png?resize=300%2C89&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-47.png?resize=768%2C227&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-47.png?resize=1536%2C454&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-47.png?w=1747&ssl=1 1747w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Select <strong>WearOS </strong>from the Hardware window and click <strong>Next</strong>.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-49.png?resize=750%2C488&ssl=1" alt="" class="wp-image-1088" width="750" height="488" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-49.png?resize=1024%2C667&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-49.png?resize=300%2C195&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-49.png?resize=768%2C500&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-49.png?w=1230&ssl=1 1230w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Select the system image for a particular API level and click <strong>Next</strong>. <strong>Verify Configuration</strong> window appears. Ensure the target Operating System selected includes <strong>Google Play.</strong></li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-52.png?resize=750%2C486&ssl=1" alt="" class="wp-image-1091" width="750" height="486" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-52.png?resize=1024%2C664&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-52.png?resize=300%2C195&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-52.png?resize=768%2C498&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-52.png?w=1238&ssl=1 1238w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Select <strong>Download</strong> to begin downloading of image file</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-51.png?resize=750%2C541&ssl=1" alt="" class="wp-image-1090" width="750" height="541" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-51.png?resize=1024%2C738&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-51.png?resize=300%2C216&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-51.png?resize=768%2C553&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-51.png?w=1127&ssl=1 1127w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Once the download has been completed, select the image and click <strong>Next</strong>.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-53.png?resize=750%2C485&ssl=1" alt="" class="wp-image-1092" width="750" height="485" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-53.png?resize=1024%2C663&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-53.png?resize=300%2C194&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-53.png?resize=768%2C498&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-53.png?w=1238&ssl=1 1238w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Configure <strong>Android Virtual Device (AVD)</strong></li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-54.png?resize=750%2C487&ssl=1" alt="" class="wp-image-1093" width="750" height="487" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-54.png?resize=1024%2C665&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-54.png?resize=300%2C195&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-54.png?resize=768%2C498&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-54.png?w=1251&ssl=1 1251w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Click <strong>Finish</strong>.</li>
</ul>



<ul>
<li>Click on the “<strong>Play</strong>” button to start the AVD.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-55.png?resize=750%2C438&ssl=1" alt="" class="wp-image-1094" width="750" height="438" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-55.png?resize=1024%2C598&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-55.png?resize=300%2C175&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-55.png?resize=768%2C448&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-55.png?resize=1536%2C897&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-55.png?w=1855&ssl=1 1855w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-56.png?resize=454%2C749&ssl=1" alt="" class="wp-image-1095" width="454" height="749" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2023/01/image-56.png?w=605&ssl=1 605w, https://irlimages.blob.core.windows.net/2023-01/image-56.png?resize=182%2C300&ssl=1 182w" sizes="(max-width: 454px) 100vw, 454px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Voila.</em> <em>It’s an Android Watch</em>!</figcaption></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>That’s all for now!</h2>



<p>In today’s post, we learned about AOSP and its development and looked at how to set up and configure Android Studio to emulate Android devices. I’ll next explain how to set up an Android emulator for macOS. In the following two posts, we’ll continue the evaluation of <strong>Android Virtual Devices (AVD)</strong> and then with a demo of enrolling them in Microsoft Intune.</p>



<p>Thank you for reading, and keep watching for those upcoming posts!</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>

<!--kg-card-end: html-->
