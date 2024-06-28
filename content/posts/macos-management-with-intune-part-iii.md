---
title: "macOS Management with Intune – Part III"
date: 2022-10-25T13:03:06"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>Welcome to part three of the macOS management series, wherein I will help you with understanding the different macOS settings that should be managed with compliance policies &amp; system preferences. And then will cover some required device restrictions also.</p>

<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Compliance Policy</h2>



<p>Using the compliance policies in Microsoft Intune, you can ensure that only trusted users from compliant macOS devices can access your company resources. </p>



<p>I will not go through the steps to create the compliance policy as it's a simple, straightforward configuration and is already available on numerous blog posts. Many a time, I have seen that we follow the steps in these guides and configure the policies by simply copying the steps from these guides.</p>



<p>So, If you are the one who will manage these endpoints, then you should know: <strong>what are you configuring?</strong> <strong>Is the policy needed in your environment?</strong> <strong> What will be it's impact?</strong> </p>



<p>Let's get started then by understanding the components in macOS compliance policies.</p>

<h3><span style="text-decoration: underline;">System Integrity Protection</span></h3>


<p>The first policy to configure is <span style="text-decoration: underline;"><em>System Integrity Protection (SIP)</em></span>. SIP in macOS protects the entire system by preventing unauthorised code execution. Apple&#8217;s system is smart enough to authorise apps that users download from the App Store. If you allow the users to download the apps from trusted developers, the system also authorizes them as the developer will notarize them. </p>



<p>When you enable this setting in the compliance policy, OS will block the launching of all other apps. </p>



<p><strong><span style="text-decoration: underline;"><em>Failure to enable SIP leaves your computer vulnerable to malicious code.</em></span></strong></p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-65.png?resize=700%2C125&#038;ssl=1" alt="" class="wp-image-606" width="700" height="125" srcset="https://irlimages.blob.core.windows.net/images/image-65.png?w=933&amp;ssl=1 933w, https://irlimages.blob.core.windows.net/images/image-65.png?resize=300%2C54&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-65.png?resize=768%2C137&amp;ssl=1 768w" sizes="(max-width: 700px) 100vw, 700px" data-recalc-dims="1" /></figure></div>


<h3><span style="text-decoration: underline;">Minimum / Maximum OS Version</span></h3>



<p>You can enforce minimum and maximum OS version requirements for corporate macOS devices. When a device fails to comply with the configured versions, it is reported as non-compliant. Based on the conditions you have configured in conditional access, the device won&#8217;t be allowed to access organization resources until the device is compliant or a rule changes to allow the OS version.</p>



<p>If you want stricter controls, you can also enforce settings for specific build numbers that you want to be enforced as the minimum allowed. </p>



<h3><span style="text-decoration: underline;">Password Settings</span></h3>



<p>Next is enforcing the password policy. You should configure this policy to ensure a password is required to access and use Mac that is enrolled in Intune. This policy uses the <strong><span style="text-decoration: underline;"><em>Passcode</em></span></strong> payload, and when the payload is installed on the device, users have 60 minutes to enter a password. If users don’t do so within that time, the payload forces them to enter a password using the specified settings. The settings available for the passcode payload are:</p>



<p><strong><span style="text-decoration: underline;">Setting</span>         <span style="text-decoration: underline;">Description</span></strong></p>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/table_macos.png?resize=700%2C125&#038;ssl=1" alt="" class="wp-image-606" width="700" height="300" srcset="https://irlimages.blob.core.windows.net/images/table_macos.png?w=933&amp;ssl=1 933w, https://irlimages.blob.core.windows.net/images/table_macos.png?resize=300%2C54&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/table_macos.png?resize=768%2C137&amp;ssl=1 768w" sizes="(max-width: 700px) 100vw, 700px" data-recalc-dims="1" /></figure></div>

<h3><span style="text-decoration: underline;">Gatekeeper</span></h3>



<p>macOS includes a security technology called <span style="text-decoration: underline;"><em>Gatekeeper</em></span>, which helps to ensure that only trusted software runs on your Mac. When an end user downloads and opens an app, a plug-in, or an installer package from outside the App Store, Gatekeeper verifies that the software is from an identified developer, is notarized by Apple to be free of known malicious content, and hasn’t been altered. Gatekeeper also requests user approval before opening downloaded software for the first time to ensure the user hasn’t been tricked into running executable code they believed to be a data file.</p>



<p>By default, Gatekeeper helps ensure that all downloaded software has been signed by the App Store or signed by a registered developer and notarized by Apple. As a standard practice, you can allow launching the apps downloaded from the App store and identified developers.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-66.png?resize=690%2C95&#038;ssl=1" alt="" class="wp-image-608" width="690" height="95" srcset="https://irlimages.blob.core.windows.net/images/image-66.png?w=920&amp;ssl=1 920w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/10/image-66.png?resize=300%2C41&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-66.png?resize=768%2C105&amp;ssl=1 768w" sizes="(max-width: 690px) 100vw, 690px" data-recalc-dims="1" /></figure></div>


<h3><span style="text-decoration: underline;">Stealth Mode</span></h3>



<p>Enabling &#8220;<span style="text-decoration: underline;"><em>stealth mode</em></span>” makes it more difficult for hackers and malware to find your Mac. When stealth mode is on, your Mac doesn’t respond to either “ping” requests or connection attempts from a closed TCP or UDP network. However, it will respond to incoming requests from known apps.</p>



<h3><span style="text-decoration: underline;">Block Incoming Connections</span></h3>



<pre class="wp-block-code"><code>⚡💣 <strong><em><span style="text-decoration: underline;">This can block all connections to your mac devices. If you are using then make sure you allow the apps in firewall policy.</span></em></strong></code></pre>



<p>Blocking all incoming connections on the firewall will protect your Mac from unwanted contact initiated by other computers when connected to the internet or a private network. However, your Mac can still allow access through the firewall for some services and apps. For example:</p>



<ul><li>If users turn on a sharing service, such as file sharing, macOS will open a specific port for the service to communicate through.</li></ul>



<ul><li>An app or service on another system can request access through the firewall, or it might have a trusted certificate and be allowed access.</li></ul>



<p>You can further configure it in firewall settings to allow or restrict certain apps.</p>



<p>With all the required info now, this is how your compliance policy should look like:</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-67.png?resize=750%2C525&#038;ssl=1" alt="" class="wp-image-609" width="750" height="525" srcset="https://irlimages.blob.core.windows.net/images/image-67.png?resize=1024%2C717&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-67.png?resize=300%2C210&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-67.png?resize=768%2C538&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-67.png?w=1161&amp;ssl=1 1161w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Device Restrictions</h2>



<p>Now, we move to the next part with configuring restrictions, and I will use the settings catalogue for them:</p>



<h3><strong><span style="text-decoration: underline;">Software Update Policies</span></strong></h3>



<p><span style="text-decoration: underline;">Enable Auto Update</span></p>



<ul><li>This enforces the &#8220;Automatically check for updates&#8221; payload, and the macOS will check for the updates in the background for new malware definition files from Apple for XProtect and Gatekeeper.</li></ul>



<p><span style="text-decoration: underline;">Enable Download New Updates When Available</span></p>



<ul><li>This ensures that updates happen on time and the system is not exposed to additional risk.</li></ul>



<p><span style="text-decoration: underline;">Enable Installation of App Update</span></p>



<ul><li>This makes sure that the software is patched automatically.</li></ul>



<p><span style="text-decoration: underline;">Enable System Data Files and Security Updates</span></p>



<ul><li>This policy ensures that system patches are applied on time and reduces the risk of vulnerabilities being exploited.</li></ul>



<p><span style="text-decoration: underline;">Software Update Deferment Is Less Than or Equal to 30 Days</span></p>



<ul><li>This ensures you get time to test the major OS upgrades before rolling them to all users.</li></ul>



<p><span style="text-decoration: underline;">Ensure Standard naming patterns avoid collisions and mitigate risk for computer users.</span></p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-68.png?resize=750%2C540&#038;ssl=1" alt="" class="wp-image-611" width="750" height="540" srcset="https://irlimages.blob.core.windows.net/images/image-68.png?resize=1024%2C737&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-68.png?resize=300%2C216&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-68.png?resize=768%2C553&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-68.png?w=1036&amp;ssl=1 1036w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2><span style="text-decoration: underline;">System Preferences</span></h2>



<p>Below is a list of standard configurations you can configure for your company-owned macOS devices.</p>



<ul><li>Enable &#8220;<strong>Bluetooth</strong>&#8221; Status in Menu Bar</li></ul>



<ul><li>Enable &#8220;<strong>Wi-Fi</strong>&#8221; status in Menu Bar</li></ul>



<ul><li>Enable &#8220;<strong>Set time and date automatically</strong>&#8220;</li></ul>



<ul><li>Enforce a <strong>corporate Desktop &amp; Screen Saver</strong> on all macOS devices</li></ul>



<ul><li>Make sure that <strong>Screen Saver Corners</strong> are secure</li></ul>



<ul><li>Enable <strong>Close View Hotkeys</strong> for securing screen saver</li></ul>



<pre class="wp-block-code"><code>📢⚡Setting a hot corner to disable the screen saver poses a potential security risk since an unauthorized person could use this to bypass the login screen and gain  to the system.</code></pre>



<ul><li>Block AirDrop on all corporate-owned macOS devices</li></ul>



<pre class="wp-block-code"><code>📢⚡AirDrop can allow malicious files to be downloaded from unknown sources.</code></pre>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-69.png?resize=750%2C570&#038;ssl=1" alt="" class="wp-image-613" width="750" height="570" srcset="https://irlimages.blob.core.windows.net/images/image-69.png?resize=1024%2C779&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-69.png?resize=300%2C228&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-69.png?resize=768%2C585&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-69.png?w=1214&amp;ssl=1 1214w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Security &amp; Privacy</h2>



<p>Below is a list of standard restrictions you can configure for your company-owned macOS devices.</p>



<ul><li>Ensure FileVault Is Enabled (<span style="text-decoration: underline;"><em>I will cover FileVault in a dedicated post soon</em></span>!) </li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-73.png?resize=572%2C448&#038;ssl=1" alt="" class="wp-image-621" width="572" height="448" srcset="https://irlimages.blob.core.windows.net/images/image-73.png?w=763&amp;ssl=1 763w, https://irlimages.blob.core.windows.net/images/image-73.png?resize=300%2C235&amp;ssl=1 300w" sizes="(max-width: 572px) 100vw, 572px" data-recalc-dims="1" /></figure></div>


<ul><li>Ensure Firewall Is Enabled</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-74.png?resize=626%2C344&#038;ssl=1" alt="" class="wp-image-622" width="626" height="344" srcset="https://irlimages.blob.core.windows.net/images/image-74.png?w=834&amp;ssl=1 834w, https://irlimages.blob.core.windows.net/images/image-74.png?resize=300%2C165&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-74.png?resize=768%2C422&amp;ssl=1 768w" sizes="(max-width: 626px) 100vw, 626px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-75.png?resize=639%2C322&#038;ssl=1" alt="" class="wp-image-623" width="639" height="322" srcset="https://irlimages.blob.core.windows.net/images/image-75.png?w=852&amp;ssl=1 852w, https://irlimages.blob.core.windows.net/images/image-75.png?resize=300%2C151&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-75.png?resize=768%2C387&amp;ssl=1 768w" sizes="(max-width: 639px) 100vw, 639px" data-recalc-dims="1" /></figure></div>


<ul><li>Ensure Firewall Stealth Mode Is Enabled</li></ul>



<ul><li>Ensure Location Services Are Enabled</li></ul>



<ul><li>Ensure Sending Diagnostic, and Usage Data to Apple Is Disabled</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-76.png?resize=518%2C126&#038;ssl=1" alt="" class="wp-image-624" width="518" height="126" srcset="https://irlimages.blob.core.windows.net/images/image-76.png?w=691&amp;ssl=1 691w, https://irlimages.blob.core.windows.net/images/image-76.png?resize=300%2C73&amp;ssl=1 300w" sizes="(max-width: 518px) 100vw, 518px" data-recalc-dims="1" /></figure></div>


<ul><li>Ensure Limit Ad Tracking Is Enabled</li></ul>



<ul><li>Ensure Gatekeeper Is Enabled</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-77.png?resize=529%2C98&#038;ssl=1" alt="" class="wp-image-625" width="529" height="98" srcset="https://irlimages.blob.core.windows.net/images/image-77.png?w=705&amp;ssl=1 705w, https://irlimages.blob.core.windows.net/images/image-77.png?resize=300%2C56&amp;ssl=1 300w" sizes="(max-width: 529px) 100vw, 529px" data-recalc-dims="1" /></figure></div>


<ul><li>Ensure an Administrator Password Is Required to Access System-Wide Preferences</li></ul>



<ul><li>Disable iCloud Keychain sync</li></ul>



<ul><li>Disallow iCloud Drive sync</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-78.png?resize=548%2C227&#038;ssl=1" alt="" class="wp-image-626" width="548" height="227" srcset="https://irlimages.blob.core.windows.net/images/image-78.png?w=730&amp;ssl=1 730w, https://irlimages.blob.core.windows.net/images/image-78.png?resize=300%2C124&amp;ssl=1 300w" sizes="(max-width: 548px) 100vw, 548px" data-recalc-dims="1" /></figure></div>


<ul><li>Ensure iCloud Drive Document, and Desktop Sync Is Disabled</li></ul>



<p>Ensure Backup Automatically is Enabled</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-80.png?resize=260%2C115&#038;ssl=1" alt="" class="wp-image-628" width="260" height="115" srcset="https://irlimages.blob.core.windows.net/images/image-80.png?w=347&amp;ssl=1 347w, https://irlimages.blob.core.windows.net/images/image-80.png?resize=300%2C132&amp;ssl=1 300w" sizes="(max-width: 260px) 100vw, 260px" data-recalc-dims="1" /></figure></div>


<ul><li>Ensure Guest Accounts Is Disabled &amp; users&#8217; Accounts Do Not Have a Password Hint</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-81.png?resize=313%2C117&#038;ssl=1" alt="" class="wp-image-629" width="313" height="117" srcset="https://irlimages.blob.core.windows.net/images/image-81.png?w=417&amp;ssl=1 417w, https://irlimages.blob.core.windows.net/images/image-81.png?resize=300%2C112&amp;ssl=1 300w" sizes="(max-width: 313px) 100vw, 313px" data-recalc-dims="1" /></figure></div>


<ul><li>Ensure the &#8220;root&#8221; Account Is Disabled</li></ul>



<ul><li>Audit Software Inventory</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>Stay tuned for the next part, where I will cover app deployment using <strong>shell scripts. </strong></p>
<!--kg-card-end: html-->