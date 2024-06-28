---
title: "macOS Management with Intune - Part IV"
date: 2022-10-31T00:27:45"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>Welcome to the next part of the macOS management series. In this post, I will help you deploy different apps to your corporate macOS devices.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Microsoft Edge</h2>



<p>You have the below-listed options to configure Edge as a managed browser on the MacBooks.</p>



<ol>
<li>Settings Catalog</li>



<li>Property List Files</li>



<li>Custom profiles</li>
</ol>



<h4>Settings Catalog</h4>



<p>It is the easiest and simplest way of configuring policies for Microsoft Edge, as Microsoft has now included almost every setting that can be configured for Edge in the Settings Catalog to make Edge your corporate-managed browser.</p>



<p>Login to Intune admin portal and navigate to <strong>Devices &gt; macOS &gt; Configuration Profile,</strong> and select <strong>Settings Catalog</strong> as profile type.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-84.png?resize=750%2C351&#038;ssl=1" alt="" class="wp-image-637" width="750" height="351" srcset="https://irlimages.blob.core.windows.net/images/image-84.png?resize=1024%2C479&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-84.png?resize=300%2C140&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-84.png?resize=768%2C359&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-84.png?resize=1536%2C719&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-84.png?resize=2048%2C958&amp;ssl=1 2048w, https://irlimages.blob.core.windows.net/images/image-84.png?w=2250&amp;ssl=1 2250w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>Property List Files</h4>



<p>A property list file known as a plist is a structured text file that contains essential configuration information for a bundled executable. The file contents are structured using XML, and its contents are a set of keys and values describing different aspects of the bundle. The system uses these keys and values to obtain information about your app and how it is configured. All bundled executables (plug-ins, frameworks, and apps) must have a property list file.</p>



<p>By convention, the name of an information property list file is Info.plist. The name of this file is case-sensitive and must have an initial capital letter <strong>I</strong>. This file resides in the top level of the bundle directory. In macOS bundles, this file resides in the bundle&#8217;s Contents directory. </p>



<p>The simplest way to create an Info.plist file is to use Xcode. To do so, Open<strong> Xcode </strong>on your Mac<strong> </strong>and<strong> Click File &gt; New.</strong></p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-85.png?resize=512%2C284&#038;ssl=1" alt="" class="wp-image-644" width="512" height="284" srcset="https://irlimages.blob.core.windows.net/images/image-85.png?resize=1024%2C568&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-85.png?resize=300%2C166&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-85.png?resize=768%2C426&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-85.png?w=1319&amp;ssl=1 1319w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>


<p>Now, select platform as macOS, resource as &#8220;<strong>Property List</strong>&#8220;, and keep the file name as <strong><em>com.microsoft.Edge.plist</em></strong>.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-86.png?resize=512%2C376&#038;ssl=1" alt="" class="wp-image-645" width="512" height="376" srcset="https://irlimages.blob.core.windows.net/images/image-86.png?resize=1024%2C751&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-86.png?resize=300%2C220&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-86.png?resize=768%2C563&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-86.png?resize=1536%2C1126&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-86.png?w=1850&amp;ssl=1 1850w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>


<p>Then you can configure all the settings you want for Edge as your corporate browser.</p>



<p>Do you need to try this hard to configure Edge? No!</p>



<p>Thanks to Microsoft for making our life easier. You can download the policy templates file from the <a href="https://aka.ms/EdgeEnterprise">Microsoft Edge Enterprise landing page</a>. It has an example plist file (<em>itadminexample.plist</em>), which contains all supported data types that you can customise to define your policy settings.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-87.png?resize=512%2C325&#038;ssl=1" alt="" class="wp-image-646" width="512" height="325" srcset="https://irlimages.blob.core.windows.net/images/image-87.png?resize=1024%2C650&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-87.png?resize=300%2C190&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-87.png?resize=768%2C487&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-87.png?resize=1536%2C975&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-87.png?w=1598&amp;ssl=1 1598w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-88.png?resize=750%2C113&#038;ssl=1" alt="" class="wp-image-647" width="750" height="113" srcset="https://irlimages.blob.core.windows.net/images/image-88.png?resize=1024%2C154&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-88.png?resize=300%2C45&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-88.png?resize=768%2C115&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-88.png?resize=1536%2C231&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-88.png?resize=2048%2C308&amp;ssl=1 2048w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p><strong>Save it as &#8220;<em>com.microsoft.Edge</em>.plist&#8221;</strong>. This name is case-sensitive and shouldn&#8217;t include the channel you&#8217;re targeting because it applies to all Microsoft Edge channels.</p>



<p>The next part is deploying the plist file to your target devices. Login to Intune portal, create a new device configuration profile for the macOS platform and select the&nbsp;Preference file&nbsp;profile type. Target&nbsp;com.microsoft.Edge&nbsp;as the preferred domain name and upload your list, which you just modified in the previous step.</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-89.png?resize=750%2C359&#038;ssl=1" alt="" class="wp-image-648" width="750" height="359" srcset="https://irlimages.blob.core.windows.net/images/image-89.png?resize=1024%2C491&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-89.png?resize=300%2C144&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-89.png?resize=768%2C368&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-89.png?resize=1536%2C736&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-89.png?w=1596&amp;ssl=1 1596w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption">Assign the profile to the device group, and Edge will be silently configured on those devices. </figcaption></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Deploying Microsoft 365 Apps</h2>



<p>Microsoft 365 for Mac, or Microsoft 365 apps for Mac as it&#8217;s now known, is a key part of any Microsoft 365 deployment or any macOS deployment in an organisation.</p>



<p>We can use three different mechanisms within Microsoft Intune to get&nbsp;Microsoft 365 Apps deployed to Macs. </p>



<ol>
<li>Mac App Store via Volume Purchase Program (VPP)</li>



<li>Microsoft Content Delivery Network</li>



<li>Intune Scripting Agent for Mac</li>
</ol>



<h3>Deploying Microsoft 365 Apps for Mac via Volume Purchase Program (VPP) <strong><em>(Not the recommended way)</em></strong></h3>



<p>This method requires an Apple VPP token configured with your Intune tenant. Before proceeding further, ensure that you&#8217;ve followed the steps documented <a href="__GHOST_URL__/add-distribute-manage-vpp-apps/" target="_blank" rel="noopener" title="">here</a>.</p>



<p>Once you have an Apple Business Manager VPP token synchronised with Intune, proceed further to assign Office Apps to your users.</p>



<ol>
<li>Open&nbsp;<a href="https://business.apple.com/#main/appsandbooks" target="_blank" rel="noreferrer noopener">https://business.apple.com/#main/appsandbooks</a></li>
</ol>



<ol start="2">
<li>Click in the search menu box, change the Type to &#8220;<strong>Mac</strong>&#8221; and search for &#8220;Microsoft&#8221;.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-95.png?resize=621%2C680&#038;ssl=1" alt="" class="wp-image-671" width="621" height="680" srcset="https://irlimages.blob.core.windows.net/images/image-95.png?w=828&amp;ssl=1 828w, https://irlimages.blob.core.windows.net/images/image-95.png?resize=274%2C300&amp;ssl=1 274w, https://irlimages.blob.core.windows.net/images/image-95.png?resize=768%2C840&amp;ssl=1 768w" sizes="(max-width: 621px) 100vw, 621px" data-recalc-dims="1" /></figure></div>


<ol start="3">
<li>Select the Application that you want to assign licenses.</li>
</ol>



<ol start="4">
<li>Assign the Application to your organisation and enter the number of licenses that you need. Since these apps have no cost, it makes sense to enter more licenses than you will need.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-96.png?resize=750%2C321&#038;ssl=1" alt="" class="wp-image-672" width="750" height="321" srcset="https://irlimages.blob.core.windows.net/images/image-96.png?resize=1024%2C438&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-96.png?resize=300%2C128&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-96.png?resize=768%2C328&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-96.png?w=1437&amp;ssl=1 1437w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="5">
<li>Once you have entered the values, click&nbsp;<strong>Get</strong>. The Application will temporarily show as Processing.</li>
</ol>



<ol start="6">
<li>Repeat the process for the other applications that you intend to use.</li>
</ol>



<ol start="8">
<li>Open Intune admin portal&nbsp;and select&nbsp;<strong>Tenant Administration</strong>&nbsp;&gt;&nbsp;<strong>Connectors and tokens</strong>&nbsp;&gt;&nbsp;<strong>Apple VPP Tokens</strong>.</li>
</ol>



<ol start="9">
<li>Select the Token you want to sync and click&nbsp;<strong>Sync</strong>&nbsp;in the ellipsis menu.</li>
</ol>



<ol start="10">
<li>In the Intune admin portal, navigate to&nbsp;Apps&nbsp;&gt;&nbsp;macOS, filter for unassigned apps, and then type &#8220;Microsoft&#8221; into the search bar.</li>
</ol>



<ol start="11">
<li>Select each app you wish to deploy and assign it to an Azure AD group.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-97.png?resize=750%2C230&#038;ssl=1" alt="" class="wp-image-673" width="750" height="230" srcset="https://irlimages.blob.core.windows.net/images/image-97.png?resize=1024%2C315&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-97.png?resize=300%2C92&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-97.png?resize=768%2C236&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-97.png?w=1218&amp;ssl=1 1218w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<h3>Deploying Microsoft 365 Apps for Mac via the Microsoft Content Delivery Network (<strong><em>Recommended way</em></strong>)</h3>



<p>This mechanism is supported natively by Intune and is as simple as checking a box and providing a group of users to deploy it. Those users will receive the entire Microsoft 365 Apps (which includes Teams and the Microsoft Auto update tool).</p>



<ul>
<li>Open Intune admin portal, select&nbsp;<strong>Apps</strong>&nbsp;&gt;&nbsp;<strong>macOS</strong>&nbsp;&gt;&nbsp;<strong>Add</strong></li>
</ul>



<ul>
<li>Under Select &#8220;<strong>App Type</strong>&#8221; choose&nbsp;<strong>Microsoft 365 Apps</strong>&nbsp;&gt;&nbsp;<strong>macOS</strong></li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-99.png?resize=750%2C263&#038;ssl=1" alt="" class="wp-image-675" width="750" height="263" srcset="https://irlimages.blob.core.windows.net/images/image-99.png?resize=1024%2C358&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-99.png?resize=300%2C105&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-99.png?resize=768%2C269&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-99.png?resize=1536%2C537&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-99.png?w=1596&amp;ssl=1 1596w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Review the apps and add as Required&nbsp;apps to the appropriate device group.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-103.png?resize=750%2C157&#038;ssl=1" alt="" class="wp-image-679" width="750" height="157" srcset="https://irlimages.blob.core.windows.net/images/image-103.png?resize=1024%2C214&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-103.png?resize=300%2C63&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-103.png?resize=768%2C161&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-103.png?w=1213&amp;ssl=1 1213w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<h3>Deploying Microsoft 365 Apps for Mac via the Intune Scripting Agent for Mac</h3>



<p>This approach uses the&nbsp;Intune scripting agent&nbsp;to download and install the Office suite or individual apps. </p>



<p>You can download the scripts from <a href="https://github.com/microsoft/shell-intune-samples" target="_blank" rel="noopener" title="">Microsoft GitHub Repo</a>:</p>



<ol>
<li><a href="https://github.com/microsoft/shell-intune-samples/blob/master/Apps/Office%20for%20Mac/installOfficeBusinessPro.sh" target="_blank" rel="noreferrer noopener">Deploy entire Office Suite</a></li>



<li><a href="https://github.com/microsoft/shell-intune-samples/blob/master/Apps/Office%20for%20Mac/installOfficeSuiteInidividualApps.sh" target="_blank" rel="noreferrer noopener">Deploy individual Office Suite apps</a></li>
</ol>



<p>These two scripts do the same thing. Once deployed onto the Mac, they attempt to download the installer package and install it. </p>



<ul>
<li>Download a copy of our sample file&nbsp;<a href="https://raw.githubusercontent.com/microsoft/shell-intune-samples/master/Apps/Office%20for%20Mac/installOfficeSuiteInidividualApps.sh" target="_blank" rel="noreferrer noopener">installOfficeSuiteIndividualApps.sh</a>&nbsp;and save it to your device.</li>
</ul>



<ul>
<li>Open the file in your text editor of choice and modify the AppsToInstall array only to include Outlook, Word, PowerPoint and OneDrive.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-104.png?resize=750%2C102&#038;ssl=1" alt="" class="wp-image-680" width="750" height="102" srcset="https://irlimages.blob.core.windows.net/images/image-104.png?resize=1024%2C139&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-104.png?resize=300%2C41&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-104.png?resize=768%2C104&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-104.png?w=1160&amp;ssl=1 1160w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Mark the script as executable by opening a Terminal session and using the chmod +x command.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-105.png?resize=750%2C35&#038;ssl=1" alt="" class="wp-image-681" width="750" height="35" srcset="https://irlimages.blob.core.windows.net/images/image-105.png?w=1017&amp;ssl=1 1017w, https://irlimages.blob.core.windows.net/images/image-105.png?resize=300%2C14&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-105.png?resize=768%2C36&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Open the&nbsp;Intune admin portal and&nbsp;navigate to <strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>macOS</strong>&nbsp;&gt;&nbsp;<strong>Shell Scripts</strong>&nbsp;&gt;&nbsp;<strong>Add</strong></li>
</ul>



<ul>
<li>Enter a&nbsp;<em>Name and Description</em>&nbsp;and click&nbsp;<strong>Next</strong>.</li>
</ul>



<ul>
<li>Click the file browse UI in the Upload script dialog and select the saved file.
<ul>
<li>Run script as signed-in user = No</li>



<li>Hide script notifications on device = Not configured</li>



<li>Script frequency = Not configured</li>



<li>Set the Max number of retries to 3, Run and leave the rest as not configured</li>
</ul>
</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-106.png?resize=299%2C143&#038;ssl=1" alt="" class="wp-image-682" width="299" height="143" srcset="https://irlimages.blob.core.windows.net/images/image-106.png?w=399&amp;ssl=1 399w, https://irlimages.blob.core.windows.net/images/image-106.png?resize=300%2C144&amp;ssl=1 300w" sizes="(max-width: 299px) 100vw, 299px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Assign the script to the device group.</li>
</ul>



<p>The Intune script agent runs on an 8hr check-in cycle but can be manually triggered by the end user.</p>



<ol>
<li>Open the Company Portal app (sign in if prompted).</li>



<li>Select the device you are using.</li>



<li>Click&nbsp;<strong>Check Settings</strong>&nbsp;under the ellipses menu.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-107.png?resize=750%2C209&#038;ssl=1" alt="" class="wp-image-683" width="750" height="209" srcset="https://irlimages.blob.core.windows.net/images/image-107.png?resize=1024%2C285&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-107.png?resize=300%2C83&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-107.png?resize=768%2C214&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-107.png?w=1219&amp;ssl=1 1219w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p>There are no right and wrong with these three approaches, and each is applicable in certain circumstances. However, the recommended way to deploy M365 apps to your Macs is by using the CDN approach, as it provides the best mixture of complexity and flexibility and is the easiest to support for most scenarios.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Summary</h2>



<p>With this, I will end the series as we have configured all the policies and profiles required for enrolling and managing macOS devices with Intune. We have also configured Microsoft Edge and M365 apps as required apps to make your users productive immediately after device provisioning.</p>



<p>I hope this will help you to manage the Macs more effectively.</p>



<p>Keep learning and stay #intuneinspired.</p>
<!--kg-card-end: html-->