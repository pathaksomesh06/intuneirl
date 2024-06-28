---
title: "Security Without Sweat: Force Enable FileVault During macOS Setup Assistant"
date: 2024-02-10T10:20:58"
draft: false
tags: []
---

<p>You can now enforce&nbsp;FileVault during Setup Assistant with macOS 14. You have the option as an Intune admin to either escrow the FileVault recovery key to your Entra ID or to display it during Setup Assistant.</p><p>In this article, I'll walk you through the steps of enabling FileVault during the macOS Setup Assistant and discuss how you can streamline this process using Intune, a mobile device management solution. By taking this proactive security measure, you can ensure the safety of your sensitive information and maintain peace of mind.</p><hr><h3 id="what-is-filevault-and-why-is-it-important"><strong>What is FileVault and why is it important?</strong></h3><p>FileVault is a disk encryption feature built into macOS that helps protect your data by encrypting your entire hard drive. It ensures that your files, documents, and sensitive information can only be accessed by someone with the correct password. </p><p>FileVault uses the <strong><u>AES-XTS</u></strong> data encryption algorithm to protect full volumes on internal and removable storage devices. FileVault on a Mac with Apple silicon is implemented using Data Protection Class C with a volume key. On Mac computers with Apple silicon and Mac computers with the Apple T2 Security Chip, encrypted internal storage devices directly connected to the Secure Enclave leverage its hardware security capabilities as well as that of the AES engine. <strong><u>After a user turns on FileVault on a Mac, their credentials are required during the boot process</u></strong>.</p><p>So, why is FileVault important? The answer is simple: data security. In this digital age, we store a vast amount of personal and confidential information on our computers, including financial details, passwords, and sensitive work documents. Without proper encryption, this data is at risk of being accessed or stolen by hackers, thieves, or even unauthorized individuals.</p><p>By enabling FileVault during the macOS Setup Assistant, you are taking a proactive step to safeguard your data effortlessly right from the start. The process is straightforward and requires no technical expertise, making it accessible to users of all levels.</p><hr><h3 id="the-challenge"><strong>The Challenge</strong></h3><p>Ensuring the highest level of data security is paramount for any enterprise allowing Macs within its technological ecosystem. The integration of Macs into an MDM solution necessitates a proactive approach to safeguard sensitive information. Foremost in this security strategy is the activation of FileVault, Apple's powerful disk encryption program, on all Mac devices as they are enrolled.</p><p>It's critical to understand, that, Microsoft Intune cannot currently activate FileVault during initial device setup using Settings Catalog and you can expect to be released soon.</p><figure class="kg-card kg-bookmark-card"><a class="kg-bookmark-container" href="https://learn.microsoft.com/en-us/mem/intune/fundamentals/in-development#macos-settings"><div class="kg-bookmark-content"><div class="kg-bookmark-title">In development - Microsoft Intune</div><div class="kg-bookmark-description">This article describes Microsoft Intune features that are in development.</div><div class="kg-bookmark-metadata"><img class="kg-bookmark-icon" src="https://learn.microsoft.com/favicon.ico" alt=""><span class="kg-bookmark-author">Microsoft Learn</span><span class="kg-bookmark-publisher">dougeby</span></div></div><div class="kg-bookmark-thumbnail"><img src="https://learn.microsoft.com/en-us/media/open-graph-image.png" alt=""></div></a></figure><p>This procedural gap poses a significant risk; it leaves a window of vulnerability where sensitive data could be exposed to unauthorized access. In an ideal scenario, the activation of FileVault would be an integral step of the enrollment process, ensuring that from the moment a Mac is registered, its data is encrypted and protected.</p><hr><h3 id="the-solution-forceenableinsetupassistant"><strong>The Solution: </strong><code>ForceEnableInSetupAssistant</code></h3><p>Using the&nbsp;<code>ForceEnableInSetupAssistant</code>&nbsp;key in a configuration profile, you can enforce to turn on FileVault during Setup Assistant. This ensures that the internal storage in managed Mac computers is always encrypted before being used. Depending on your MDM policies, you can decide whether to show the FileVault recovery key to the user or to escrow the personal recovery key. </p><div class="kg-card kg-callout-card kg-callout-card-blue"><div class="kg-callout-emoji">💡</div><div class="kg-callout-text">For this feature to work, the user account that was created interactively during Setup Assistant must have the role of Administrator.</div></div><p>Also, it is important to understand here that, if&nbsp;you are using this payload then the system also ignores all other keys in this payload, except for&nbsp;<code>ShowRecoveryKey</code>.</p><p>To bridge this gap, I created the below custom configuration profile to ship this key to the Mac, which will be used during enrolment. </p><pre><code>&lt;?xml version="1.0" encoding="UTF-8"?&gt;
&lt;!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"&gt;
&lt;plist version="1.0"&gt;
	&lt;dict&gt;
		&lt;key&gt;PayloadContent&lt;/key&gt;
		&lt;array&gt;
			&lt;dict&gt;
				&lt;key&gt;DeferForceAtUserLoginMaxBypassAttempts&lt;/key&gt;
				&lt;integer&gt;-1&lt;/integer&gt;
				&lt;key&gt;Enable&lt;/key&gt;
				&lt;string&gt;On&lt;/string&gt;
				&lt;key&gt;ForceEnableInSetupAssistant&lt;/key&gt;
				&lt;true/&gt;
				&lt;key&gt;OutputPath&lt;/key&gt;
				&lt;string&gt;"https://portal.manage.microsoft.com"&lt;/string&gt;
				&lt;key&gt;PayloadDisplayName&lt;/key&gt;
				&lt;string&gt;FileVault-SA&lt;/string&gt;
				&lt;key&gt;PayloadIdentifier&lt;/key&gt;
				&lt;string&gt;com.apple.MCX.FileVault2.ED155FB6&lt;/string&gt;
				&lt;key&gt;PayloadType&lt;/key&gt;
				&lt;string&gt;com.apple.MCX.FileVault2&lt;/string&gt;
				&lt;key&gt;PayloadUUID&lt;/key&gt;
				&lt;string&gt;E0BC271E-6339-4338-BB4D&lt;/string&gt;
				&lt;key&gt;PayloadVersion&lt;/key&gt;
				&lt;integer&gt;1&lt;/integer&gt;
				&lt;key&gt;UserEntersMissingInfo&lt;/key&gt;
				&lt;false/&gt;
			&lt;/dict&gt;
		&lt;/array&gt;
		&lt;key&gt;PayloadDescription&lt;/key&gt;
		&lt;string&gt;Enable Filevault in Setup Assistant&lt;/string&gt;
		&lt;key&gt;PayloadDisplayName&lt;/key&gt;
		&lt;string&gt;filevault2&lt;/string&gt;
		&lt;key&gt;PayloadIdentifier&lt;/key&gt;
		&lt;string&gt;IRL.BB074437-36A8-4AE5-A82F-D9062972B3FD&lt;/string&gt;
		&lt;key&gt;PayloadOrganization&lt;/key&gt;
		&lt;string&gt;IRL&lt;/string&gt;
		&lt;key&gt;PayloadScope&lt;/key&gt;
		&lt;string&gt;System&lt;/string&gt;
		&lt;key&gt;PayloadType&lt;/key&gt;
		&lt;string&gt;Configuration&lt;/string&gt;
		&lt;key&gt;PayloadUUID&lt;/key&gt;
		&lt;string&gt;23524AC4-F0E0-4B0D-ADC1-D75AC20D34BF&lt;/string&gt;
		&lt;key&gt;PayloadVersion&lt;/key&gt;
		&lt;integer&gt;1&lt;/integer&gt;
		&lt;key&gt;TargetDeviceType&lt;/key&gt;
		&lt;integer&gt;5&lt;/integer&gt;
	&lt;/dict&gt;
&lt;/plist&gt;
</code></pre><hr><p><strong>Configure The Profile in Intune</strong></p><p>Follow the below steps to deploy this custom configuration profile to your Mac devices:</p><ul><li>Sign in to the&nbsp;<a href="https://intune.microsoft.com/" rel="noreferrer">Microsoft Intune admin center</a></li><li>Navigate to Devices-&gt;macOS-&gt;Configuration Profiles</li><li>Select&nbsp;<strong>Create-&gt;New Policy</strong></li></ul><figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2024/02/Screenshot-2024-02-10-at-13.10.16.png" class="kg-image" alt="" loading="lazy" width="2000" height="757" srcset="__GHOST_URL__/content/images/size/w600/2024/02/Screenshot-2024-02-10-at-13.10.16.png 600w, __GHOST_URL__/content/images/size/w1000/2024/02/Screenshot-2024-02-10-at-13.10.16.png 1000w, __GHOST_URL__/content/images/size/w1600/2024/02/Screenshot-2024-02-10-at-13.10.16.png 1600w, __GHOST_URL__/content/images/2024/02/Screenshot-2024-02-10-at-13.10.16.png 2012w" sizes="(min-width: 720px) 720px"></figure><ul><li><strong>Profile type</strong>: Select&nbsp;<strong>Custom</strong>. Or, select&nbsp;<strong>Templates</strong>&nbsp;&gt;&nbsp;<strong>Custom</strong></li></ul><figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2024/02/Screenshot-2024-02-10-at-13.11.33.png" class="kg-image" alt="" loading="lazy" width="1156" height="1674" srcset="__GHOST_URL__/content/images/size/w600/2024/02/Screenshot-2024-02-10-at-13.11.33.png 600w, __GHOST_URL__/content/images/size/w1000/2024/02/Screenshot-2024-02-10-at-13.11.33.png 1000w, __GHOST_URL__/content/images/2024/02/Screenshot-2024-02-10-at-13.11.33.png 1156w" sizes="(min-width: 720px) 720px"></figure><ul><li>In&nbsp;<strong>Basics</strong>, enter the name &amp; description</li></ul><figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2024/02/image-1.png" class="kg-image" alt="" loading="lazy" width="1768" height="873" srcset="__GHOST_URL__/content/images/size/w600/2024/02/image-1.png 600w, __GHOST_URL__/content/images/size/w1000/2024/02/image-1.png 1000w, __GHOST_URL__/content/images/size/w1600/2024/02/image-1.png 1600w, __GHOST_URL__/content/images/2024/02/image-1.png 1768w" sizes="(min-width: 720px) 720px"></figure><p></p><ul><li><strong>Configuration profile name</strong>: Enter a name for the policy</li><li><strong>Deployment channel</strong>: Select device channel</li><li><strong>Configuration profile file</strong>: Browse to the&nbsp;<code>.mobileconfig</code>&nbsp;file</li></ul><figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2024/02/image-2.png" class="kg-image" alt="" loading="lazy" width="1702" height="1638" srcset="__GHOST_URL__/content/images/size/w600/2024/02/image-2.png 600w, __GHOST_URL__/content/images/size/w1000/2024/02/image-2.png 1000w, __GHOST_URL__/content/images/size/w1600/2024/02/image-2.png 1600w, __GHOST_URL__/content/images/2024/02/image-2.png 1702w" sizes="(min-width: 720px) 720px"></figure><ul><li>Assign the profile to the required group.</li></ul><hr><h3 id="demo"><strong>Demo</strong></h3><figure class="kg-card kg-embed-card"><iframe width="200" height="113" src="https://www.youtube.com/embed/PKA9BsFqNbc?feature=oembed" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen="" title="Enable FileVault during Setup Assistant"></iframe></figure><hr><h3 id="the-result"><strong>The Result</strong></h3><p>With the profile in place, FileVault activation became a non-negotiable aspect of the Setup Assistant, effectively closing the initial security gap. Users proceeded through the familiar setup flow, witnessing FileVault seamlessly enabled in the background, without requiring any additional interaction.</p><p>And, by leveraging the optional "Disable FileVault recovery key creation" setting, the setup process remained user-friendly while maintaining robust security. </p><p>Stay tuned for more valuable insights on securing your Mac.</p>