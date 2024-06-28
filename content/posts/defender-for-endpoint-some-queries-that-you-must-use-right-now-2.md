---
title: "Defender for Endpoint: Some Essential Queries That You Must Use Right Now!"
date: 2023-01-06T16:24:15"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>Being an Intune administrator means that in addition to managing and deploying endpoints, you are also somewhat responsible for ensuring that they continue to comply to the security standards set forth by your company.</p>



<p>Likewise, you may have heard a lot about utilizing Microsoft Defender for Endpoint to construct logic apps and do threat-hunting queries, and you may want to give those a shot as well. Excellent! Starting off with some field notes, I&#8217;ve included a few use cases that you should also try or implement to gain a better grasp of your devices and their security posture.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>The Need</h2>



<p>Proactively detecting and eliminating advanced threats via threat hunting is becoming increasingly important for many organizations and is actually a time consuming task. However, you may set up rules that automatically adjust to your security policies in accordance with the most recent threat information.</p>



<p>There are many ways to achieve this automation, like:</p>



<ol>
<li>Automating SIEM/EDR/ATP queries</li>



<li>Use runbooks for automation of incidents</li>



<li>Use Logic apps</li>



<li>Automate queries &amp; reports using Power Automate &amp; PowerApps</li>



<li>Create dashboards using Power BI</li>
</ol>



<p>Now, let&#8217;s get into some threat-hunting ideas to look for and build some simple must have queries.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Devices Not Onboarded to MDE</h2>



<p>It is quite common in any environment to have endpoints that have not been successfully onoarded to defender for endpoint. Such devices are shown as &#8220;can be onoarded&#8221; in recommendations. Logging into your Defender admin portal and verifying the list on daily basis can be a daunting task. However you can easily automate this by scheduling a report of such devices using Power Automate or Logic Apps.</p>



<p>I am using Power Automate for this and the configuration is as below:</p>



<ol>
<li>Sign in to&nbsp;<a href="https://flow.microsoft.com/" target="_blank" rel="noopener" title="">Power Automate</a>.</li>



<li>Select&nbsp;<strong>My flows</strong>&nbsp;&gt;&nbsp;<strong>New flow</strong>&nbsp;&gt;&nbsp;<strong>Scheduled cloud flow</strong>.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-2.png?resize=298%2C269&#038;ssl=1" alt="" class="wp-image-1032" width="298" height="269" srcset="https://irlimages.blob.core.windows.net/2023-01/image-2.png?w=397&amp;ssl=1 397w, https://irlimages.blob.core.windows.net/2023-01/image-2.png?resize=300%2C271&amp;ssl=1 300w" sizes="(max-width: 298px) 100vw, 298px" data-recalc-dims="1" /></figure></div>


<ol start="3">
<li>In the fields next to&nbsp;<strong>Starting</strong>, specify the date and time when your flow should start.</li>



<li>In the fields next to&nbsp;<strong>Repeat every</strong>, specify the flow&#8217;s recurrence.</li>



<li>Select&nbsp;<strong>Create</strong>.</li>



<li>Select&nbsp;<strong>Recurrence</strong>&nbsp;&gt;&nbsp;<strong>Show advanced options</strong> and configure the schedule.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-4.png?resize=568%2C338&#038;ssl=1" alt="" class="wp-image-1034" width="568" height="338" srcset="https://irlimages.blob.core.windows.net/2023-01/image-4.png?w=757&amp;ssl=1 757w, https://irlimages.blob.core.windows.net/2023-01/image-4.png?resize=300%2C178&amp;ssl=1 300w" sizes="(max-width: 568px) 100vw, 568px" data-recalc-dims="1" /></figure></div>


<ol start="7">
<li>Choose&nbsp;<strong>Microsoft Defender Advance Hunting</strong>&nbsp;for the new step and type your query:</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-11.png?resize=567%2C208&#038;ssl=1" alt="" class="wp-image-1042" width="567" height="208" srcset="https://irlimages.blob.core.windows.net/2023-01/image-11.png?w=756&amp;ssl=1 756w, https://irlimages.blob.core.windows.net/2023-01/image-11.png?resize=300%2C110&amp;ssl=1 300w" sizes="(max-width: 567px) 100vw, 567px" data-recalc-dims="1" /></figure></div>


<ol start="8">
<li>Create a CSV to export all the results from the query.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-6.png?resize=558%2C134&#038;ssl=1" alt="" class="wp-image-1036" width="558" height="134" srcset="https://irlimages.blob.core.windows.net/2023-01/image-6.png?w=744&amp;ssl=1 744w, https://irlimages.blob.core.windows.net/2023-01/image-6.png?resize=300%2C72&amp;ssl=1 300w" sizes="(max-width: 558px) 100vw, 558px" data-recalc-dims="1" /></figure></div>


<ol start="9">
<li>Schedule the report.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-8.png?resize=374%2C306&#038;ssl=1" alt="" class="wp-image-1038" width="374" height="306" srcset="https://irlimages.blob.core.windows.net/2023-01/image-8.png?w=748&amp;ssl=1 748w, https://irlimages.blob.core.windows.net/2023-01/image-8.png?resize=300%2C245&amp;ssl=1 300w" sizes="(max-width: 374px) 100vw, 374px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Local Admin Report</h2>



<p>This is one of the most common requirements and you can easily use KQL query in the Advanced Hunting to create &amp; schedule a report for machines having users added as local admin to them.</p>



<pre class="wp-block-code"><code>DeviceLogonEvents
| where Timestamp &gt;= ago(7d)
| where IsLocalAdmin == true

| summarize count() by DeviceName, AccountName,LogonType
| sort by AccountName</code></pre>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-9.png?resize=750%2C342&#038;ssl=1" alt="" class="wp-image-1040" width="750" height="342" srcset="https://irlimages.blob.core.windows.net/2023-01/image-9.png?resize=1024%2C467&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2023-01/image-9.png?resize=300%2C137&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2023-01/image-9.png?resize=768%2C350&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2023-01/image-9.png?w=1072&amp;ssl=1 1072w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Hunting For Legacy Authentication</h2>



<p>Basic authentication has been depreciated so it&#8217;s time to hunt down the applications and clients with Basic Authentication and switch to newer authentication methods.</p>



<pre class="wp-block-code"><code>SigninLogs
| where ClientAppUsed !in ("Mobile Apps and Desktop clients", "Browser")
| where isnotempty(ClientAppUsed)
| evaluate pivot(ClientAppUsed, count(), UserPrincipalName)</code></pre>



<p>You can easily automate a daily report using it in Power Automate.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>If you are using Microsoft Defender for Endpoint for your Android Enterprise and iOS devices then there are certain configurations required in defender portal to avoid unnecessary alerts on end-users devices.</p>



<h2>Whitelist Your Trusted Root Certificate</h2>



<p>If you are deploying trusted root certificates on your enterprise devices then you might receive alerts in defender portal for <strong>&#8220;Suspicious certificates installed on one endpoint&#8221;</strong>. Since these devices are corporate owned devices and have your root  certificate installed then you can classify these alerts as false positive i.e. detected and identified as malicious even though the entity isn&#8217;t actually a threat.</p>



<p>Only apps/programs signed with the exact signed certificate uploaded as indicator are affected. Do not expect to upload a root certificate and all sub certificates will be handled the same.</p>



<p>The full chain of trust for the certificate must be valid and either be trusted through a root certificate in the Microsoft Trusted Root Program or the root certificate must be present in the Trusted Root Certification Authorities store.</p>



<p>To do so, the steps are as below:</p>



<ol>
<li>Select Settings &gt; Endpoints &gt; Indicators (under Rules) in the navigation pane.</li>



<li>Select&nbsp;<strong>Add indicator</strong>.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-12.png?resize=750%2C277&#038;ssl=1" alt="" class="wp-image-1043" width="750" height="277" srcset="https://irlimages.blob.core.windows.net/2023-01/image-12.png?resize=1024%2C379&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2023-01/image-12.png?resize=300%2C111&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2023-01/image-12.png?resize=768%2C284&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2023-01/image-12.png?w=1426&amp;ssl=1 1426w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="3">
<li>Specify the following details:
<ul>
<li>Indicator &#8211; Specify the entity details and define the expiration of the indicator.</li>



<li>Action &#8211; Specify the action to be taken and provide a description.</li>



<li>Scope &#8211; Define the scope of the machine group.</li>
</ul>
</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-13.png?resize=750%2C365&#038;ssl=1" alt="" class="wp-image-1044" width="750" height="365" srcset="https://irlimages.blob.core.windows.net/2023-01/image-13.png?resize=1024%2C498&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2023-01/image-13.png?resize=300%2C146&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2023-01/image-13.png?resize=768%2C374&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2023-01/image-13.png?w=1274&amp;ssl=1 1274w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="4">
<li>Review the details in the Summary tab, then click&nbsp;<strong>Save</strong>.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-14.png?resize=750%2C248&#038;ssl=1" alt="" class="wp-image-1045" width="750" height="248" srcset="https://irlimages.blob.core.windows.net/2023-01/image-14.png?resize=1024%2C338&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2023-01/image-14.png?resize=300%2C99&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2023-01/image-14.png?resize=768%2C253&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2023-01/image-14.png?resize=1536%2C506&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2023-01/image-14.png?w=1796&amp;ssl=1 1796w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Supress iOS/Android Upgrade Notifications</h2>



<p>If you have configured software update deferral policies for your iOS &amp; Android Enterprise devices then you might observe that the end users are ntofied to update iOS update notifications in Defender for Endpoint app. And this causes confusion and a bad user experience.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-15.png?resize=750%2C396&#038;ssl=1" alt="" class="wp-image-1046" width="750" height="396" srcset="https://irlimages.blob.core.windows.net/2023-01/image-15.png?resize=1024%2C540&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2023-01/image-15.png?resize=300%2C158&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2023-01/image-15.png?resize=768%2C405&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2023-01/image-15.png?resize=1536%2C811&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2023-01/image-15.png?w=1571&amp;ssl=1 1571w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p>To avoid these notifications on end user&#8217;s devices, you simply need to create an exception for iOS Upgrade in Defender portal. The process is pretty simple- select the security recommendation for iOS update and then select&nbsp;<strong>Exception options</strong>&nbsp;and fill out the form.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2023-01/image-16.png?resize=750%2C382&#038;ssl=1" alt="" class="wp-image-1047" width="750" height="382" srcset="https://irlimages.blob.core.windows.net/2023-01/image-16.png?resize=1024%2C521&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2023-01/image-16.png?resize=300%2C153&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2023-01/image-16.png?resize=768%2C391&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2023-01/image-16.png?w=1079&amp;ssl=1 1079w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>These are merely a few extremely simple instances, and the list is by no means complete. You can engage in a wide variety of approaches and methods when hunting. As you begin to evaluate your environment and choose the types of approaches and data you can use, your hunting maturity will increase.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!--kg-card-end: html-->