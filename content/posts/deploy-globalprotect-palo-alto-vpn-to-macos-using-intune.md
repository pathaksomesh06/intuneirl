---
title: "Deploy GlobalProtect (Palo Alto) VPN to macOS using Intune"
date: 2022-11-21T02:19:21"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>On the last week&#8217;s post for <a href="https://intuneirl.com/2022/11/deploy-cisco-anyconnect-vpn-on-macos-devices-with-2fa/" target="_blank" rel="noopener" title="">Cisco AnyConnect VPN</a> on macOS, I had a request for publishing a similar guide for deploying Palo Alto&#8217;s VPN on corporate macOS devices. So on the request of Mieszko Ślusarczyk, this article will help you as an exhaustive guide for installing and configuring GlobalProtect VPN on your macOS devices.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>GlobalProtect VPN</h2>



<p>GlobalProtect is Palo Alto Networks’ VPN solution, which delivers the capabilities of their Security Operating Platform to remote workers and mobile devices. It provides excellent protection for network connections and in-depth visibility into who is accessing an organization’s network. GlobalProtect establishes a secure SSL or IPsec VPN connection between users and the network.</p>



<p>The GlobalProtect app software runs on endpoints and enables access to your network resources through the GlobalProtect portals and gateways you have deployed. The GlobalProtect app for Windows and macOS endpoints is deployed from the GlobalProtect portal. You can configure the app&#8217;s behaviour—for example, which tabs the users can see—in the client configuration(s) you define on the portal. See Define the GlobalProtect Agent Configurations, Customize the GlobalProtect App, and Deploy the GlobalProtect App Software for details.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-83.png?resize=750%2C651&#038;ssl=1" alt="https://docs.paloaltonetworks.com/" class="wp-image-908" width="750" height="651" srcset="https://irlimages.blob.core.windows.net/2022-11/image-83.png?resize=1024%2C889&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-83.png?resize=300%2C260&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-83.png?resize=768%2C667&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-83.png?w=1083&amp;ssl=1 1083w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Illustration to show how the GlobalProtect portals, gateways, and apps work together to enable secure access for all your users, regardless of what endpoints they are using or where they are located.</em></figcaption></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Licenses</h2>



<p>You don&#8217;t require GlobalProtect licenses if you wish to use them to offer a secure remote access or virtual private network (VPN) solution via one or more internal/external gateways. However, you need to buy an annual GlobalProtect Gateway license to access more sophisticated services (such as HIP checks and related content updates, support for the GlobalProtect mobile app, or IPv6 compatibility). This license needs to be set up on each firewall that controls a gateway that:</p>



<ul>
<li>Supports the GlobalProtect app for mobile endpoints</li>
</ul>



<ul>
<li>Supports the GlobalProtect app for Linux endpoints</li>
</ul>



<ul>
<li>Provides IPv6 connections</li>
</ul>



<ul>
<li>Split tunnel traffic based on the destination domain, application process name, or HTTP/HTTPS video streaming application.</li>
</ul>



<ul>
<li>Supports identification of managed devices using the endpoint’s serial number on gateways</li>
</ul>



<ul>
<li>Enforces GlobalProtect connections with FQDN exclusions</li>
</ul>



<p>For GlobalProtect Clientless VPN, you must also install a GlobalProtect Gateway license on the firewall that hosts the Clientless VPN from the GlobalProtect portal. You also need the&nbsp;GlobalProtect Clientless VPN&nbsp;dynamic updates to use this feature.</p>



<p>For detailed info on licenses, you can refer &#8211; <a href="https://docs.paloaltonetworks.com/pan-os/9-1/pan-os-admin/subscriptions/activate-subscription-licenses.html" target="_blank" rel="noopener" title="">Palo Alto Licenses</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Download and Install the GlobalProtect App</h2>



<p>You must download and install the GlobalProtect app on your macOS endpoint before you can join the GlobalProtect network. <strong>You should always download the app directly from a GlobalProtect portal within your organization</strong>. Because of this, you will not find any direct download link for the GP app on the Palo Alto Networks website.</p>



<p>To download the installer, ask your administrator for the IP address or FQDN of the GlobalProtect site. Your administrator should also confirm the username and password you can use to log into the portal and gateways. You usually connect to your company network using the same username and password.</p>



<p>Follow the steps to download the app:</p>



<ul>
<li>Log in to the GlobalProtect portal</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-85.png?resize=503%2C440&#038;ssl=1" alt="" class="wp-image-911" width="503" height="440" srcset="https://irlimages.blob.core.windows.net/2022-11/image-85.png?w=671&amp;ssl=1 671w, https://irlimages.blob.core.windows.net/2022-11/image-85.png?resize=300%2C262&amp;ssl=1 300w" sizes="(max-width: 503px) 100vw, 503px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>login with your admin credentials</em></figcaption></figure></div>


<ul>
<li>Navigate to the app download page and download the latest package for macOS</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-87.png?resize=485%2C542&#038;ssl=1" alt="" class="wp-image-913" width="485" height="542" srcsethttps://irlimages.blob.core.windows.net/2022-11/image-87.png?w=647&amp;ssl=1 647w, https://irlimages.blob.core.windows.net/2022-11/image-87.png?resize=268%2C300&amp;ssl=1 268w" sizes="(max-width: 485px) 100vw, 485px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Download macOS package</em></figcaption></figure></div>


<ul>
<li>Save the installer to your disk</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Enable System Extensions</h2>



<p>Apple has restricted the support for kernel extensions for macOS 10.15.4 and higher versions. This means you now have to use system extensions instead of kernel extensions. In addition to enabling system extensions, you must also enable network extensions to suppress the&nbsp;Network Extensions Configuration&nbsp;pop-up prompts that may occur for the Split Tunnel and enforce GlobalProtect Connections for Network Access features.</p>



<p>Use the following steps to configure a profile to approve the system extensions automatically:</p>



<ul>
<li>Login to&nbsp;<a href="https://intune.microsoft.com/#home" target="_blank" rel="noreferrer noopener">Intune portal</a></li>
</ul>



<ul>
<li>Navigate to&nbsp;<strong>Devices -&gt; macOS -&gt; Configuration Profiles</strong>&nbsp;and select create a profile</li>
</ul>



<ul>
<li>From the profile type dropdown, select Templates -&gt;<strong>Extensions&nbsp;</strong>profile</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-88.png?resize=750%2C450&#038;ssl=1" alt="" class="wp-image-914" width="750" height="450" srcset="https://irlimages.blob.core.windows.net/2022-11/image-88.png?w=1024&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-88.png?resize=300%2C180&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-88.png?resize=768%2C461&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>In&nbsp;<strong>Basics</strong>, enter the name &amp; description to match the purpose of the profile.</li>
</ul>



<ul>
<li>In the&nbsp;<strong>System Extensions</strong>&nbsp;– Set the Team identification to “<strong>PXPZ95SK77</strong>” and the Bundle identifier to “<strong>com.paloaltonetworks.GlobalProtect.client.extension</strong>“</li>
</ul>



<ul>
<li>Under Allowed system extension types, add a line to allow team identifier “<strong>PXPZ95SK77</strong>” to provide “<strong>Network extensions</strong>”.</li>
</ul>



<ul start="8">
<li>Next, review and assign it to the required group.</li>
</ul>



<p>This is how the configuration profile should look like:</p>



<figure class="wp-block-image size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-89.png?resize=731%2C320&#038;ssl=1" alt="" class="wp-image-915" width="731" height="320" srcset="https://irlimages.blob.core.windows.net/2022-11/image-89.png?w=975&amp;ssl=1 975w, https://irlimages.blob.core.windows.net/2022-11/image-89.png?resize=300%2C131&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-89.png?resize=768%2C336&amp;ssl=1 768w" sizes="(max-width: 731px) 100vw, 731px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Pre-populates GlobalProtect App Settings</h2>



<p>We will use a script that pre-populates GlobalProtect app settings, such as the default portal address and connection method.</p>



<ul>
<li>Sign in to the&nbsp;<a href="https://intune.microsoft.com/" target="_blank" rel="noreferrer noopener">Intune portal.</a></li>
</ul>



<ul>
<li>Select&nbsp;<strong>Devices</strong>&nbsp;&gt;&nbsp;<strong>macOS</strong>&nbsp;&gt;&nbsp;<strong>Shell scripts</strong>&nbsp;&gt;&nbsp;<strong>Add</strong>.</li>
</ul>



<ul>
<li>In&nbsp;<strong>Basics</strong>, enter the name and description and click&nbsp;<strong>Next</strong>.</li>
</ul>



<ul>
<li>In&nbsp;<strong>Script settings</strong>, upload the script and configure the parameters as follows:
<ul>
<li>Run the script as a signed-in user: <strong>No</strong></li>



<li>Hide script notifications on devices: <strong>Not Configured</strong></li>



<li>Script frequency: <strong>Not Configured</strong></li>



<li>Max number of times to retry if the script fails: <strong>3 Times</strong></li>



<li>Assign the script to your device group</li>
</ul>
</li>
</ul>


<p>#!/bin/bash<br />
## Description: Checks for global preferences file and populates<br />
## it with the default portal if needed.<br />
## Body ###########################################################<br />
## Declare Variables ##############################################</p>
<p># Get current Console user<br />
active_user=$( stat -f &#8220;%Su&#8221; /dev/console )</p>
<p># Global Prefs File<br />
gPrefs=/Library/Preferences/com.paloaltonetworks.GlobalProtect.settings.plist</p>
<p>## Logic ##########################################################</p>
<p># Check to see if the global preference file already exists&#8230;<br />
if [[ -e $gPrefs ]]; then<br />
	echo &#8220;Default global portal already exists. Skipping.&#8221;<br />
else<br />
	echo &#8220;Setting default global portal to: your.portal.here.com&#8221;<br />
     # If it does not already exist, create it and populate the default portal using the echo command<br />
       echo &#8216;<?xml version="1.0" encoding="UTF-8"?><br />
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict><br />
    <key>Palo Alto Networks</key><br />
    <dict><br />
        <key>GlobalProtect</key><br />
        <dict><br />
            <key>PanSetup</key><br />
            <dict><br />
                <key>Portal</key><br />
                <string>your.portal.here.com</string><br />
                <key>Prelogon</key><br />
                <string>0</string><br />
            </dict><br />
            <key>Settings</key><br />
            <dict><br />
                <key>connect-method</key><br />
                <string>on-demand</string><br />
            </dict><br />
        </dict><br />
    </dict><br />
</dict>
</plist>
&#8216; > $gPrefs<br />
echo $?<br />
	# Kill the Preference caching daemon to prevent it from overwriting any changes<br />
	killall cfprefsd<br />
	echo $?<br />
fi<br />
# Check exit code.<br />
exit $?</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Enable 2FA for Remote Access VPN</h2>



<p>The end user must successfully authenticate through an authentication profile and a certificate profile to access a GlobalProtect portal or gateway configured, which works as a two-factor authentication. This means that certificates must be pre-deployed on the endpoints before their initial portal connection for portal authentication. A user&#8217;s client certificate must also match the requirements specified in the certificate profile.</p>



<ul>
<li>If the certificate profile does not specify a username field (<strong>Username Field</strong>&nbsp;is set to&nbsp;<strong>None</strong>), the client certificate does not require a username. In this case, the user must provide (manually) the username when authenticating against the authentication profile.</li>



<li>If the certificate profile specifies a username field, the certificate the user presents must contain a username in the corresponding field. If you do not want to force users to authenticate with a username from the certificate, do not specify a username field in the certificate profile.</li>
</ul>



<p>You have the below available options to configure 2FA for remote access VPN:</p>



<ul>
<li>Enable Two-Factor Authentication Using Certificate and Authentication Profiles</li>



<li>Enable Two-Factor Authentication Using One-Time Passwords (OTPs)</li>



<li>Enable Two-Factor Authentication Using Smart Cards</li>



<li>Enable Two-Factor Authentication Using a Software Token Application</li>
</ul>



<p>You must have a conversation with the team managing VPN solutions in your organization to choose and configure the best option.</p>



<p>However, since you are deploying the GlobalProtect VPN solution to your company&#8217;s macOS devices, I would say that the best and easiest method for enabling 2FA will be to use certificates and authentication profiles.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Deploy Global Protect Package </h2>



<ul>
<li>Log in to the Intune portal</li>
</ul>



<ul>
<li>Select&nbsp;<strong>Apps</strong>&nbsp;&gt;&nbsp;<strong>All apps</strong>&nbsp;&gt;&nbsp;<strong>Add</strong></li>
</ul>



<ul>
<li>In the&nbsp;<strong>Select app type</strong>&nbsp;pane, under the&nbsp;<strong>Other</strong>&nbsp;app types, select&nbsp;<strong>macOS LoB</strong>.</li>
</ul>



<ul>
<li>In the&nbsp;<strong>App package file</strong>&nbsp;pane, select the browse button. Then, select the GlobalProtect VPN installer that you downloaded previously. The app details will be displayed.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-90.png?resize=750%2C662&#038;ssl=1" alt="" class="wp-image-918" width="750" height="662" srcset="https://irlimages.blob.core.windows.net/2022-11/image-90.png?resize=1024%2C904&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-90.png?resize=300%2C265&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-90.png?resize=768%2C678&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-90.png?w=1076&amp;ssl=1 1076w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>Once done, deploy the app to your device group</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>End User Experience</h2>



<blockquote class="wp-block-quote">
<p>Please note that installing GlobalProtect requires an automated logout and restart of your Mac.</p>
</blockquote>



<ul>
<li>Once you have rebooted the Mac and logged in, the GlobalProtect Sign-In window should appear. Enter your corporate domain username and password and click the &#8220;Sign In&#8221; button to establish the VPN connection.&nbsp;</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-91.png?resize=388%2C221&#038;ssl=1" alt="" class="wp-image-919" width="388" height="221" srcset="https://irlimages.blob.core.windows.net/2022-11/image-91.png?w=517&amp;ssl=1 517w, https://irlimages.blob.core.windows.net/2022-11/image-91.png?resize=300%2C171&amp;ssl=1 300w" sizes="(max-width: 388px) 100vw, 388px" data-recalc-dims="1" /></figure></div>


<p>If you have multiple profiles/gateways, you might see a list/dropdown to select the profile. Select the correct profile and click connect.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-92.png?resize=233%2C314&#038;ssl=1" alt="" class="wp-image-920" width="233" height="314" srcset="https://irlimages.blob.core.windows.net/2022-11/image-92.png?w=310&amp;ssl=1 310w, https://irlimages.blob.core.windows.net/2022-11/image-92.png?resize=222%2C300&amp;ssl=1 222w" sizes="(max-width: 233px) 100vw, 233px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>And It&#8217;s connected!</em></figcaption></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Winding Up</h2>



<p>I hope you will find this post helpful in configuring and deploying GlobalProtect VPN client to your managed macOS devices with much ease now.</p>



<p>Please leave feedback and comments below if you liked it.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!--kg-card-end: html-->