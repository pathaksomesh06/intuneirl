---
title: "Zero Touch Onboarding & Activation of Microsoft Defender for Endpoint"
date: 2022-11-17T14:55:46"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>You can now configure your iOS devices to be silently onboarded and activated on Microsoft Defender for Endpoint without requiring interaction from the end user. In this flow, you will create a few configuration profiles, and the user will be notified of the installation. Defender for Endpoint is automatically installed and activated without the user needing to open the app. Follow the steps below to set up zero-touch or silent deployment and activation of Defender for Endpoint on enrolled iOS devices:</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Pre-requisites</h2>



<ul>
<li>Access to Intune portal</li>



<li>Access to Apple Business Manager</li>



<li>Devices are enrolled in Intune</li>



<li>Defender for Endpoint license is assigned to the user</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Deploy the App</h2>



<p>You have two options for deploying MDE app to your user&#8217;s devices:</p>



<blockquote class="wp-block-quote">
<ol>
<li>App Store App</li>



<li>VPP App</li>
</ol>
</blockquote>



<h3>Deploy Defender as App Store App</h3>



<ul>
<li>In&nbsp;<a href="https://go.microsoft.com/fwlink/?linkid=2109431">Intune portal</a>, go to&nbsp;<strong>Apps</strong>&nbsp;&gt;&nbsp;<strong>iOS/iPadOS</strong>&nbsp;&gt;&nbsp;<strong>Add</strong>&nbsp;&gt;&nbsp;<strong>iOS store app</strong>&nbsp;and click&nbsp;<strong>Select</strong>.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-64.png?resize=750%2C559&#038;ssl=1" alt="" class="wp-image-884" width="750" height="559" srcset="https://irlimages.blob.core.windows.net/2022-11/image-64.png?resize=1024%2C763&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-64.png?resize=300%2C224&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-64.png?resize=768%2C572&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-64.png?w=1255&amp;ssl=1 1255w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Select the app as public store app</em></figcaption></figure></div>


<ul>
<li>Click on Search the App Store on the Add app page and type&nbsp;<strong>Microsoft Defender</strong>&nbsp;in the search bar. In the search results section, click on&nbsp;<em>Microsoft Defender</em>&nbsp;and click&nbsp;<strong>Select</strong>.</li>
</ul>



<ul>
<li>Select&nbsp;<strong>iOS 12.0</strong>&nbsp;as the Minimum operating system. Review the rest of the information about the app and click&nbsp;<strong>Next</strong>.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-65.png?resize=750%2C705&#038;ssl=1" alt="" class="wp-image-885" width="750" height="705" srcset="https://irlimages.blob.core.windows.net/2022-11/image-65.png?w=1016&amp;ssl=1 1016w, https://irlimages.blob.core.windows.net/2022-11/image-65.png?resize=300%2C282&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-65.png?resize=768%2C721&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>app info</em></figcaption></figure></div>


<ul>
<li>In the&nbsp;<strong>Assignments</strong>&nbsp;section, go to the&nbsp;<strong>Required</strong>&nbsp;section and select&nbsp;<strong>Add group</strong>. You can then choose the user group(s) you would like to target Defender for Endpoint on the iOS app. Click&nbsp;<strong>Select</strong>&nbsp;and then&nbsp;<strong>Next</strong>.</li>
</ul>



<h3>Deploy Defender as VPP App (Recommended way)</h3>



<ul>
<li>Log in to Apple Business Manager and click&nbsp;<strong>Apps and Books</strong>, then search for &#8220;Microsoft </li>



<li>defender&#8221; in the app or book in the search field.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-66.png?resize=750%2C289&#038;ssl=1" alt="" class="wp-image-886" width="750" height="289" srcset="https://irlimages.blob.core.windows.net/2022-11/image-66.png?resize=1024%2C394&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-66.png?resize=300%2C115&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-66.png?resize=768%2C295&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-66.png?resize=1536%2C590&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/image-66.png?w=1782&amp;ssl=1 1782w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Add app in ABM</em></figcaption></figure></div>


<ul>
<li>&nbsp;Select the app or book in the search results list that you want to purchase.</li>
</ul>



<ul>
<li>Select the&nbsp;<strong>location&nbsp;</strong>where the app or book licenses will be initially assigned.</li>
</ul>



<ul>
<li>Enter the number of licenses, and if necessary, change the payment method, then click<strong>&nbsp;Buy</strong></li>
</ul>



<blockquote class="wp-block-quote">
<p>Availability of app licenses depends on the amount purchased. If you purchased:</p>



<ul>
<li>5000 licenses or fewer, they are immediately processed</li>



<li>5001 to 19,999 licenses, they are processed daily after 1:00 p.m., Pacific time</li>



<li>20,000 licenses or more, they are processed daily after 4:00 p.m., Pacific time</li>
</ul>
</blockquote>



<ul>
<li>Force sync your VPP token in Intune to immediately sync for processing the purchase.</li>
</ul>



<ul>
<li>Log in to&nbsp;<a href="https://endpoint.microsoft.com/" target="_blank" rel="noreferrer noopener">Intune portal</a>.&nbsp;</li>
</ul>



<ul>
<li>Select&nbsp;<strong>Apps</strong>&nbsp;&gt;&nbsp;<strong>All apps</strong>.</li>
</ul>



<ul>
<li>On the list of apps pane, choose the app you want to assign and then choose&nbsp;<strong>Properties&nbsp;</strong></li>
</ul>



<ul>
<li>On the&nbsp;<strong>Assignments</strong>&nbsp;tab, choose whether the app will be&nbsp;<strong>Required</strong>&nbsp;or&nbsp;<strong>Available for enrolled devices.</strong></li>
</ul>



<ul>
<li>Assing it to<strong>&nbsp;</strong>the&nbsp;groups you want to assign the app.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Configure Supervised Mode via Intune</h2>



<p>For configuring the supervised mode for Defender for Endpoint app, we would need an app configuration policy and device configuration profile. Follow the below steps to configure them:</p>



<h3>App Configuration Policy</h3>



<ul>
<li>Sign in to the&nbsp;Intune portal&nbsp;and go to&nbsp;<strong>Apps</strong>&nbsp;&gt;&nbsp;<strong>App configuration policies</strong>&nbsp;&gt;&nbsp;<strong>Add</strong>. Select&nbsp;<strong>Managed devices</strong>.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-67.png?resize=750%2C391&#038;ssl=1" alt="" class="wp-image-887" width="750" height="391" srcset="https://irlimages.blob.core.windows.net/2022-11/image-67.png?resize=1024%2C533&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-67.png?resize=300%2C156&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-67.png?resize=768%2C400&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-67.png?w=1139&amp;ssl=1 1139w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>App configuration policy</em></figcaption></figure></div>


<ul>
<li>In the&nbsp;<em>Create app configuration policy</em>&nbsp;page, provide the following information:
<ul>
<li>Policy Name</li>



<li>Platform: Select iOS/iPadOS</li>



<li>Targeted app: Select&nbsp;<strong>Microsoft Defender for Endpoint</strong>&nbsp;from the list</li>
</ul>
</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-68.png?resize=750%2C403&#038;ssl=1" alt="" class="wp-image-888" width="750" height="403" srcset="https://irlimages.blob.core.windows.net/2022-11/image-68.png?resize=1024%2C550&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-68.png?resize=300%2C161&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-68.png?resize=768%2C412&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-68.png?resize=1536%2C825&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/image-68.png?w=2000&amp;ssl=1 2000w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>add the app</em></figcaption></figure></div>


<ul>
<li>In the next screen, select&nbsp;<strong>Use configuration designer</strong>&nbsp;as the format. Specify the following properties:
<ul>
<li>Configuration Key:&nbsp;<code>issupervised</code></li>



<li>Value type: String</li>



<li>Configuration Value:&nbsp;<code>{{issupervised}}</code></li>
</ul>
</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-69.png?resize=750%2C441&#038;ssl=1" alt="" class="wp-image-889" width="750" height="441" srcset="https://irlimages.blob.core.windows.net/2022-11/image-69.png?resize=1024%2C602&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-69.png?resize=300%2C176&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-69.png?resize=768%2C452&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-69.png?resize=1536%2C903&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/image-69.png?w=1646&amp;ssl=1 1646w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Assign the policy to the same group to which the app is assigned.</li>
</ul>



<h3>Device Configuration Profile</h3>



<p>This profile is for enabling enhanced Anti-phishing capabilities. Follow the steps below:</p>



<ul>
<li>Download the config profile from&nbsp;<a href="https://aka.ms/mdeiosprofilesupervised">https://aka.ms/mdeiosprofilesupervised</a>.</li>
</ul>



<ul>
<li>Navigate to&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>iOS/iPadOS</strong>&nbsp;&gt;&nbsp;<strong>Configuration profiles</strong>&nbsp;&gt;&nbsp;<strong>Create Profile</strong></li>
</ul>



<ul>
<li>Select&nbsp;<strong>Profile Type</strong>&nbsp;&gt;&nbsp;<strong>Templates</strong>&nbsp;and&nbsp;<strong>Template name</strong>&nbsp;&gt;&nbsp;<strong>Custom</strong></li>
</ul>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-70.png?resize=715%2C348&#038;ssl=1" alt="" class="wp-image-890" width="715" height="348" srcset="https://irlimages.blob.core.windows.net/2022-11/image-70.png?w=953&amp;ssl=1 953w, https://irlimages.blob.core.windows.net/2022-11/image-70.png?resize=300%2C146&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-70.png?resize=768%2C374&amp;ssl=1 768w" sizes="(max-width: 715px) 100vw, 715px" data-recalc-dims="1" /></figure>



<ul>
<li>Provide the name of the profile. When prompted to import a Configuration profile file, select the one downloaded from the previous step.</li>
</ul>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-71.png?resize=702%2C372&#038;ssl=1" alt="" class="wp-image-891" width="702" height="372" srcset="https://irlimages.blob.core.windows.net/2022-11/image-71.png?w=936&amp;ssl=1 936w, https://irlimages.blob.core.windows.net/2022-11/image-71.png?resize=300%2C159&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-71.png?resize=768%2C407&amp;ssl=1 768w" sizes="(max-width: 702px) 100vw, 702px" data-recalc-dims="1" /></figure>



<ul>
<li>Assign the policy to the same group to which APP is assigned.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Zero-touch Onboarding &amp; Activation</h2>



<ul>
<li>In&nbsp;Intune portal, go to&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>Configuration Profiles</strong>&nbsp;&gt;&nbsp;<strong>Create Profile</strong>.</li>
</ul>



<ul>
<li>Choose&nbsp;<strong>Platform</strong>&nbsp;as&nbsp;<strong>iOS/iPadOS</strong>&nbsp;and&nbsp;<strong>Profile type</strong>&nbsp;as&nbsp;<strong>VPN</strong>. Select&nbsp;<strong>Create</strong>.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-72.png?resize=512%2C445&#038;ssl=1" alt="" class="wp-image-892" width="512" height="445" srcset="https://irlimages.blob.core.windows.net/2022-11/image-72.png?resize=1024%2C890&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-72.png?resize=300%2C261&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-72.png?resize=768%2C668&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-72.png?w=1071&amp;ssl=1 1071w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Type a name for the profile and select&nbsp;<strong>Next</strong>.</li>
</ul>



<ul>
<li>Select&nbsp;<strong>Custom VPN</strong>&nbsp;for Connection Type and in the&nbsp;<strong>Base VPN</strong>&nbsp;section, enter the following:
<ul>
<li>Connection Name = Microsoft Defender for Endpoint</li>



<li>VPN server address = 127.0.0.1</li>



<li>Auth method = &#8220;Username and password&#8221;</li>



<li>Split Tunneling = Disable</li>



<li>VPN identifier = com.microsoft.scmx</li>



<li>In the key-value pairs, enter the key&nbsp;<strong>SilentOnboard</strong>&nbsp;and set the value to&nbsp;<strong>True</strong>.</li>



<li>Type of Automatic VPN = On-demand VPN</li>



<li>Select&nbsp;<strong>Add</strong>&nbsp;for&nbsp;<strong>On Demand Rules</strong>&nbsp;and select&nbsp;<strong>I want to do the following = Connect VPN</strong>,&nbsp;<strong>I want to restrict to = All domains</strong>.</li>
</ul>
</li>
</ul>



<blockquote class="wp-block-quote">
<p>The configurations for the custom vpn profile are case sensitive. Any slight mistake will disable auto-activation of MDE.</p>
</blockquote>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-73.png?resize=657%2C437&#038;ssl=1" alt="" class="wp-image-893" width="657" height="437" srcset="https://irlimages.blob.core.windows.net/2022-11/image-73.png?w=876&amp;ssl=1 876w, https://irlimages.blob.core.windows.net/2022-11/image-73.png?resize=300%2C200&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-73.png?resize=768%2C511&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-73.png?resize=360%2C240&amp;ssl=1 360w" sizes="(max-width: 657px) 100vw, 657px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>End User Experience</h2>



<p>The VPN configuration profile is pushed to the device as soon as the device is enrolled. Until Microsoft Defender is installed and activated on the device, the connection is just a self-loop.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-81.png?resize=562%2C665&#038;ssl=1" alt="" class="wp-image-901" width="562" height="665" srcset="https://irlimages.blob.core.windows.net/2022-11/image-81.png?w=749&amp;ssl=1 749w, https://irlimages.blob.core.windows.net/2022-11/image-81.png?resize=254%2C300&amp;ssl=1 254w" sizes="(max-width: 562px) 100vw, 562px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-82.png?resize=557%2C392&#038;ssl=1" alt="" class="wp-image-902" width="557" height="392" srcset="https://irlimages.blob.core.windows.net/2022-11/image-82.png?w=742&amp;ssl=1 742w, https://irlimages.blob.core.windows.net/2022-11/image-82.png?resize=300%2C211&amp;ssl=1 300w" sizes="(max-width: 557px) 100vw, 557px" data-recalc-dims="1" /></figure></div>


<p>You will see the blue dot on the MDE app icon within a few minutes and a notification in the device&#8217;s notification center that the device has been successfully onboarded to MDE.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-77.png?resize=404%2C158&#038;ssl=1" alt="" class="wp-image-897" width="404" height="158" srcset="https://irlimages.blob.core.windows.net/2022-11/image-77.png?w=538&amp;ssl=1 538w, https://irlimages.blob.core.windows.net/2022-11/image-77.png?resize=300%2C118&amp;ssl=1 300w" sizes="(max-width: 404px) 100vw, 404px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Device silently onboarded</em></figcaption></figure></div>


<p>Tap the Defender for Endpoint app icon (MSDefender),&nbsp;and you will notice that the app is activated with web protection auto-enabled.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-78.png?resize=560%2C733&#038;ssl=1" alt="" class="wp-image-898" width="560" height="733" srcset="https://irlimages.blob.core.windows.net/2022-11/image-78.png?w=746&amp;ssl=1 746w, https://irlimages.blob.core.windows.net/2022-11/image-78.png?resize=229%2C300&amp;ssl=1 229w" sizes="(max-width: 560px) 100vw, 560px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-79.png?resize=552%2C485&#038;ssl=1" alt="" class="wp-image-899" width="552" height="485" srcset="https://irlimages.blob.core.windows.net/2022-11/image-79.png?w=736&amp;ssl=1 736w, https://irlimages.blob.core.windows.net/2022-11/image-79.png?resize=300%2C263&amp;ssl=1 300w" sizes="(max-width: 552px) 100vw, 552px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-80.png?resize=568%2C329&#038;ssl=1" alt="" class="wp-image-900" width="568" height="329" srcset="https://irlimages.blob.core.windows.net/2022-11/image-80.png?w=757&amp;ssl=1 757w, https://irlimages.blob.core.windows.net/2022-11/image-80.png?resize=300%2C174&amp;ssl=1 300w" sizes="(max-width: 568px) 100vw, 568px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Wrapping-Up</h2>



<p>When looking from the end-user perspective, the experience is super cool. <strong>No interaction is required, as the onboarding and activation are 100% silent.</strong></p>



<p>At the same time, from the administrator&#8217;s perspective, these features give you complete visibility of the device&#8217;s security, and the ease of onboarding devices is also what we have been looking forward from many years. I hope that Android Enterprise will also have the same experience soon.</p>



<p class="has-small-font-size"><em>Ref</em>: </p>



<p class="has-small-font-size"><a href="https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/ios-install?view=o365-worldwide#zero-touch-onboarding-of-microsoft-defender-for-endpoint/?WT.mc_id=EM-MVP-5004955">App-based deployment for Microsoft Defender for Endpoint on iOS | Microsoft Learn</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!--kg-card-end: html-->