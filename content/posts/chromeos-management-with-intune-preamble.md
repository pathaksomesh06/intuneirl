---
title: "ChromeOS Management with Intune - Preamble"
date: 2022-11-01T01:49:12"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Talk of The Town</h2>



<p>In the last few days, ChromeOS &amp; Chrome Enterprise have become the <strong>buzzwords </strong>for the Mobile Device Management world. Microsoft Ignite &#8211; more than two weeks now, it seems Microsoft still has many more secrets to reveal in the crazy world of device management.</p>



<p>Like you, I was also super excited to test the new feature. In fact, still excited, as there is so much to explore into it. Let&#8217;s get started, then. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>What is Chrome Enterprise</h2>



<p>Google Chrome Enterprise, introduced by<strong> Google in 2017</strong>, is a business-based workplace solution for deploying and managing <strong>Chrome devices, Chrome browser and Chrome OS</strong>. Chrome Enterprise provides quality, easy-to-access and navigate cloud-based administrative tools and integrations with third-party services and offers 24/7 support for IT decision-makers and operators.</p>



<p>Chrome Enterprise offers the general Chrome OS features with its automatic updates, multi-layered security, remote desktop, application virtualization support, preference syncing and cloud or native printing.</p>



<p>Chrome Enterprise is offered under a yearly subscription service with a price charged per device.</p>



<p>Among Chrome Enterprise, added management features are:</p>



<ul><li>Google Play Store apps</li><li>Chrome OS extensions</li><li>Chrome web browser</li><li>Microsoft Active Directory</li><li>Printer management</li><li>Flexible fleet management</li></ul>



<p>As an administrator, the Google Admin console is where you manage all your Google Workspace services. <strong>Google Workspace (formerly known as Google Apps and later G Suite) is a collection of cloud computing, productivity and collaboration tools, software and products developed and marketed by Google.</strong> You can relate it to the Azure admin portal, where you add or remove users, manage billing, set up mobile devices, and more. The Admin console can be accessed at <a href="https://admin.google.com/" target="_blank" rel="noreferrer noopener">admin.google.com</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Intune &amp; Google Enterprise &#8211; Some Facts</h2>



<p>Before you start managing your trendy Chromebooks or ChromeOS, you need to configure a connection between Intune &amp; Google Workspace, and for that, you will need a connector &#8211; and for that, you will need a Google Workspace Subscription. 😃😎</p>



<p>In this article, I will help sign up for a Google Workspace subscription and set up and monitor a connection between the Google Admin console and Microsoft Intune.</p>



<p>This connector will help you to:</p>



<ul><li>Sync device information between the Google Admin console and Microsoft Intune.</li></ul>



<ul><li>View device information in your device inventory lists in the Microsoft Endpoint Manager admin center.</li></ul>



<ul><li>Apply remote actions, such as deprovision, restart, lost mode, and wipe in the admin center.</li></ul>



<pre class="wp-block-code"><code><strong><span style="text-decoration: underline;">ChromeOS or Chrome Enterprise devices are enrolled through Google Admin Center not Intune!</span></strong></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Set-Up Google Admin / Google Workspace</h2>



<p>As a first step, we need to have an active subscription to Google Workspace. In the <strong>Basic plan, you get the following</strong>:</p>



<ul><li>The complete set of G Suite apps with full enterprise-level functionality. </li><li>30 GB of cloud storage per person. </li><li>Basic admin-level controls let you add/remove users, enable security and more. </li></ul>



<p>You’ll have to subscribe to the Business plan if you want more features with additional functionality as:</p>



<ul><li>Cloud Search to search through all G Suite apps to get you the desired results. </li><li>The ability to recover company data from ex-employees’ accounts.</li><li>Advanced admin features let you set how long emails and chats are retained, where your data is stored, and more. </li></ul>



<p>If you want even more security and control over your data in G Suite, the <strong>Enterprise plan</strong>:</p>



<ul><li>An advanced console from where you can manage all users, apps, and devices on G Suite.</li><li>Control sharing of sensitive information.  </li><li>Get advanced enterprise-grade security and reports on how your data is being used. </li></ul>



<p>You can start with a 14-day free trial to use Google Workspace. The steps are as below:</p>



<ul><li>To start, fire up your favourite browser and navigate to workspace.google.com. On this page, click on the blue ‘Get Started button. </li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114254.jpg?resize=750%2C362&#038;ssl=1" alt="" class="wp-image-694" width="750" height="362" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114254.jpg?resize=1024%2C494&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114254.jpg?resize=300%2C145&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114254.jpg?resize=768%2C370&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114254.jpg?resize=1536%2C740&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114254.jpg?w=1892&amp;ssl=1 1892w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>The next page will be the sign-up page. Enter your business name, the number of employees and the country in which your business is located. After typing this info, click ‘Next’.</li></ul>



<ul><li>Next, click on ‘I have one I can use to enter your domain name. If you don’t have one, click on ‘I don’t have one.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image.png?resize=750%2C421&#038;ssl=1" alt="" class="wp-image-697" width="750" height="421" srcset="https://irlimages.blob.core.windows.net/2022-11/image.png?resize=1024%2C575&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image.png?resize=300%2C168&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image.png?resize=768%2C431&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image.png?w=1366&amp;ssl=1 1366w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114337.jpg?resize=750%2C368&#038;ssl=1" alt="" class="wp-image-696" width="750" height="368" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114337.jpg?resize=1024%2C503&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114337.jpg?resize=300%2C147&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114337.jpg?resize=768%2C377&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114337.jpg?resize=1536%2C755&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-114337.jpg?w=1872&amp;ssl=1 1872w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>Click ‘Next’ and on the next page where you’ll have to enter the exact address of your business. This is required to register your domain. </li></ul>



<ul><li>The next page will ask you to create your first Google Admin username.</li></ul>



<ul><li>Create a secure password and remember it. Once you sign in, you’ll be asked to review your Google Workspace plan. Click <strong>Next </strong>to confirm. </li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-1.png?resize=662%2C628&#038;ssl=1" alt="" class="wp-image-698" width="662" height="628" srcset="https://irlimages.blob.core.windows.net/2022-11/image-1.png?w=882&amp;ssl=1 882w, https://irlimages.blob.core.windows.net/2022-11/image-1.png?resize=300%2C285&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-1.png?resize=768%2C729&amp;ssl=1 768w" sizes="(max-width: 662px) 100vw, 662px" data-recalc-dims="1" /></figure></div>


<p>The next part is exactly the same steps you do while setting up the M365 tenant. i.e. adding &amp; verifying your custom domain, adding new users and assigning them roles and services. This is how your new Google Workspace Admin Center will look like once you are done with all these configurations:</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210216.jpg?resize=750%2C414&#038;ssl=1" alt="" class="wp-image-699" width="750" height="414" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210216.jpg?resize=1024%2C565&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210216.jpg?resize=300%2C166&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210216.jpg?resize=768%2C424&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210216.jpg?resize=1536%2C848&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210216.jpg?w=1897&amp;ssl=1 1897w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p>Looks cool 😎👩‍💻🏆</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Connect Intune with Google Workspace</h2>



<p>Now, we have to make our Intune tenant talk to your Google Workspace Admin Console. For this, you need to follow the steps as shown:</p>



<ul><li>Sign in to the <a href="https://go.microsoft.com/fwlink/?linkid=2109431">Microsoft Endpoint Manager admin center</a>.</li></ul>



<ul><li>Go to <strong>Tenant administration</strong> > <strong>Connectors and tokens</strong>.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210416.jpg?resize=750%2C365&#038;ssl=1" alt="" class="wp-image-700" width="750" height="365" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210416.jpg?resize=1024%2C499&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210416.jpg?resize=300%2C146&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210416.jpg?resize=768%2C374&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210416.jpg?resize=1536%2C748&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210416.jpg?w=1862&amp;ssl=1 1862w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>Select <strong>Chrome Enterprise (preview)</strong> > <strong>Connect</strong>.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210440.jpg?resize=750%2C323&#038;ssl=1" alt="" class="wp-image-701" width="750" height="323" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210440.jpg?resize=1024%2C441&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210440.jpg?resize=300%2C129&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210440.jpg?resize=768%2C331&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210440.jpg?resize=1536%2C662&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210440.jpg?w=1915&amp;ssl=1 1915w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>On the <strong>Connect to Chrome Enterprise</strong> page, select <strong>Google Admin console</strong>, and then:</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=750%2C390&#038;ssl=1" alt="" class="wp-image-702" width="750" height="390" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=1024%2C532&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=300%2C156&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=768%2C399&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=1536%2C799&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?w=1900&amp;ssl=1 1900w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>Sign in to the Admin console.</li></ul>



<ul><li>Go to <strong>Security</strong> > <strong>Access and data control</strong> > <strong>API Controls</strong>.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210724.jpg?resize=750%2C400&#038;ssl=1" alt="" class="wp-image-703" width="750" height="400" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210724.jpg?resize=1024%2C546&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210724.jpghttps://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210724.jpg?resize=300%2C160&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210724.jpg?resize=768%2C410&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210724.jpg?resize=1536%2C819&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210724.jpg?w=1877&amp;ssl=1 1877w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>Select <strong>MANAGE DOMAIN WIDE DELEGATION</strong>.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210809.jpg?resize=750%2C397&#038;ssl=1" alt="" class="wp-image-704" width="750" height="397" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210809.jpg?resize=1024%2C543&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210809.jpghttps://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210809.jpg?resize=300%2C159&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210809.jpg?resize=768%2C408&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210809.jpg?resize=1536%2C815&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210809.jpg?w=1911&amp;ssl=1 1911w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>Select <strong>Add new</strong> to create the API client for your connection.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210855.jpg?resize=750%2C388&#038;ssl=1" alt="" class="wp-image-705" width="750" height="388" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210855.jpg?resize=1024%2C529&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210855.jpg?resize=300%2C155&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210855.jpg?resize=768%2C397&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210855.jpg?resize=1536%2C794&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210855.jpg?w=1888&amp;ssl=1 1888w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>Copy the Client ID and OAuth Scopes in the Microsoft Endpoint Manager admin center.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=750%2C390&#038;ssl=1" alt="" class="wp-image-702" width="750" height="390" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=1024%2C532&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpghttps://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=300%2C156&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=768%2C399&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?resize=1536%2C799&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-210513.jpg?w=1900&amp;ssl=1 1900w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>Return to the Google Admin console and paste each value in the <strong>Client ID</strong> and <strong>OAutho scopes (comma-delimited)</strong> spaces. Intune requires the following scopes:<ul><li><code>https://www.googleapis.com/auth/admin.directory.device.chromeos</code></li><li><code>https://www.googleapis.com/auth/admin.directory.user.readonly</code></li><li><code>https://www.googleapis.com/auth/admin.directory.orgunit.readonly</code></li></ul></li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211103.jpg?resize=750%2C400&#038;ssl=1" alt="" class="wp-image-706" width="750" height="400" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211103.jpg?resize=1024%2C546&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211103.jpg?resize=300%2C160&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211103.jpg?resize=768%2C410&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211103.jpg?resize=1536%2C819&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211103.jpg?w=1776&amp;ssl=1 1776w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>Select <strong>Authorize</strong> to save all changes.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211154.jpg?resize=750%2C338&#038;ssl=1" alt="" class="wp-image-707" width="750" height="338" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211154.jpg?resize=1024%2C461&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211154.jpg?resize=300%2C135&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211154.jpg?resize=768%2C346&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211154.jpg?resize=1536%2C692&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211154.jpg?w=1913&amp;ssl=1 1913w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>Return to the Microsoft Endpoint Manager admin center and select <strong>Launch Google to connect now.</strong></li></ul>



<ul><li>Use your Google Admin account when prompted to authenticate with your organization&#8217;s Google Enterprise domain. </li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-2.png?resize=750%2C325&#038;ssl=1" alt="" class="wp-image-708" width="750" height="325" srcset="https://irlimages.blob.core.windows.net/2022-11/image-2.png?resize=1024%2C444&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-2.png?resize=300%2C130&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-2.png?resize=768%2C333&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-2.png?resize=1536%2C665&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/image-2.png?w=1849&amp;ssl=1 1849w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul><li>After you authenticate, the connection is established, and your organization’s enrolled Chrome OS devices begin syncing from the Google Admin console. The status changes to <strong>Active</strong> when syncing is complete.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211554.jpg?resize=750%2C313&#038;ssl=1" alt="" class="wp-image-709" width="750" height="313" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211554.jpg?resize=1024%2C428&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211554.jpg?resize=300%2C125&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211554.jpg?resize=768%2C321&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211554.jpg?resize=1536%2C641&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211554.jpg?w=1887&amp;ssl=1 1887w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211605.jpg?resize=750%2C289&#038;ssl=1" alt="" class="wp-image-710" width="750" height="289" srcset="https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211605.jpg?resize=1024%2C395&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211605.jpg?resize=300%2C116&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211605.jpg?resize=768%2C296&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211605.jpg?resize=1536%2C592&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/Annotation-2022-10-31-211605.jpg?w=1907&amp;ssl=1 1907w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Monitor connection status</h2>



<p>Go to <strong>Chrome Enterprise (preview)</strong> in the Intune admin portal to check the overall health of your connection. Chrome OS devices should appear shortly after the initial connection. Devices will continue to sync periodically and receive updates.</p>



<p>Available details include:</p>



<ul><li><strong>Status</strong>: <strong>Syncing</strong> is shown when devices are still being synced. The status changes to <strong>Active</strong> when syncing is complete.</li><li><strong>Last check-in</strong>: This shows the last time new devices, device details, or remote actions were synced between Microsoft Intune and the Google Admin console.</li><li>Chrome devices synced: Shows the number of Chrome OS devices synced with Intune.</li><li>Connected account: This shows the Google Admin account connected to Microsoft Intune.</li></ul>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-5.png?resize=750%2C276&#038;ssl=1" alt="" class="wp-image-713" width="750" height="276" srcset="https://irlimages.blob.core.windows.net/2022-11/image-5.png?resize=1024%2C377&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-5.png?resize=300%2C111&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-5.png?resize=768%2C283&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-5.png?resize=1536%2C566&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/image-5.png?w=1720&amp;ssl=1 1720w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Summary</h2>



<p>For now, I will end it here and give you some time to play around with your all-new Google Workspace Admin Console. In the next part, I will help you provision a Chrome Enterprise device and get it synced to Intune. Till then, stay <strong>In(tuned)</strong> and be <strong>#intuneinspired</strong>. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!--kg-card-end: html-->