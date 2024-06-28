---
title: "macOS Management with Intune - Part II"
date: 2022-10-20T17:20:03"
draft: false
tags: []
---

<!--kg-card-begin: html--><p>Part two of the macOS management series, and we will configure the policies &amp; profiles for <strong>silent onboarding of mac OS devices in Microsoft Defender for Endpoint</strong> along with pushing the Company Portal app on the device.</p>

<hr class="wp-block-separator has-alpha-channel-opacity"/>

<p>Before creating any macOS policy, let us first configure MDE. Log in to Security Center and enable the connection for Defender. I will use MDE as an enterprise security platform for securing corporate devices.</p>

<hr class="wp-block-separator has-alpha-channel-opacity"/>

<h3 id="configure-microsoft-defender-for-endpoint-in-intune">Configure Microsoft Defender for Endpoint in Intune</h3>

<p>The first step is to set up the communication between Intune and Microsoft Defender for Endpoint:</p>


<ol><li>In <strong>Microsoft 365 Defender</strong>; Select <a href="https://security.microsoft.com/preferences2/integration"><strong>Settings</strong> > <strong>Endpoints</strong> > <strong>Advanced features</strong></a>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-37.png?resize=750%2C263&#038;ssl=1" alt="" class="wp-image-537" width="750" height="263" srcset="https://irlimages.blob.core.windows.net/images/image-37.png?resize=1024%2C359&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-37.png?resize=300%2C105&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-37.png?resize=768%2C269&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-37.png?resize=1536%2C539&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-37.png?w=1905&amp;ssl=1 1905w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="2"><li>For&nbsp;<strong>Microsoft Intune connection</strong>, choose&nbsp;<strong>On</strong>:</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-38.png?resize=750%2C81&#038;ssl=1" alt="" class="wp-image-538" width="750" height="81" srcset="https://irlimages.blob.core.windows.net/images/image-38.png?resize=1024%2C110&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-38.png?resize=300%2C32&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-38.png?resize=768%2C82&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-38.png?w=1527&amp;ssl=1 1527w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>Return to&nbsp;<strong>Microsoft Defender for the Endpoint</strong>&nbsp;page in the Intune portal, and the connector status should be &#8220;Enabled.&#8221;</li></ol>


<hr class="wp-block-separator has-alpha-channel-opacity"/>

<p class="has-medium-font-size"><strong>Deploy Microsoft Defender for Endpoint on macOS</strong></p>


<p>Deployment of MDE on your macOS devices is a bit complicated process. You will first need to download the onboarding package, approve the extension and then configure a few more policies. The below five steps are required for onboarding your macOS in MDE:</p>


<ol><li>Download the onboarding package</li><li>Client device setup</li><li>Approve system extensions</li><li>Create System Configuration profiles</li><li>Publish application</li></ol>


<hr class="wp-block-separator has-alpha-channel-opacity"/>

<h3>Download the Onboarding Package</h3>

<ol><li>In Microsoft 365 Defender portal, go to Settings &gt; Endpoints &gt; Device management &gt; Onboarding.</li></ol>


<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-40.png?resize=701%2C629&#038;ssl=1" alt="" class="wp-image-541" width="701" height="629" srcset="https://irlimages.blob.core.windows.net/images/image-40.png?w=934&amp;ssl=1 934w, https://irlimages.blob.core.windows.net/images/image-40.png?resize=300%2C269&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-40.png?resize=768%2C690&amp;ssl=1 768w" sizes="(max-width: 701px) 100vw, 701px" data-recalc-dims="1" /></figure>


<ol start="2"><li>Set the operating system to macOS and the deployment method to Mobile Device Management / Microsoft Intune.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-41.png?resize=750%2C505&#038;ssl=1" alt="" class="wp-image-542" width="750" height="505" srcset="https://irlimages.blob.core.windows.net/images/image-41.png?resize=1024%2C689&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-41.png?resize=300%2C202&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-41.png?resize=768%2C517&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-41.png?w=1094&amp;ssl=1 1094w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>Select Download onboarding package. Save it as <strong>WindowsDefenderATPOnboardingPackage.zip</strong> to the same directory.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.41.35.png?resize=750%2C383&#038;ssl=1" alt="" class="wp-image-544" width="750" height="383" srcset="https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.41.35.png?resize=1024%2C523&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.41.35.png?resize=300%2C153&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.41.35.png?resize=768%2C392&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.41.35.png?resize=1536%2C784&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.41.35.png?resize=2048%2C1045&amp;ssl=1 2048w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.41.35.png?w=2250&amp;ssl=1 2250w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="4"><li>Extract the contents of the .zip file</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.22.png?resize=750%2C443&#038;ssl=1" alt="" class="wp-image-545" width="750" height="443" srcset="https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.22.png?resize=1024%2C605&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.22.png?resize=300%2C177&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.22.png?resize=768%2C453&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.22.png?resize=1536%2C907&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.22.png?resize=2048%2C1209&amp;ssl=1 2048w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p>The zip contains the onboarding files for MDM solutions. But as we are using Intune as an MDM solution, so will focus on the folder named &#8220;Intune&#8221;.</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.54.png?resize=750%2C441&#038;ssl=1" alt="" class="wp-image-546" width="750" height="441" srcset="https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.54.png?resize=1024%2C603&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.54.png?resize=300%2C177&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.54.png?resize=768%2C453&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.54.png?resize=1536%2C905&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/Screenshot-2022-10-20-at-09.43.54.png?w=2045&amp;ssl=1 2045w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3>Create System Configuration profiles</h3>



<p>As the next step, we will create configuration profiles for Microsoft Defender for Endpoint. The steps are as below:</p>



<ol><li>Log in to Intune portal, navigate to <strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>macOS Devices</strong> &gt; <strong>Configuration profiles</strong> &gt; <strong>Create Profile</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-43.png?resize=750%2C225&#038;ssl=1" alt="" class="wp-image-548" width="750" height="225" srcset="https://irlimages.blob.core.windows.net/images/image-43.png?resize=1024%2C306&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-43.png?resize=300%2C90&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-43.png?resize=768%2C229&amp;ssl=1 768w, hhttps://irlimages.blob.core.windows.net/images/image-43.png?resize=1536%2C459&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-43.png?w=1624&amp;ssl=1 1624w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="2"><li>Select <strong>Profile type</strong> as <strong>Templates and Template name</strong> as <strong>Custom</strong>. Click&nbsp;<strong>Create</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-44.png?resize=750%2C462&#038;ssl=1" alt="" class="wp-image-549" width="750" height="462" srcset="https://irlimages.blob.core.windows.net/images/image-44.png?resize=1024%2C631&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-44.png?resize=300%2C185&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-44.png?resize=768%2C473&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-44.png?w=1525&amp;ssl=1 1525w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>Give the profile a name and click&nbsp;<strong>Next</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-45.png?resize=750%2C634&#038;ssl=1" alt="" class="wp-image-550" width="750" height="634" srcset="https://irlimages.blob.core.windows.net/images/image-45.png?resize=1024%2C865&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-45.png?resize=300%2C253&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-45.png?resize=768%2C648&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-45.png?w=1208&amp;ssl=1 1208w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="4"><li>Choose &#8220;<strong>Device</strong>&#8221; as the deployment channel and select WindowsDefenderATPOnboarding.xml in the &#8220;Intune&#8221; folder that we extracted from the onboarding package above as a configuration profile file.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-46.png?resize=750%2C472&#038;ssl=1" alt="" class="wp-image-551" width="750" height="472" srcset="https://irlimages.blob.core.windows.net/images/image-46.png?resize=1024%2C644&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-46.png?resize=300%2C189&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-46.png?resize=768%2C483&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-46.png?resize=1536%2C965&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-46.png?w=1634&amp;ssl=1 1634w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="5"><li>Click Next.</li></ol>



<ol start="6"><li>Assign devices on the Assignment tab. Click Next.</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3 id="approve-system-extensions">Approve System Extensions</h3>



<p>Now, we need to create a profile so that the extensions in the onboarding file are approved in the system context.</p>



<ol><li>Select Create Profile under Configuration Profiles.</li></ol>



<ol start="2"><li>Select Platform as macOS, Profile type as Templates and the Template name as Extensions. Click create.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-47.png?resize=750%2C465&#038;ssl=1" alt="" class="wp-image-552" width="750" height="465" srcset="https://irlimages.blob.core.windows.net/images/image-47.png?resize=1024%2C635&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-47.png?resize=300%2C186&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-47.png?resize=768%2C476&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-47.png?w=1512&amp;ssl=1 1512w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>In the Basics tab, give a name to this new profile.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-48.png?resize=750%2C597&#038;ssl=1" alt="" class="wp-image-553" width="750" height="597" srcset="https://irlimages.blob.core.windows.net/images/image-48.png?resize=1024%2C815&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-48.png?resize=300%2C239&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-48.png?resize=768%2C612&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-48.png?w=1252&amp;ssl=1 1252w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="4"><li>In the Configuration settings tab, expand System Extensions and add the following entries in the Allowed system extensions section:</li></ol>



<figure class="wp-block-table has-small-font-size"><table><thead><tr><th>Bundle identifier</th><th>Team identifier</th></tr></thead><tbody><tr><td>com.microsoft.wdav.epsext</td><td>UBF8T346G9</td></tr><tr><td>com.microsoft.wdav.netext</td><td>UBF8T346G9</td></tr></tbody></table></figure>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-50.png?resize=750%2C477&#038;ssl=1" alt="" class="wp-image-555" width="750" height="477" srcset="https://irlimages.blob.core.windows.net/images/image-50.png?resize=1024%2C650&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-50.png?resize=300%2C190&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-50.png?resize=768%2C487&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-50.png?resize=1536%2C975&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-50.png?w=1615&amp;ssl=1 1615w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-51.png?resize=750%2C115&#038;ssl=1" alt="" class="wp-image-556" width="750" height="115" srcset="https://irlimages.blob.core.windows.net/images/image-51.png?resize=1024%2C157&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-51.png?resize=300%2C46&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-51.png?resize=768%2C118&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-51.png?w=1095&amp;ssl=1 1095w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3>Full Disk Access</h3>



<p>By default, the new versions of macOS do not allow applications to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicitly granting that app&#8217;s permission. Microsoft defender is also no exception; without this consent, it will not be able to protect the device fully.</p>



<p>This profile grants Full Disk Access to Microsoft Defender for Endpoint. </p>



<ol><li>Download the config file from <a href="https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig" target="_blank" rel="noreferrer noopener">mdatp-xplat/fulldisk.mobileconfig at master · microsoft/mdatp-xplat · GitHub</a> and save it as <strong>fulldisk.mobileconfig</strong></li></ol>



<ol start="2"><li>Log in to Intune portal, navigate to <strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>macOS Devices</strong> &gt; <strong>Configuration profiles</strong> &gt; <strong>Create Profile</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-43.png?resize=750%2C225&#038;ssl=1" alt="" class="wp-image-548" width="750" height="225" srcset="https://irlimages.blob.core.windows.net/images/image-43.png?resize=1024%2C306&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-43.png?resize=300%2C90&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-43.png?resize=768%2C229&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-43.png?resize=1536%2C459&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-43.png?w=1624&amp;ssl=1 1624w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>Select <strong>Profile type</strong> as <strong>Templates and Template name</strong> as <strong>Custom</strong>. Click&nbsp;<strong>Create</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-44.png?resize=750%2C462&#038;ssl=1" alt="" class="wp-image-549" width="750" height="462" srcset="https://irlimages.blob.core.windows.net/images/image-44.png?resize=1024%2C631&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-44.png?resize=300%2C185&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-44.png?resize=768%2C473&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-44.png?w=1525&amp;ssl=1 1525w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="4"><li>Give the profile a name and click <strong>Next</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-52.png?resize=750%2C620&#038;ssl=1" alt="" class="wp-image-557" width="750" height="620" srcset="https://irlimages.blob.core.windows.net/images/image-52.png?resize=1024%2C846&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-52.png?resize=300%2C248&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-52.png?resize=768%2C634&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-52.png?w=1188&amp;ssl=1 1188w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="5"><li>Choose &#8220;<strong>Device</strong>&#8221; as the deployment channel and select the <strong><strong>fulldisk.mobileconfig</strong></strong> that we downloaded in step 1.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-53.png?resize=630%2C602&#038;ssl=1" alt="" class="wp-image-558" width="630" height="602" srcset="https://irlimages.blob.core.windows.net/images/image-53.png?w=840&amp;ssl=1 840w, https://irlimages.blob.core.windows.net/images/image-53.png?resize=300%2C287&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-53.png?resize=768%2C734&amp;ssl=1 768w" sizes="(max-width: 630px) 100vw, 630px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3>Network&nbsp;Filter</h3>



<p>This profile configures the Endpoint Detection and Response (EDR) capabilities for Microsoft Defender to inspect socket traffic and report this information to the security center. Configuring this policy allows the network extension to perform this functionality.</p>



<p>Download the config file <a href="https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig" target="_blank" rel="noreferrer noopener">Network Config</a> file and repeat the same steps to create a custom profile. </p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-54.png?resize=629%2C585&#038;ssl=1" alt="" class="wp-image-559" width="629" height="585" srcset="https://irlimages.blob.core.windows.net/images/image-54.png?w=839&amp;ssl=1 839w, https://irlimages.blob.core.windows.net/images/image-54.png?resize=300%2C279&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-54.png?resize=768%2C714&amp;ssl=1 768w" sizes="(max-width: 629px) 100vw, 629px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3>Notifications</h3>



<p>This profile will allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS.</p>



<p>Download the config file <a href="https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig" target="_blank" rel="noreferrer noopener">notif.mobileconfig</a> file and repeat the same steps to create a custom profile.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-55.png?resize=750%2C635&#038;ssl=1" alt="" class="wp-image-560" width="750" height="635" srcset="https://irlimages.blob.core.windows.net/images/image-55.png?resize=1024%2C867&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-55.png?resize=300%2C254&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-55.png?resize=768%2C650&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-55.png?w=1159&amp;ssl=1 1159w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>

<h3>Background Services</h3>



<p>This configuration profile grants Background Service permissions to Microsoft Defender for Endpoint. macOS 13 (Ventura) contains new privacy enhancements. Beginning with this version, by default, applications cannot run in background without explicit consent. Microsoft Defender for Endpoint must run its daemon process in background.</p>



<p>Download the config file <a href="https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/background_services.mobileconfig" target="_blank" rel="noreferrer noopener">background_services.mobileconfig</a> file and repeat the same steps to create a custom profile.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/macos_background_services.png?resize=750%2C635&#038;ssl=1" alt="" class="wp-image-560" width="750" height="635" srcset="https://irlimages.blob.core.windows.net/images/macos_background_services.png?resize=1024%2C867&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/macos_background_services.png?resize=300%2C254&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/macos_background_services.png?resize=768%2C650&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/macos_background_services.png?w=1159&amp;ssl=1 1159w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>This is how your portal might look like once you have created all these profiles for MDE:</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-56.png?resize=750%2C269&#038;ssl=1" alt="" class="wp-image-561" width="750" height="269" srcset="https://irlimages.blob.core.windows.net/images/image-56.png?resize=1024%2C367&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-56.png?resize=300%2C107&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-56.png?resize=768%2C275&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-56.png?w=1276&amp;ssl=1 1276w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3>Deploy MDE to macOS Devices</h3>



<p>Now we have completed all the pre-work for Microsoft Defender for Endpoint, its time to publish the app to devices:</p>



<ol><li>Login to Intune portal and navigate to Apps &gt; macOS &gt; and select the app type as <strong>Microsoft Defender for Endpoint (macOS)</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-57.png?resize=750%2C496&#038;ssl=1" alt="" class="wp-image-562" width="750" height="496" srcset="https://irlimages.blob.core.windows.net/images/image-57.png?resize=1024%2C677&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-57.png?resize=300%2C198&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-57.png?resize=768%2C507&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-57.png?resize=1536%2C1015&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-57.png?w=1586&amp;ssl=1 1586w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="2"><li>Keep default values, click Next and assign it to the <strong>Device </strong>group.</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>It is not completed yet&#8230;There are still two more configurations remaining:</p>



<ol><li>Install Quick Scan settings for MDE</li><li>Enable quick scan settings for MDE</li></ol>



<p>Navigate to Devices &gt; macOS &gt; Shell Scripts, upload the two scripts below, and assign them to the same device group to which the MDE policies were assigned.</p>



<ul><li><a href="https://github.com/microsoft/shell-intune-samples/blob/master/macOS/Config/MDATP/installMDATPQuickScanJob.sh">shell-intune-samples/installMDATPQuickScanJob.sh at master · microsoft/shell-intune-samples · GitHub</a></li><li><a href="https://github.com/microsoft/shell-intune-samples/blob/master/macOS/Config/MDATP/runMDATPQuickScan.sh">shell-intune-samples/runMDATPQuickScan.sh at master · microsoft/shell-intune-samples · GitHub</a></li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h3>Add macOS Company Portal App</h3>



<p>There are multiple ways of pushing the Company Portal to macOS devices: </p>



<ul><li>Instruct users to download and install Company Portal</li><li>Install Company Portal for macOS as a macOS LOB app</li><li>Install Company Portal for macOS by using a macOS Shell Script</li></ul>



<p>However, for now, I will walk you through the app deployment on supervised devices and would recommend deploying Company Portal using shell script. The company portal will be downloaded and installed using the macOS Shell Scripts feature. This option will always install the current version of Company Portal for macOS but lacks the option of reporting app installation.</p>



<ol><li>Download the <a href="https://github.com/microsoft/shell-intune-samples/blob/master/macOS/Apps/Company%20Portal/installCompanyPortal.zsh" target="_blank" rel="noreferrer noopener">Intune Company Portal Installation Script</a>.</li></ol>



<ol start="2"><li>Login to Intune portal and navigate to <strong>Devices &gt; macOS &gt; Shell Scripts.</strong></li></ol>



<ol start="3"><li>Set Run script as &#8220;<strong>signed-in user</strong>&#8221; to No. This enforces the script to run in the system context.</li></ol>



<ol start="4"><li>Set the Maximum number of retries if the script fails to <strong>3</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-58.png?resize=750%2C501&#038;ssl=1" alt="" class="wp-image-566" width="750" height="501" srcset="https://irlimages.blob.core.windows.net/images/image-58.png?resize=1024%2C684&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-58.png?resize=300%2C200&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-58.png?resize=768%2C513&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-58.png?resize=360%2C240&amp;ssl=1 360w, https://irlimages.blob.core.windows.net/images/image-58.png?resize=600%2C400&amp;ssl=1 600w, https://irlimages.blob.core.windows.net/images/image-58.png?w=1312&amp;ssl=1 1312w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="5"><li>Assign the script to the device group.</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>It has been a long post, and I will end it here. In the next part of the series, I will cover device enrollment using Modern Authentication, some mandatory restrictions that you should have on the MacBooks and finally, publishing M365 apps, certificates and VPN.</p>



<p>Stay In(tuned) and be #intuneinspired</p>
<!--kg-card-end: html-->