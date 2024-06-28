---
title: "Security Benchmark for macOS - Best Practice Guide"
date: 2022-11-10T12:45:55"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>There has always been a perception that macOS devices are safer than Windows PCs in terms of security. The idea that Apple devices are impenetrable, or secure is widespread. But those times are long gone, as both platforms have seen zero-dat attacks and number of vunerabilities exposed in every OS release.</p>



<p>I&#8217;ll provide you with a list of configurations and settings in this article that you may use to strengthen the overall security of your macOS device fleet.</p>



<h3>Disclaimer:</h3>



<p>This guide is provided on an &#8216;as is basis without any warranties. You are responsible if you break anything or if something stops functioning as it should.</p>



<h3>Benchmarks</h3>



<p>This guide is based on recommendations from the Center for Internet Security (CIS) Benchmark as they are globally recognized and consensus-driven best practices for cybersecurity defences.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>User Accounts &amp; Access</h2>



<p>When you power on the Macbook for the first, it goes through setup assistant screen which ask you to set  a name, a username, and a password in order to set up your first user account. This account by default becomes the local administrator. Administrator accounts have the ability to modify or remove any file and install any program, which could be dangerous if the program is malicious. </p>



<ul><li>Disable password hints on logon window</li><li>Force logon window to show username and password screen</li><li>Disbale Guest accounts</li><li>Remove guest home folder</li><li>Enable file name extensions</li><li>Enable parental controls</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>System Preferences &amp; Restrictions</h2>



<p>With Microsoft Intune, you can configure and enforce configurations and restrictions as minimum standard baselines for securing your MacBooks. These configurations &amp; restrictions will help in protecting remote attacks on the device.</p>



<ul><li>Disable Bluetooth and Bluetooth Discoverable Mode</li></ul>



<p>Apple does not allow MDM vendors to control the Bluetooth payload directly, so you will not find any setting in Intune portal to disable Bluetooth. However, you can still push a custom bash script to disable Bluetooth on your corporate macOS devices.</p>



<pre class="wp-block-code has-small-font-size"><code>#!/bin/sh 
$ sudo defaults write/Library/Preferences/com.apple.Bluetooth ControllerPowerState -int 0
$ sudo killall -HUP bluetoothd                          </code></pre>



<ul start="2"><li>Enforce set time and date automatically</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-10.png?resize=479%2C145&#038;ssl=1" alt="" class="wp-image-723" width="479" height="145" srcset="https://irlimages.blob.core.windows.net/2022-11/image-10.png?w=958&amp;ssl=1 958w, https://irlimages.blob.core.windows.net/2022-11/image-10.png?resize=300%2C91&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-10.png?resize=768%2C232&amp;ssl=1 768w" sizes="(max-width: 479px) 100vw, 479px" data-recalc-dims="1" /></figure></div>


<ul><li>Secure screen-saver corners and inactivity level</li></ul>



<p>There is no default configuration available for securing the screensaver, but you can use the script available here to configure hot corner settings &#8211; <a href="https://gist.github.com/jmahlman/058a5e83a3df7c5e8b50fa0a3067b282" target="_blank" rel="noopener" title="">Github</a></p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-12.png?resize=300%2C276&#038;ssl=1" alt="" class="wp-image-725" width="300" height="276" srcset="https://irlimages.blob.core.windows.net/2022-11/image-12.png?w=599&amp;ssl=1 599w, https://irlimages.blob.core.windows.net/2022-11/image-12.png?resize=300%2C276&amp;ssl=1 300w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" /></figure></div>


<ul><li>Disable Sharing:</li></ul>



<ul><li>Disable Remote Apple Events in Sharing<ul><li>Disable Internet Sharing</li><li>Disable Screen Sharing</li><li>Disable Printer Sharing</li><li>Disable Remote Login (SSH)</li><li>Disable DVD or CD Sharing</li><li>Disable Bluetooth Sharing</li><li>Disable File Sharing</li><li>Disable Remote Management</li></ul></li></ul>



<ul><li>Energy Saver</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-13.png?resize=441%2C66&#038;ssl=1" alt="" class="wp-image-726" width="441" height="66" srcset="https://irlimages.blob.core.windows.net/2022-11/image-13.png?w=881&amp;ssl=1 881w, https://irlimages.blob.core.windows.net/2022-11/image-13.png?resize=300%2C45&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-13.png?resize=768%2C115&amp;ssl=1 768w" sizes="(max-width: 441px) 100vw, 441px" data-recalc-dims="1" /></figure></div>


<ul><li>Enable FileVault</li></ul>



<ul><li>Enable Encryption of all volumes</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-14.png?resize=475%2C367&#038;ssl=1" alt="" class="wp-image-727" width="475" height="367" srcset="https://irlimages.blob.core.windows.net/2022-11/image-14.png?w=949&amp;ssl=1 949w, https://irlimages.blob.core.windows.net/2022-11/image-14.png?resize=300%2C232&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-14.png?resize=768%2C594&amp;ssl=1 768w" sizes="(max-width: 475px) 100vw, 475px" data-recalc-dims="1" /></figure></div>


<ul><li>Enable Firewall, Gatekeeper &amp; Stealth Mode</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-15.png?resize=515%2C128&#038;ssl=1" alt="" class="wp-image-728" width="515" height="128" srcset="https://irlimages.blob.core.windows.net/2022-11/image-15.png?w=687&amp;ssl=1 687w, https://irlimages.blob.core.windows.net/2022-11/image-15.png?resize=300%2C74&amp;ssl=1 300w" sizes="(max-width: 515px) 100vw, 515px" data-recalc-dims="1" /></figure></div>


<ul><li>Enable location services and disable sending diagnostic data to Apple</li></ul>



<ul><li>Block iCloud backup</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-16.png?resize=294%2C184&#038;ssl=1" alt="" class="wp-image-729" width="294" height="184" srcset="https://irlimages.blob.core.windows.net/2022-11/image-16.png?w=587&amp;ssl=1 587w, https://irlimages.blob.core.windows.net/2022-11/image-16.png?resize=300%2C188&amp;ssl=1 300w" sizes="(max-width: 294px) 100vw, 294px" data-recalc-dims="1" /></figure></div>


<ul><li>Enforce Time Machine Auto Backups</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-17.png?resize=497%2C210&#038;ssl=1" alt="" class="wp-image-730" width="497" height="210" srcset="https://irlimages.blob.core.windows.net/2022-11/image-17.png?w=994&amp;ssl=1 994w, https://irlimages.blob.core.windows.net/2022-11/image-17.png?resize=300%2C127&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-17.png?resize=768%2C325&amp;ssl=1 768w" sizes="(max-width: 497px) 100vw, 497px" data-recalc-dims="1" /></figure></div>


<ul><li>Block Game Center</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-18.png?resize=473%2C144&#038;ssl=1" alt="" class="wp-image-731" width="473" height="144" srcset="https://irlimages.blob.core.windows.net/2022-11/image-18.png?w=631&amp;ssl=1 631w, https://irlimages.blob.core.windows.net/2022-11/image-18.png?resize=300%2C91&amp;ssl=1 300w" sizes="(max-width: 473px) 100vw, 473px" data-recalc-dims="1" /></figure></div>


<ul><li>Enable security audits and retain logs for at least 60-90 days.</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Updates &amp; Patches</h2>



<p>Using Intune, you can easily create &amp; deploy OS update policies to ensure that your macOS devices are always updated and fully patched.</p>



<ul><li>Enable Auto Update</li></ul>



<ul><li>Enable app update installs</li></ul>



<ul><li>Enable system data files and security update installs</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-19.png?resize=635%2C411&#038;ssl=1" alt="" class="wp-image-732" width="635" height="411" srcset="https://irlimages.blob.core.windows.net/2022-11/image-19.png?w=847&amp;ssl=1 847w, https://irlimages.blob.core.windows.net/2022-11/image-19.png?resize=300%2C194&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-19.png?resize=768%2C497&amp;ssl=1 768w" sizes="(max-width: 635px) 100vw, 635px" data-recalc-dims="1" /></figure></div>


<ul><li>Configure Update Policies for macOS</li></ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-20.png?resize=750%2C327&#038;ssl=1" alt="" class="wp-image-733" width="750" height="327" srcset="https://irlimages.blob.core.windows.net/2022-11/image-20.png?w=1017&amp;ssl=1 1017w, https://irlimages.blob.core.windows.net/2022-11/image-20.png?resize=300%2C131&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-20.png?resize=768%2C335&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Network Configurations</h2>



<p>Few network configurations are also required to reduce the network-based attacks on the corporate devices.</p>



<ul><li>Configure Firewall<ul><li>Before you <em>Block all incoming connections</em>, ensure that you allow<em> signed software</em> in the firewall setting to receive incoming connections to allow digitally signed applications access to your network without prompting.</li><li>Configure the firewall policy to block all inbound and outbound traffic that isn’t expressly permitted as an organization policy.</li><li>Enable &#8220;Wi-Fi&#8221; status to be shown in menu bar.</li><li>Block FTP, HTTP &amp; NFS</li></ul></li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Enable &amp; Activate Antivirus Protection</h2>



<p>It is true to some extent that Mac is a bit more secure as compared to Windows but still they can be infected by malware, malicious softwares/files or any zero-day attacks. To make sure, your devices are always protected, an enterprise endpoint security platform should always be installed on these devices.</p>



<p>You can refer to one of my previous article, to onboard the corporate owned macOS devices in Microsoft Defender for Endpoint:</p>



<p> <a href="__GHOST_URL__/macos-management-with-intune-part-ii//">macOS Management with Intune – Part II &#8211; Intune &#8211; In Real Life (intuneirl.com)</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Security Configurations</h2>



<p>With Intune, you can easily create and enforce baseline security policies to keep the corporate MacBooks secure.</p>



<ul><li>Enforce strong password policies</li></ul>



<ul><li>Enforce password age &amp; history requirements&#8217;</li></ul>



<ul><li>Configure keychain to be automatically locked in case of inactivity</li></ul>



<ul><li>Block the root account</li></ul>



<ul><li>Block auto-login</li></ul>



<ul><li>If possible use managed Apple ID</li></ul>



<ul><li>Enforce the mac to require password on wake-up or from screen saver</li></ul>



<ul><li>Block access to modifying system preferences</li></ul>



<ul><li>Configure a corporate wallpaper &amp; screensaver</li></ul>



<ul><li>Configure account lockout threshold</li></ul>



<ul><li>Secure home folders</li></ul>



<ul><li>Enforce the corporate naming convention for macOS devices</li></ul>



<ul><li>Block USB &amp; external storage/media</li></ul>



<ul><li>Deploy software metering &amp; inventory applications to keep a track of software installed on the MacBooks</li></ul>



<ul><li>Secure access to EFI with stong password</li></ul>



<ul><li>Block Airdrop as unmanaged location</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Wrapping Up</h2>



<p>It is an everlasting list and it depends upon how secure you want the devices to be. Many of the settings, restrictions or configurations we discussed are pretty simple and should always be implemented. However, before you implement any of these benchmark, it is always advisable to perform a risk assessment of your environment and based on the feedback you should implement the policies.</p>



<p>I hope this will help you with configuring policies in Intune with giving more granular control over these modern and trendy devices. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!--kg-card-end: html-->