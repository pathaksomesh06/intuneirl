---
title: "Deploy Cisco AnyConnect VPN on macOS devices with 2FA"
date: 2022-11-15T01:46:49"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<h2>Background</h2>



<p>This post is once again focused on macOS devices since, over the past few days, there have been discussions in various communities about installing the Cisco AnyConnect VPN solution on business-owned macOS machines. So, I thought of sharing my own experience of deploying the VPN solution with no user interaction required and, at the same time, securing it 2FA. Reason for 2FA – Ensure that users can only connect to this VPN solution from a corporate device, as anyone can easily download & connect the VPN client from their personal devices.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Cisco AnyConnect VPN Deployment</h2>



<p>Like any other VPN solution, the Cisco AnyConnect VPN allows you to connect to the corporate network allowing access to specific allowed resources and services as if you are on the corporate network.</p>



<p id="ID-1425-00000005__ID-1425-00000006">Deploying AnyConnect involves <strong><span style="text-decoration: underline;">silently installing, configuring, and upgrading the AnyConnect client</span></strong> and its related files on end user’s devices:</p>



<p id="ID-1425-00000005__ID-1425-00000007">The Cisco AnyConnect Secure Mobility Client can be deployed remotely to devices by the following methods:</p>



<ul><li><strong>Predeploy </strong>– The end-user does new installations and upgrades, or it is pushed using an enterprise device management system.</li></ul>



<ul><li><strong>Web Deploy</strong> – The AnyConnect package is loaded on the headend, an ASA or FTD firewall, or an ISE server. When the user connects to a firewall or ISE, AnyConnect is deployed to the client.</li></ul>



<p>You can include optional modules that enable supplemental features, client profiles that set up the VPN, and optional features when you deploy AnyConnect.</p>



<p>As we are focused on Intune as an enterprise device management system, in this article, we will focus on the first approach of deployment, i.e. “Predeploy”.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>What Do You Need To Start With?</h2>



<p>To start with, you need to have access to the following:</p>



<ul><li>AnyConnect package</li><li>Modules to support extra features</li><li>Client profiles that configure AnyConnect and the extra features, which you will create</li><li>Language files, images, scripts, and help files for customizing the deployment</li><li>AnyConnect ISE Posture and the compliance module</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>AnyConnect System Extension</h2>



<p>AnyConnect uses a network system extension on macOS 11 (and later), bundled into an application named Cisco AnyConnect Socket Filter. The AnyConnect extension has the following three components that are visible in the macOS System Preferences-Network UI window:</p>



<ul><li>DNS proxy</li><li>App/transparent proxy</li><li>Content filter</li></ul>



<p>AnyConnect requires its system extension and all its components to be active for proper operation, which implies that the mentioned components are all present and show as green (running) in the left pane of the macOS Network UI.</p>



<p>For installation in the system context, macOS requires the extension to be approved via MDM without end-user interaction. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Intune Configurations</h2>



<p>To approve the AnyConnect system extension without end-user interaction, we need to push the system extension payload to the devices using Intune. To do so, follow these steps:</p>



<ol><li>Login to <a href="https://intune.microsoft.com/#home" target="_blank" rel="noopener" title="">Intune portal</a>.</li></ol>



<ol start="2"><li>Navigate to <strong>Devices -> macOS -> Configuration Profiles</strong> and select create a profile.</li></ol>



<ol start="3"><li>From the profile type dropdown, select Templates -><strong>Extensions </strong>profile</li></ol>



<p> </p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-44.png?resize=750%2C450&ssl=1" alt="" class="wp-image-783" width="750" height="450" srcset="https://irlimages.blob.core.windows.net/2022-11/image-44.png?resize=1024%2C614&ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-44.png?resize=300%2C180&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-44.png?resize=768%2C461&ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-44.png?resize=1536%2C922&ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/image-44.png?w=1565&ssl=1 1565w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="4"><li>In <strong>Basics</strong>, enter the name & description to match the purpose of the profile.</li></ol>



<ol start="5"><li>In the <strong>System Extensions</strong> – Set the Team identification to “<strong>DE8Y96K9QP</strong>” and the Bundle identifier to “<strong>com.cisco.anyconnect.macos.acsockext</strong>“</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-47.png?resize=518%2C125&ssl=1" alt="" class="wp-image-786" width="518" height="125" srcset="https://irlimages.blob.core.windows.net/2022-11/image-47.png?w=691&ssl=1 691w, https://irlimages.blob.core.windows.net/2022-11/image-47.png?resize=300%2C73&ssl=1 300w" sizes="(max-width: 518px) 100vw, 518px" data-recalc-dims="1" /></figure></div>


<ol start="7"><li>Under Allowed system extension types, add a line to allow team identifier “DE8Y96K9QP” to provide “Network extensions”.</li></ol>



<ol start="8"><li>Next, review and assign it to the required group.</li></ol>



<p>This is how the configuration profile should look like:</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-48.png?resize=668%2C287&ssl=1" alt="" class="wp-image-787" width="668" height="287" srcset="https://irlimages.blob.core.windows.net/2022-11/image-48.png?w=890&ssl=1 890w, https://irlimages.blob.core.windows.net/2022-11/image-48.png?resize=300%2C129&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-48.png?resize=768%2C330&ssl=1 768w" sizes="(max-width: 668px) 100vw, 668px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>WebContentFilter Payload Settings</h2>



<p>Sadly, there isn’t a way to accomplish this via the online UI of Microsoft Intune. You must first build an XML configuration and then upload it as a configuration profile. To do so, please follow the steps:</p>



<ol><li>Login to <a href="https://intune.microsoft.com/#home" target="_blank" rel="noopener" title="">Intune portal</a>.</li></ol>



<ol start="2"><li>Navigate to <strong>Devices -> macOS -> Configuration Profiles</strong> and select create a profile.</li></ol>



<ol start="3"><li>From the profile type dropdown, select Templates -><strong>Custom </strong>profile</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-49.png?resize=750%2C456&ssl=1" alt="" class="wp-image-788" width="750" height="456" srcset="https://irlimages.blob.core.windows.net/2022-11/image-49.png?resize=1024%2C622&ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-49.png?resize=300%2C182&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-49.png?resize=768%2C467&ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-49.png?resize=1536%2C933&ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-11/image-49.png?w=1557&ssl=1 1557w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="4"><li>In <strong>Basics</strong>, enter the name & description to match the purpose of the profile.</li></ol>



<ol start="5"><li>You can use the below table to create your XML file:</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-50.png?resize=483%2C299&ssl=1" alt="" class="wp-image-789" width="483" height="299" srcset="https://irlimages.blob.core.windows.net/2022-11/image-50.png?w=965&ssl=1 965w, https://irlimages.blob.core.windows.net/2022-11/image-50.png?resize=300%2C186&ssl=1 300w, v?resize=768%2C476&ssl=1 768w" sizes="(max-width: 483px) 100vw, 483px" data-recalc-dims="1" /></figure></div>


<p>Or, you can copy-paste and save this as XML to upload to the profile:</p>


<p><?xml version="1.0" encoding="UTF-8"?><br />
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
    <dict><br />
        <key>PayloadContent</key><br />
        <array><br />
            <dict><br />
                <key>Enabled</key><br />
                <true/>
                <key>FilterType</key><br />
                <string>Plugin</string><br />
                <key>AutoFilterEnabled</key><br />
                <false/><br />
                <key>FilterBrowsers</key><br />
                <false/><br />
                <key>FilterSockets</key><br />
                <true/>
                <key>FilterPackets</key><br />
                <false/><br />
                <key>FilterGrade</key><br />
                <string>firewall</string><br />
                <key>FilterDataProviderBundleIdentifier</key><br />
                <string>com.cisco.anyconnect.macos.acsockext</string><br />
                <key>FilterDataProviderDesignatedRequirement</key><br />
                <string>anchor apple generic and identifier “com.cisco.anyconnect.macos.acsockext” and (certificate leaf[field.1.2.840.113635.100.6.1.9] /* exists */ or certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = DE8Y96K9QP)</string><br />
                <key>PluginBundleID</key><br />
                <string>com.cisco.anyconnect.macos.acsock</string><br />
                <key>VendorConfig</key><br />
                <dict/><br />
                <key>UserDefinedName</key><br />
                <string>Cisco AnyConnect Content Filter</string><br />
                <key>PayloadDisplayName</key><br />
                <string>Cisco AnyConnect Content Filter</string><br />
                <key>PayloadIdentifier</key><br />
                <string>com.cisco.anyconnect.webcontentfilter.42B8BA0E-57F4-4E57-872B-1F5FCB8527EA.2512DB6A-B5EA-41DB-B6C6-3A07726C214E</string><br />
                <key>PayloadType</key><br />
                <string>com.apple.webcontent-filter</string><br />
                <key>PayloadUUID</key><br />
                <string>2512DB6A-B5EA-41DB-B6C6-3A07726C214E</string><br />
                <key>PayloadVersion</key><br />
                <integer>1</integer><br />
            </dict><br />
        </array><br />
        <key>PayloadDisplayName</key><br />
        <string>Cisco AnyConnect Content Filter</string><br />
        <key>PayloadIdentifier</key><br />
        <string>com.cisco.anyconnect.webcontentfilter.42B8BA0E-57F4-4E57-872B-1F5FCB8527EA</string><br />
        <key>PayloadScope</key><br />
        <string>System</string><br />
        <key>PayloadType</key><br />
        <string>Configuration</string><br />
        <key>PayloadUUID</key><br />
        <string>42B8BA0E-57F4-4E57-872B-1F5FCB8527EA</string><br />
        <key>PayloadVersion</key><br />
        <integer>1</integer><br />
    </dict>
</plist>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-51.png?resize=750%2C391&ssl=1" alt="" class="wp-image-790" width="750" height="391" srcset="https://irlimages.blob.core.windows.net/2022-11/image-51.png?w=1001&ssl=1 1001w, https://irlimages.blob.core.windows.net/2022-11/image-51.pngg?resize=300%2C156&ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-51.png?resize=768%2C400&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Cisco AnyConnect Profile</h2>



<p>As a next step, we will create the required profile for the VPN client and will push it to the devices as a shell script.</p>



<p><strong><span style="text-decoration: underline;">Shell Script for profile:</span></strong></p>


<p>!/bin/sh</p>
<p>mkdir -p /opt/cisco/anyconnect/profile</p>
<p>cat <<EOF>/opt/cisco/anyconnect/profile/profile.xml<br />
<?xml version="1.0" encoding="UTF-8"?><br />
<AnyConnectProfile xmlns="http://schemas.xmlsoap.org/encoding/"><br />
<ServerList><br />
<HostEntry><br />
<HostName>x.x.x.x</HostName><br />
<HostAddress>https://x.x.x.x</HostAddress><br />
</HostEntry><br />
</ServerList><br />
</AnyConnectProfile><br />
EOF</p>



<ul><li>Sign in to the <a href="https://intune.microsoft.com" target="_blank" rel="noopener" title="">Intune portal.</a></li></ul>



<ul><li>Select <strong>Devices</strong> > <strong>macOS</strong> > <strong>Shell scripts</strong> > <strong>Add</strong>.</li></ul>



<ul><li>In <strong>Basics</strong>, enter the name and description and click <strong>Next</strong>.</li></ul>



<ul><li>In <strong>Script settings</strong>, upload the script and configure the parameters as follows:<ul><li>Run the script as a signed-in user: <strong>No</strong></li><li>Hide script notifications on devices: <strong>Not Configured</strong></li><li>Script frequency: <strong>Not Configured</strong></li><li>Max number of times to retry if script fails: <strong>3 Times</strong></li></ul></li></ul>



<ul><li>Assign the script to your device group</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Cisco AnyConnect Package</h2>



<p>When it comes to iOS/macOS devices, I prefer to push the corporate apps as LOB apps as it gives more control over the app. </p>



<p><strong>P.S –</strong> <strong>The feature is in public preview</strong></p>



<p>The following prerequisites must be met before a macOS DMG app is installed on macOS devices.</p>



<ol><li>Intune manages devices.</li><li>DMG app is smaller than 2GB in size.</li><li>The <a href="https://learn.microsoft.com/en-us/mem/intune/apps/lob-apps-macos-agent">Microsoft Intune management agent for macOS</a> is installed.</li></ol>



<p>Follow the steps to push the VPN client to the devices:</p>



<ul><li>Sign in to the <a href="https://go.microsoft.com/fwlink/?linkid=2109431">Intune portal</a>.</li></ul>



<ul><li>Select <strong>Apps</strong> > <strong>All apps</strong> > <strong>Add</strong>.</li></ul>



<ul><li>In the <strong>Select app type</strong> pane, under the <strong>Other</strong> app types, select <strong>macOS app (DMG)</strong>.</li></ul>



<ul><li>In the <strong>App package file</strong> pane, select the browse button. Then, select the Cisco AnyConnect VPN DMG file with the extension <em>.dmg</em>. The app details will be displayed.</li></ul>



<ul><li>When you’re finished, select <strong>OK</strong> on the <strong>App package file</strong> pane to add the app.</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-52.png?resize=551%2C387&ssl=1" alt="" class="wp-image-791" width="551" height="387" srcset="https://irlimages.blob.core.windows.net/2022-11/image-52.png?w=734&ssl=1 734w, https://irlimages.blob.core.windows.net/2022-11/image-52.png?resize=300%2C211&ssl=1 300w" sizes="(max-width: 551px) 100vw, 551px" data-recalc-dims="1" /></figure></div>


<ul><li>Once done, deploy the app to your device group.</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Trespassing Not Allowed</h2>



<p>Alright, so by now, you have deployed the VPN app and configured all the required settings so that the app gets installed without any user interaction.</p>



<p>Now, as the last part of this post, let’s control the configuration so that the connection can only be initiated from a corporate device.</p>



<p>And to achieve this, you need to define specific parameters in the Cisco ISE platform that ensures that the device initiating the connection is a corporate device. There are numerous ways of doing it; you just need to make sure that the parameter you define is unique and cannot be modified at the device level.</p>



<p>An example of configuration:</p>



<ol><li>You check for your SHA1 signature of any signed/wrapped app deployed on the macOS devices.</li><li>You specify the path of a specific file that is hardcoded in the system preferences where user access is restricted.</li><li>Device latest patch level with MDE</li></ol>



<p>So, when the user initiates the VPN connection, the device will be evaluated first and once passed, only then will it be allowed to access corporate resources.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Summary</h2>



<p>You can easily deploy the Cisco Anyconnect VPN client to your corporate macOS devices. </p>



<p>I’d love to know what you think, so do leave your comments below, and if you liked it, then do share it. </p>



<p><strong>Cheers</strong>/</p>



<p>Somesh</p>

<!--kg-card-end: html-->
