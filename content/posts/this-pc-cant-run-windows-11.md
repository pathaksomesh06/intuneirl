---
title: "This PC can't run Windows 11!"
date: 2023-01-24T01:10:00"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>As the craze for Windows 11 continue growing, more and more people are installing Windows 11 everyday. For testing or educational purposes, some people install it on a PC, while others install it on a virtual machine or hypervisor.</p>



<p>The most typical situation is installing it on a virtual machine (VM), as this is the quickest and simplest method to get started. You install Hyper-V on our base machine and fire-up the VM by booting it from Win11 ISO and boom! &#8220;<strong>This PC cannot run Windows 11</strong>&#8221; appears after choosing the Windows 11 version. The minimal system requirements for installing this version of Windows are not met by this computer. Let&#8217;s understand why do we receive this notification, and what can we do about the PC&#8217;s inability to run Windows 11?</p>



<p>For full system requirements for Windows 11, check out the&nbsp;<a href="https://aka.ms/WindowsSysReq" target="_blank" rel="noreferrer noopener">Windows System Requirements</a>&nbsp;page.</p>



<h2>The Error Message</h2>



<p>After starting the virtual machine with the Windows 11 ISO, we do the initial Windows Setup processes. We receive the following notification after choosing the Windows OS we wish to install, which prevents us from moving forward. </p>



<p>If you tried to install Windows 11 on a PC or used the Microsoft PC Health Check app, you might have encountered the similar error on your computer as well that said, &#8220;This PC can&#8217;t run Windows 11&#8221;.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-65.png?resize=750%2C561&#038;ssl=1" alt="" class="wp-image-1124" width="750" height="561" srcset="https://irlimages.blob.core.windows.net/images/image-65.png?resize=1024%2C765&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-65.png?resize=300%2C224&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-65.png?resize=768%2C574&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-65.png?w=1178&amp;ssl=1 1178w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p>What&#8217;s blocking the installation here &#8211; <strong>Secure Boot and TPM 2.0</strong> are the two essential feature that may be missing from your computer. But what about if you are using a Hyper-V? So let&#8217;s understand more about these and see how to fix them as you don&#8217;t require any special skills, and you&#8217;ll just be clicking through few menus.</p>



<h2>What is TPM ?&nbsp;</h2>



<p>TPM is short for&nbsp;<strong>T</strong>rusted&nbsp;<strong>P</strong>latform&nbsp;<strong>M</strong>odule, is a computer security feature that helps keep sensitive information like passwords and encryption keys safe. Think of your smartphone which you cannot access without your biometrics and you are totally locked out if it doesn&#8217;t recognize your fingerprint, PIN or facial recognition.</p>



<p>The TPM system is available in several configurations, such as a physical chip that can be installed on a particular motherboard , a module that is already soldered to the motherboard, or one that is firmware-based and can be enabled within your BIOS without tinkering with any hardware.</p>



<p>Until Windows 11 was announced, TPM was something not many people had heard of however most pre-built computers sold within the past few years already have some sort of TPM installed or enabled.</p>



<h3>How do I check if I have a TPM chip?</h3>



<p>To see if you have a TPM chip, you just need to check the TPM Windows service. Then, you can verify the connection within Device Manager.</p>



<ol>
<li>Click the&nbsp;<strong>Windows&nbsp;</strong>icon, type, then click “<strong>tpm.msc</strong>”.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-66.png?resize=353%2C253&#038;ssl=1" alt="" class="wp-image-1125" width="353" height="253" srcset="https://irlimages.blob.core.windows.net/images/image-66.png?w=471&amp;ssl=1 471w, https://irlimages.blob.core.windows.net/images/image-66.png?resize=300%2C215&amp;ssl=1 300w" sizes="(max-width: 353px) 100vw, 353px" data-recalc-dims="1" /></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-69.png?resize=750%2C406&#038;ssl=1" alt="" class="wp-image-1128" width="750" height="406" srcset="https://irlimages.blob.core.windows.net/images/image-69.png?resize=1024%2C555&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-69.png?resize=300%2C163&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-69.png?resize=768%2C416&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-69.png?w=1256&amp;ssl=1 1256w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>TPM.msc</em></figcaption></figure></div>


<ol start="2">
<li>Hold the&nbsp;<strong>Windows&nbsp;</strong>key and type <strong>Device Manager,</strong> and hit Enter.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-68.png?resize=720%2C590&#038;ssl=1" alt="" class="wp-image-1127" width="720" height="590" srcset="https://irlimages.blob.core.windows.net/images/image-68.png?w=960&amp;ssl=1 960w, https://irlimages.blob.core.windows.net/images/image-68.png?resize=300%2C246&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-68.png?resize=768%2C629&amp;ssl=1 768w" sizes="(max-width: 720px) 100vw, 720px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Device Manager</em></figcaption></figure></div>


<ol start="3">
<li>Scroll down and expand&nbsp;<strong>Security Devices</strong>&nbsp;to confirm that the TPM is listed and is functioning correctly.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-70.png?resize=439%2C494&#038;ssl=1" alt="" class="wp-image-1129" width="439" height="494" srcset="https://irlimages.blob.core.windows.net/images/image-70.png?w=585&amp;ssl=1 585w, https://irlimages.blob.core.windows.net/images/image-70.png?resize=266%2C300&amp;ssl=1 266w" sizes="(max-width: 439px) 100vw, 439px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>TPM in Device Manager</em></figcaption></figure></div>


<h2>What is Secure Boot?</h2>



<p>Secure Boot is a security feature that is built into the firmware of your computer. It helps to protect your computer against unauthorized access. Secure Boot is incorporated into the UEFI firmware.</p>



<p>By using Secure Boot, you can ensure that only trusted software and firmware are able to boot your computer, ensuring that your system is secure. Which said, your machine won&#8217;t boot if an insecure firmware component is present while Secure Boot is off.</p>



<h2>How to enable TPM and Secure Boot</h2>



<pre class="wp-block-code"><code>Enabling TPM and Secure Boot is a straightforward process, but you need to be aware of the specific steps you need to take on different motherboard models. Before making any changes, be sure to have your motherboard’s owner’s manual handy so you can navigate both the menus and the specific terms and language used on different systems.</code></pre>



<h3>Enable TPM</h3>



<p>Upgrading your BIOS firmware can sometime give you access to the TPM settings. Often, OEM manufacturers will include specific instructions on how to install and upgrade the firmware.</p>



<h4>From Windows 10&#8217;s Start menu</h4>



<p>If you&#8217;re signed in to Windows, you can access your UEFI settings right from the Advanced Startup menu:</p>



<ol>
<li>Hold the&nbsp;<strong>Windows&nbsp;</strong>key and open the <strong>Settings app</strong>.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-71.png?resize=685%2C380&#038;ssl=1" alt="" class="wp-image-1130" width="685" height="380" srcset="https://irlimages.blob.core.windows.net/images/image-71.png?w=913&amp;ssl=1 913w, https://irlimages.blob.core.windows.net/images/image-71.png?resize=300%2C166&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-71.png?resize=768%2C426&amp;ssl=1 768w" sizes="(max-width: 685px) 100vw, 685px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Settings</em></figcaption></figure></div>


<ol start="2">
<li>Type&nbsp;<strong>Advanced</strong>, click&nbsp;<strong>Change advanced startup options</strong>, then select&nbsp;<strong>Restart Now</strong>.</li>
</ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-72.png?resize=750%2C245&#038;ssl=1" alt="" class="wp-image-1131" width="750" height="245" srcset="https://irlimages.blob.core.windows.net/images/image-72.png?resize=1024%2C335&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-72.png?resize=300%2C98&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-72.png?resize=768%2C251&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-72.png?resize=1536%2C503&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/images/image-72.png?w=1762&amp;ssl=1 1762w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Search for advanced startup options</em></figcaption></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-73.png?resize=750%2C443&#038;ssl=1" alt="" class="wp-image-1132" width="750" height="443" srcset="https://irlimages.blob.core.windows.net/images/image-73.png?w=1006&amp;ssl=1 1006w, https://irlimages.blob.core.windows.net/images/image-73.png?resize=300%2C177&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-73.png?resize=768%2C454&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Press Restart Now</em></figcaption></figure></div>


<ol start="3">
<li>In the blue&nbsp;<strong>Choose an option&nbsp;</strong>window, choose&nbsp;<strong>Troubleshoot</strong>, then&nbsp;<strong>Advanced options</strong>, followed by&nbsp;<strong>UEFI Firmware Settings</strong>.</li>
</ol>



<ol start="4">
<li>Your PC will reboot directly to your UEFI BIOS.</li>
</ol>



<h4>From start-up</h4>



<p>You can also get into your UEFI to change your TPM settings when you boot your PC. This requires you to press the BIOS key command. Once you’re in your UEFI BIOS, you can then update the TPM settings. The UEFI key command differs from motherboard to motherboard, but it will typically be&nbsp;<strong>F2</strong> or <strong>F12</strong> or <strong>DEL</strong> key.</p>



<p>In the BIOS or UEFI menu, there should be at least one option or tab labelled&nbsp;<strong>Security</strong>. Once you&#8217;re inside the Security section, you&#8217;re going to be looking for the&nbsp;<strong>TPM settings</strong>. <strong>Find the switch that turns on the TPM</strong> and enable it. </p>



<p>Once you&#8217;ve enable the TPM, click <strong>Save</strong> and restart the computer.&nbsp;</p>



<h3>Enable Secure Boot&nbsp;</h3>



<p>Enter the UEFI settings as outlined in the&nbsp;<strong>Windows 10</strong> <strong>Startup</strong>&nbsp;methods above, but this time look for the Secure Boot option. From there, just switch to Secure Boot mode.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-74.png?resize=750%2C479&#038;ssl=1" alt="" class="wp-image-1133" width="750" height="479" srcset="https://irlimages.blob.core.windows.net/images/image-74.png?resize=1024%2C653&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-74.png?resize=300%2C191&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-74.png?resize=768%2C490&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-74.png?w=1055&amp;ssl=1 1055w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Secure Boot is ON</em></figcaption></figure></div>


<p>So, this solves the purpose for installing Windows 11 on a PC or if you are upgrading from Win10 to Win11. But what if you are installing creating a test Windows 11 VM in Hyper-V and you get this message?</p>



<p>Let&#8217;s fix that also.</p>



<h2>Installing Windows 11 on a VM in Hyper-V</h2>



<p>For a Hyper-V VM, here are the things you need enabled and configure to get Windows 11 to work:</p>



<ul>
<li><strong>Gen 2 VM</strong>: As we know now that a TPM and secure boot are required for Windows 11 so, on Hyper-V, these are only available on Gen 2 VMs, <strong>so don’t try to install Windows 11 on a Gen 1 VM</strong>.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-75.png?resize=646%2C479&#038;ssl=1" alt="" class="wp-image-1134" width="646" height="479" srcset="https://irlimages.blob.core.windows.net/images/image-75.png?w=861&amp;ssl=1 861w, https://irlimages.blob.core.windows.net/images/image-75.png?resize=300%2C223&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-75.png?resize=768%2C570&amp;ssl=1 768w" sizes="(max-width: 646px) 100vw, 646px" data-recalc-dims="1" /><figcaption class="wp-element-caption">Always select Gen2 VM</figcaption></figure></div>


<ul>
<li>UEFI, Secure Boot capable: Gen 2 VMs have UEFI, which replaces the traditional BIOS on regular Gen 1 VMs and allows for Secure boot. By default, Secure Boot is enabled on Gen 2 VMs.</li>
</ul>



<ul>
<li>TPM 2.0: Hyper-V allows VMs to have a virtual TPM chip..</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-76.png?resize=664%2C629&#038;ssl=1" alt="" class="wp-image-1135" width="664" height="629" srcset="https://irlimages.blob.core.windows.net/images/image-76.png?w=885&amp;ssl=1 885w, https://irlimages.blob.core.windows.net/images/image-76.png?resize=300%2C284&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-76.png?resize=768%2C728&amp;ssl=1 768w" sizes="(max-width: 664px) 100vw, 664px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>TPM &amp; secure boot enabled</em></figcaption></figure></div>


<p>After creating the VM, we set its configuration, such as configuring the number of virtual processors and memory. We added a new DVD drive and added the ISO file to it. We then set the VM&#8217;s boot order so that the DVD will be booted first and pressed the <strong>connect</strong> button to power on the VM. You can now create a Windows 11 capable VM on Hyper-V 😉. Happy Days .</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/images/image-77.png?resize=750%2C601&#038;ssl=1" alt="" class="wp-image-1136" width="750" height="601" srcset="https://irlimages.blob.core.windows.net/images/image-77.png?resize=1024%2C820&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/images/image-77.png?resize=300%2C240&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/images/image-77.png?resize=768%2C615&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/images/image-77.png?w=1256&amp;ssl=1 1256w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Windows 11 is now installing</em></figcaption></figure></div>


<h2>Wrapping Up</h2>



<p>I hope this was helpful and that you will now be able to create a Windows 11 VMs quickly and easily on Hyper-V!</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!--kg-card-end: html-->