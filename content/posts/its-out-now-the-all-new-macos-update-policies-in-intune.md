---
title: "It's Out Now! The All New macOS Update Policies in Intune"
date: 2022-10-20T21:38:35"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<h2>Overview</h2>



<p>The feature all Intune admins managing corporate macOS devices have been waiting for a long is out! </p>



<p>It appeared on my test tenant, and I could not resist myself to test it out. Let me take you through all these brand-new features and help you configure the policies in Intune to manage macOS software updates for enrolled devices using Automated Device Enrollment (ADE).</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>What&#8217;s new</h2>



<p>With this new feature, you will now be able to configure the below update types will include:</p>



<ol><li>Critical updates</li><li>Firmware updates</li><li>Configuration file updates</li><li>All other updates (OS, built-in apps)</li></ol>



<p>In addition to scheduling when a device receives the updates, you’ll be able to manage the following features:</p>



<ol><li><strong>Download and Install</strong>: Download or install the update, depending on the current state.</li><li><strong>Download only</strong>: Download the software update without installing it.</li><li><strong>Install immediately</strong>: Download the software update and trigger the restart countdown notification.</li><li><strong>Notify only</strong>: Download the software update and notify the user through the App Store.</li><li><strong>Install later</strong>: Download the software update and install it at a later time.</li><li><strong>Not configured</strong>: No action was taken on the software update.</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Updates and Upgrades</h2>



<p>Apple operating systems use a version numbering scheme to distinguish major upgrades from minor updates. Unlike iOS/iPadOS/TV OS, <strong>macOS uses a simple integer (for example, macOS 11 and macOS 12)</strong> <strong>with a name</strong> like Big Sur and Monterey. </p>



<p>Upgrades are released much less frequently than updates and can take a while to install because of their large size. In comparison, updates are more frequently released patches for the current operating system and help protect the device against vulnerabilities. <strong><span style="text-decoration: underline;">Updates use a second and sometimes a third number to denote increments. For example,&nbsp;iOS 15.1&nbsp;is an update to&nbsp;iOS 15.</span></strong></p>



<p>With this new feature, Intune allows you to manage, download, install, or even defer macOS software upgrades and updates remotely.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>The Magic Behind These Updates</h2>



<p>The MDM solution (Intune) uses the Apple Software Lookup service to be aware of available updates to push the update commands directly to the device. </p>



<p><strong>Earlier Approach:</strong></p>



<ol><li>First, the MDM server gets a list of available updates from Apple, and when the policy is configured and applied correctly, the MDM will send the updated version to the device. </li><li>Then the device goes to the Apple lookup server to verify if the update is eligible and begins downloading and installing it.</li></ol>



<p><strong>New Approach:</strong></p>



<ol><li>Apple introduced a new workflow for both macOS &amp; iOS by introducing a new command &#8220;SofwtareUpdateModeIID&#8221; key. This key returns the hardware model ID to Intune. </li><li>The Apple lookup software service will look for the appropriate hardware ID match for macOS, allowing Intune to determine the applicable updates without using the old approach of the AvailabelOSUpdates command.</li><li>Intune will then determine the update applicability by comparing the result from the DeviceInformation query to the deviceID returned in the same query.</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>Once Intune knows which OS update applies to devices, the ScheduleOSUpdate command is used to push to update the macOS. Intune can trigger this command even during a software deferral window also. The five options available now for macOS have their own significance; let&#8217;s understand the logic behind each of them:</p>



<h3>Download and Install (Immediately)</h3>



<pre class="wp-block-code has-medium-font-size"><code>Thumb Rule: Avoid It!</code></pre>



<p>The <strong><em>InstallASAP</em> </strong>command is the default mechanism for the <strong>ScheduleOSUpdate</strong> command, with a default for <strong>InstallAction </strong>to download the updates. It downloads the software update and triggers the restart countdown notification. This command may require a restart (if the InstallForceRestart option is used). This may result in data loss on the end user&#8217;s device.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-59.png?resize=750%2C472&#038;ssl=1" alt="" class="wp-image-574" width="750" height="472" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-59.png?resize=1024%2C644&amp;ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-59.png?resize=300%2C189&amp;ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-59.png?resize=768%2C483&amp;ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-59.png?w=1214&amp;ssl=1 1214w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3><strong>Download Only</strong></h3>



<p>This command downloads the software update in the background without installing it on the device. It will not start the installation. </p>



<p>All these requests are in json format. Below is the example of a device requesting an update and the response given back:</p>



<p><strong><span style="text-decoration: underline;">Request Update:</span></strong></p>



<pre class="wp-block-code"><code>&lt;?xml version="1.0" encoding="UTF-8"?>
&lt;!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
&lt;plist version="1.0">
&lt;dict>
    &lt;key>Command&lt;/key>
    &lt;dict>
        &lt;key>RequestType&lt;/key>
        &lt;string>ScheduleOSUpdate&lt;/string>
        &lt;key>Updates&lt;/key>
        &lt;array>
            &lt;dict>
                &lt;key>InstallAction&lt;/key>
                &lt;string>DownloadOnly&lt;/string>
                &lt;key>ProductKey&lt;/key>
                &lt;string>iOSUpdate17A576&lt;/string>
                &lt;key>ProductVersion&lt;/key>
                &lt;string>13.0&lt;/string>
            &lt;/dict>
        &lt;/array>
    &lt;/dict>
    &lt;key>CommandUUID&lt;/key>
    &lt;string>0001_ScheduleOSUpdate&lt;/string>
&lt;/dict>
&lt;/plist></code></pre>



<pre class="wp-block-code"><code><strong><span style="text-decoration: underline;">Request Update:</span></strong>

&lt;?xml version="1.0" encoding="UTF-8"?>
&lt;!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
&lt;plist version="1.0">
&lt;dict>
    &lt;key>CommandUUID&lt;/key>
    &lt;string>0001_ScheduleOSUpdate&lt;/string>
    &lt;key>Status&lt;/key>
    &lt;string>Acknowledged&lt;/string>
    &lt;key>UDID&lt;/key>
    &lt;string>00008020-000915083C80012E&lt;/string>
    &lt;key>UpdateResults&lt;/key>
    &lt;array>
        &lt;dict>
            &lt;key>InstallAction&lt;/key>
            &lt;string>DownloadOnly&lt;/string>
            &lt;key>ProductKey&lt;/key>
            &lt;string>iOSUpdate17A576&lt;/string>
            &lt;key>Status&lt;/key>
            &lt;string>Downloading&lt;/string>
        &lt;/dict>
    &lt;/array>
&lt;/dict>
&lt;/plist></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3>Notify only</h3>



<p>Notify only alerts users that there is an action pending for installation. The user is notified about the software update through the <strong>App Store</strong>. It will also not start the installation.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3>Install Later</h3>



<p>It will allow you to schedule the installation later tonight. <strong>The device will usually choose a time between 02:00 and 04:00</strong> based on when the machine is least used to allow the update to install. The update will only install if the device is plugged into the power source.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-60.png?resize=750%2C466&#038;ssl=1" alt="" class="wp-image-575" width="750" height="466" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-60.png?resize=1024%2C636&amp;ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-60.png?resize=300%2C186&amp;ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-60.png?resize=768%2C477&amp;ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-60.png?w=1222&amp;ssl=1 1222w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Conclusion</h2>



<p>I hope this article has been insightful in giving you a detailed understanding of how Intune &amp; Apple help you to update your devices. Follow the <strong>three-step approach</strong> and keep your macOS devices updated with all the latest patches &amp; updates. Recommended approach:</p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="631" height="287" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-61.png?resize=631%2C287&#038;ssl=1" alt="" class="wp-image-576" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-61.png?w=631&amp;ssl=1 631w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/image-61.png?resize=300%2C136&amp;ssl=1 300w" sizes="(max-width: 631px) 100vw, 631px" data-recalc-dims="1" /></figure>



<p>Keep learning and keep sharing. </p>



<p>Stay In(tuned). #intuneinspired</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>

<!--kg-card-end: html-->
