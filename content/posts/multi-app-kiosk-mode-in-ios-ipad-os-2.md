---
title: "Multi-App KIOSK Mode In iOS/iPad OS"
date: 2022-09-23T20:52:00"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<p>This article describes how to enable multi-app kiosk mode on iOS using Intune.</p>



<p><strong>Kiosk mode</strong> is a lockdown mechanism that restricts the device to access only the allowed app with restricted access to the remaining functionality of the device. Such devices are used for a specific purpose, such as digital signage and ticket printing, and are traditionally company owned and not associated with any user. The multi-app kiosk mode helps you to allow the device to run only a few applications ensuring that the device is not used for anything other than the apps pushed to it.</p>



<p>As per Microsoft, these devices can be configured to run multiple applications in kiosk mode (available only for Android KNOX and Android Enterprise devices) or a single app available for Android and supervised iOS devices. However</p>



<p>What if you still want to configure your iOS/iPad OS devices to run in multi-app kiosk mode?? There is a workaround for it. However, you will not get a single-app kiosk’s exact look and feel. Let’s see how you can achieve it:</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Create an Apple Enrollment Profile:</strong></p>



<p>A few months back, I wrote a post with detailed steps and a walkthrough for creating an <a href="https://intuneirl.com/2022/07/company-owned-ios-device-automated-device-enrollment-part-i/" target="_blank" rel="noreferrer noopener"><strong>Apple enrollment profile</strong></a>. For now, we will create a profile for multi-app kiosk devices. Follow the steps below to configure the profile:</p>



<ul><li>From the <a rel="noreferrer noopener" href="https://endpoint.microsoft.com/" target="_blank"><u>Microsoft Endpoint Manager</u></a> portal, navigate to <strong>Devices</strong> > <strong>iOS/iPadOS</strong> > <strong>iOS/iPadOS enrollment</strong> > <strong>Enrollment program tokens</strong>. </li></ul>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="406" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/1-bc55a33.jpg?resize=750%2C406&ssl=1" alt="" class="wp-image-328" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/1-bc55a33.jpg?w=884&ssl=1 884w, https://irlimages.blob.core.windows.net/2022-09/1-bc55a33.jpg?resize=300%2C162&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/1-bc55a33.jpg?resize=768%2C415&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<ul><li>Select a token, and then select <strong>Profiles</strong>.Select <strong>Create profile</strong> > <strong>iOS/iPadOS</strong>.</li></ul>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="312" src="https://irlimages.blob.core.windows.net/2022-09/2-7eb43ed.png?resize=750%2C312&ssl=1" alt="" class="wp-image-329" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-7eb43ed.png?w=893&ssl=1 893w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-7eb43ed.png?resize=300%2C125&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-7eb43ed.png?resize=768%2C319&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="312" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-199394f.png?resize=750%2C312&ssl=1" alt="" class="wp-image-330" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-199394f.png?w=893&ssl=1 893w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-199394f.png?resize=300%2C125&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-199394f.png?resize=768%2C319&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<ul><li>Provide a <strong>Name</strong> and <strong>Description</strong> for the profile (These details will not be visible to users, and click <strong>Next</strong>.</li></ul>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="698" height="478" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114225.png?resize=698%2C478&ssl=1" alt="" class="wp-image-331" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114225.png?w=698&ssl=1 698w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114225.png?resize=300%2C205&ssl=1 300w" sizes="(max-width: 698px) 100vw, 698px" data-recalc-dims="1" /></figure>



<ul><li>In the management settings page, select “<strong>Enroll without User Affinity,”</strong> We will use this profile to enroll devices as multi-app kiosks.</li></ul>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="401" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114500.png?resize=750%2C401&ssl=1" alt="" class="wp-image-332" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114500.png?w=893&ssl=1 893w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114500.png?resize=300%2C161&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114500.png?resize=768%2C411&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="176" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114804-88d9432.png?resize=750%2C176&ssl=1" alt="" class="wp-image-333" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114804-88d9432.png?w=943&ssl=1 943w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114804-88d9432.png?resize=300%2C70&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-114804-88d9432.png?resize=768%2C180&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<ul><li>For locked enrollment, I would recommend using “Yes” for supervised devices, as it disables iOS/iPadOS settings for removing the management profile from the device. The only option to remove the profile is to wipe it.</li><li>If you allow users to sync their devices with any computer, select “<strong>Allow All</strong>” from Sync with the Computer option.</li><li>Configure naming template or cellular data if required and click <strong>Next</strong> to proceed.</li><li>On the <strong>Setup Assistant</strong> page, update settings for “Department” & “Department Phone Number”.</li><li>Next, you can toggle the options to modify the Setup Assistant screens on the device during user setup.</li></ul>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="473" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Untitled-cc56cfd.png?resize=750%2C473&ssl=1" alt="" class="wp-image-334" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Untitled-cc56cfd.png?w=758&ssl=1 758w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Untitled-cc56cfd.png?resize=300%2C189&ssl=1 300w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Sync managed devices</strong></p>



<p>Now that Intune has permission to manage your devices, we have to synchronize Intune<br>with Apple to see your managed devices in Intune portal.</p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="380" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/10-1.png?resize=750%2C380&ssl=1" alt="" class="wp-image-335" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/10-1.png?w=893&ssl=1 893w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/10-1.png?resize=300%2C152&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/10-1.png?resize=768%2C389&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Add Apps to Devices</strong></p>



<p>Assign the desired apps to the device group from Intune the conventional way. (Client Apps -> Add App).</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Multi-App Kiosk Mode</strong></p>



<ol><li>Sign in to the <a href="https://endpoint.microsoft.com/">Microsoft Endpoint Manager admin center</a>.</li><li>Select <strong>Devices</strong> > <strong>Configuration profiles</strong> > <strong>Create profile</strong>.</li><li>Enter the following properties:<ul><li>Platform: Choose the platform as iOS for your devices.</li></ul></li><li>Select <strong>Device restrictions</strong>. Or, select <strong>Templates</strong> > <strong>Device restrictions</strong>. Select <strong>Create</strong>.</li><li>In <strong>Basics</strong>, enter the <strong>Name and Description </strong>for the profile.</li><li>In the <strong>Configurations </strong>pane, select “<strong>Show or Hide apps</strong>,” as illustrated below. In the ‘<strong>Visible Apps</strong>’ section, you can select multiple apps that will be visible to the user while everything else remains hidden.</li><li>You can arrange the <strong>Dock </strong>also on the device to pin the allowed apps there.</li><li>In <strong>Assignments</strong>, select the device groups that will receive your profile. </li></ol>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="607" height="478" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-122147.png?resize=607%2C478&ssl=1" alt="" class="wp-image-336" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-122147.png?w=607&ssl=1 607w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-122147.png?resize=300%2C236&ssl=1 300w" sizes="(max-width: 607px) 100vw, 607px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="523" height="478" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-122457.png?resize=523%2C478&ssl=1" alt="" class="wp-image-337" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-122457.png?w=523&ssl=1 523w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/Annotation-2022-09-23-122457.png?resize=300%2C274&ssl=1 300w" sizes="(max-width: 523px) 100vw, 523px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>This is what your multi-app kiosk device will look like:</strong></p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="359" height="478" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/20220923_102911000_iOS.png?resize=359%2C478&ssl=1" alt="" class="wp-image-338" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/20220923_102911000_iOS.png?w=359&ssl=1 359w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/20220923_102911000_iOS.png?resize=225%2C300&ssl=1 225w" sizes="(max-width: 359px) 100vw, 359px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="359" height="478" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/20220923_102948000_iOS-97cbaca.png?resize=359%2C478&ssl=1" alt="" class="wp-image-339" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/20220923_102948000_iOS-97cbaca.png?w=359&ssl=1 359w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/20220923_102948000_iOS-97cbaca.png?resize=225%2C300&ssl=1 225w" sizes="(max-width: 359px) 100vw, 359px" data-recalc-dims="1" /></figure>



<p>That’s all for this week. Stay safe and have a nice weekend 🍕🥂🍻</p>

<!--kg-card-end: html-->
