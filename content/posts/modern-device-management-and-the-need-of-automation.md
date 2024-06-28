---
title: "Modern Device Management and The Need of Automation"
date: 2023-01-26T17:47:24"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p class="has-text-align-left">Managing devices in an organization are becoming more complex as more and more devices are introduced. And it becomes essential to look for modern solutions that can effectively manage these modern devices, streamline workflows, and lessen the administrative burden. Automating device management is a key feature of any mobile device management (MDM) solution. Automating device management tasks provides organizations with multiple benefits, including:</p>



<ul>
<li><strong>Improved operational efficiency</strong></li>



<li><strong>Time-saving</strong></li>



<li><strong>Improved quality and consistency</strong></li>



<li><strong>Increased employee satisfaction</strong></li>



<li><strong>Increased customer satisfaction</strong></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2 class="wp-block-heading">Why Automation?</h2>



<p>Practically, you cannot automate everything in device management as there will be specific workflows or tasks that either cannot be automated or it could be that you would not like to automate them. The most crucial challenge, then, is how to differentiate between jobs that can be automated and those that are best left to MDM admins. To answer this, as an MDM admin, you need to filter out the following:</p>



<ul>
<li><strong>The repetitive tasks</strong></li>



<li><strong>Time-consuming</strong> <strong>tasks</strong></li>



<li><strong>Tasks with a high risk of human errors</strong></li>



<li><strong>Generally, more than one team is involved.</strong></li>



<li><strong>Rule-based tasks</strong></li>
</ul>



<p>Finding the ideal process to automate might be difficult because it must first satisfy a number of conditions. However, to ensure streamlined &amp; automated user-app-device management, you must select and automate the right task!</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2 class="wp-block-heading">Scope of this blog</h2>



<p class="has-text-align-center"><em>It is challenging to cover all use cases in this article because Intune can now manage SIX different types of device platforms, and several device types are inside each</em>. So I&#8217;ll go over a few <em>typical device-user-app management activities that are simple to execute, yield instant advantages, and are widely used. I have tried to scope them by type of tasks. Let&#8217;s get started, then!</em>(<strong><em>Apologies to the MEM community experts if I have missed mentioning your blogs</em>/article</strong>)</p>



<h2 class="wp-block-heading">Device Provisioning</h2>



<p>The Mobile Device Management lifecycle starts with device provisioning. If you are provisioning &amp; deploying corporate devices daily without Zero-Touch, then this would be the first task you should automate. Depending on the type of device/platform you are provisioning, the provisioning method and automation also differ. Intune currently support zero-touch provisioning for the following platforms:</p>



<ul>
<li>Windows 10/11- Autopilot</li>



<li>iOS, iPad OS, Apple TV OS &amp; macOS &#8211; Apple Device Enrollment Program</li>



<li>Android Enterprise &#8211; Samsung Knox Mobile Enrollment</li>



<li>Android Enterprise &#8211; Android Zero Touch Deployment</li>
</ul>



<h3 class="wp-block-heading">What is Zero-Touch provisioning?</h3>



<p>Zero-touch provisioning is a method of setting up devices that automatically configure the device using certain inbuilt/custom features. Zero-touch provisioning helps IT teams quickly deploy corporate devices in a large-scale environment, eliminating most of the manual labour involved with adding provisioning and managing them.</p>



<p>Zero-touch provisioning is also used to automate the system updating process. You can also use your own custom scripts to pre-configure the devices so that they can be enrolled and managed through your device management platforms.</p>



<h4 class="wp-block-heading">Platform &#8211; Windows </h4>



<p>Windows Autopilot is a cloud service provided by Microsoft that makes it easier for device management admins to provision Windows 10/11 devices on the go. With Windows Autopilot, administrators can avoid building custom images for each device and maintain them. With each new Microsoft update, admins must update the images and start the process repeatedly. With Windows Autopilot, administrators can instead automatically provision the devices with the necessary settings and configurations.</p>



<p>One of the most useful features is customizing the OOBE, which is the setup wizard, wherein, for example, you can restrict the user from being a local admin, enable self-deployment mode or even provision the machine with a corporate nomenclature. Administrators can remotely reset the devices and re-deploy them to another user using the Autopilot reset option. The device is ready for you to use right away. You need to connect to the internet, and it will be ready for you!</p>



<p>Bulk provisioning can be automated in a number of ways, including through custom connectors, PowerShell, Graph, Power Automate, PowerApps, and Logic Apps. If you look for these, you can easily locate the information on blogs written by community experts. I&#8217;ve provided links to a couple of them below to save you time:</p>



<ul>
<li><a href="https://call4cloud.nl/category/autopilot/" target="_blank" rel="noopener" title="">Autopilot &#8211; Call4Cloud</a></li>
</ul>



<ul>
<li><a href="https://oofhours.com/2020/07/13/automating-the-windows-autopilot-device-hash-import-and-profile-assignment-process/" target="_blank" rel="noopener" title="">Automating the Windows Autopilot device hash import and profile assignment process – Out of Office Hours (oofhours.com)</a></li>
</ul>



<ul>
<li><a href="https://andrewstaylor.com/2023/01/11/monitoring-intune-enrollment-limits/" target="_blank" rel="noopener" title="">Monitoring Intune Enrollment Limits &#8211; Andrew Taylor (andrewstaylor.com)</a></li>
</ul>



<ul start="2">
<li><a href="https://msendpointmgr.com/2018/07/23/automation-of-gathering-and-importing-windows-autopilot-information/#autopilotgraphapi" target="_blank" rel="noopener" title="">Automation of gathering and importing Windows Autopilot information &#8211; MSEndpointMgr</a></li>
</ul>



<ul start="3">
<li><a href="https://www.inthecloud247.com/windows-autopilot-lifecycle-automation-with-logic-apps/" target="_blank" rel="noopener" title="">Windows Autopilot lifecycle automation with Logic Apps | Peter Klapwijk &#8211; In The Cloud 24-7 (inthecloud247.com)</a></li>
</ul>



<ul start="4">
<li><a href="https://www.portaldotjay.com/2021/04/autopilot-prestager-power-automate-for.html?m=1" target="_blank" rel="noopener" title="">Autopilot Prestager – A Power Automate for staging Autopilot devices using an in-house inventory database. (portaldotjay.com)</a></li>
</ul>



<ul start="5">
<li><a href="https://eldar.cloud/2021/05/03/azure-logic-app-import-device-to-autopilot/" target="_blank" rel="noopener" title="">Azure Logic App &#8211; Import device to Autopilot &#8211; Eldar Borge</a></li>
</ul>



<ul start="6">
<li><a href="https://oliverkieselbach.com/2018/07/17/automation-of-gathering-and-importing-windows-autopilot-information/" target="_blank" rel="noopener" title="">Automation of gathering and importing Windows Autopilot information – Modern IT – Cloud – Workplace (oliverkieselbach.com)</a></li>
</ul>



<ul>
<li><a href="https://oceanleaf.ch/intune-automation-enlightenment/" target="_blank" rel="noopener" title="">Intune automation enlightenment &#8211; Azure Logic App + Graph API + Managed Identity (oceanleaf.ch)</a></li>
</ul>



<ul>
<li><a href="https://smbtothecloud.com/powershell-data-factory-logic-app-autopilot-hardware-hashes-sent-to-you-in-teams/" target="_blank" rel="noopener" title="">PowerShell + Data Factory + Logic App = Autopilot Hardware Hashes sent to you in Teams &#8211; SMBtotheCloud</a></li>
</ul>



<ul>
<li><a href="https://www.systanddeploy.com/2019/04/manage-windows-autopilot-with-powershell.html" target="_blank" rel="noopener" title="">Manage Windows Autopilot with PowerShell | Syst &amp; Deploy (systanddeploy.com)</a></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4 class="wp-block-heading">Platform &#8211; iOS, iPad OS, TV OS &amp; macOS</h4>



<p>Apple devices can be handed out to employees directly and used right out of the box with Apple Business Manager without requiring manual configuration. Additionally, thanks to flexible deployment models for all Apple platforms, as an IT admin, you can provide workers with the appropriate apps for the job more quickly than before.</p>



<p><strong>Apple Business Manager</strong> is a web-based portal for IT administrators to deploy iPhone, iPad, iPod touch, Apple TV, and Mac, all from one place. Working seamlessly with a mobile device management solution, Apple Business Manager makes it easy to automate device deployment, purchase apps, distribute<br>content, and create Managed Apple IDs for employees. With Apple Business Manager, every iPhone, iPad, and Mac can be set up and configured automatically—eliminating the need for IT teams to handle each device individually. IT can also purchase and distribute apps for employees and enable employees to use Apple services with a Managed Apple ID.</p>



<p>Some the blogs to refer:</p>



<ul>
<li><a href="https://uem4all.com/2022/09/07/apple-automated-device-enrollment-profile-duplicator/" target="_blank" rel="noopener" title="">Apple Automated Device Enrollment profile duplicator – Mobility, Management, &amp; Security (uem4all.com)</a></li>
</ul>



<ul>
<li><a href="https://intuneirl.com/2022/07/company-owned-ios-device-automated-device-enrollment-part-i/" target="_blank" rel="noopener" title="">Company-Owned iOS Device -Automated Device Enrollment – Part I &#8211; Intune &#8211; In Real Life (intuneirl.com)</a></li>
</ul>



<ul>
<li><a href="https://mattsoseman.wordpress.com/2020/04/12/intune-how-to-mdm-enroll-ios-ipados-devices/" target="_blank" rel="noopener" title="">Intune: How to MDM enroll iOS/iPadOS devices | Matt Soseman&#8217;s Blog (wordpress.com)</a></li>
</ul>



<ul>
<li><a href="https://katystech.blog/mem/intune-part-3-ipads" target="_blank" rel="noopener" title="">Intune: Managing iOS devices | Katy&#8217;s Tech Blog (katystech.blog)</a></li>
</ul>



<ul>
<li><a href="https://vmlabblog.com/2021/05/ios-user-enrollment-using-intune/" target="_blank" rel="noopener" title="">iOS User enrollment using Intune &#8211; VMLabBlog.com</a></li>
</ul>



<ul>
<li><a href="https://intuneirl.com/2022/10/macos-management-with-intune-the-prologue/" target="_blank" rel="noopener" title="">macOS Management with Intune – The Prologue &#8211; (intuneirl.com)</a></li>
</ul>



<ul>
<li><a href="https://hmaslowski.com/home/f/apples-automated-device-enrollment-to-microsoft-endpoint-manager" target="_blank" rel="noopener" title="">Apple iOS/iPadOS Automated Device Enrollment (ADE) to MEM/Intune (hmaslowski.com)</a></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4 class="wp-block-heading">Platform &#8211; Android Enterprise</h4>



<p>Similar to how you use Apple DEP to enrol large numbers of Apple devices, you can use <strong>Android Zero-Touch Enrollment</strong> for bulk provisioning Android devices. Android Zero-Touch, commonly called <strong>Android ZTE</strong>, allows IT admin to bulk deploy corporate-owned devices without configuring each one individually. When the devices are switched on, and the initial network connectivity is successfully established, they are silently added to the MDM. </p>



<p><strong>Samsung Knox Mobile Enrollment,</strong> commonly referred to as <strong>Samsung KME,</strong> helps you set up Intune for enrolling supported Samsung Enterprise Android devices. Using Intune with Samsung KME, you can enrol many company-owned Android devices when end users turn on their devices for the first time and connect to a Wi-Fi or cellular network. Also, devices can be enrolled using Bluetooth or NFC when using the Knox Deployment App. </p>



<p>Here are a few noteworthy blogs to refer:</p>



<ul>
<li><a href="https://timmyit.com/2022/02/14/intune-knox-platform-for-enterprise-oemconfig-claim-your-2-year-free-license-for-premium-features/" target="_blank" rel="noopener" title="">Intune – Knox Platform for Enterprise (OEMConfig) claim your 2 year free license for Premium features – TimmyIT.com</a></li>
</ul>



<ul>
<li><a href="https://www.inthecloud247.com/setup-samsung-knox-mobile-enrollment-to-enroll-android-devices-in-microsoft-intune/" target="_blank" rel="noopener" title="">Setup Samsung Knox Mobile Enrollment to enroll Android devices in Microsoft Intune | Peter Klapwijk &#8211; In The Cloud 24-7 (inthecloud247.com)</a></li>
</ul>



<ul>
<li><a href="https://hmaslowski.com/all-my-posts/f/samsungs-kme-with-android-enterprise-enrollment-to-memintune?blogcategory=Android" target="_blank" rel="noopener" title="">Samsung&#8217;s KME with Android Enterprise enrollment to MEM/Intune (hmaslowski.com)</a></li>
</ul>



<ul>
<li><a href="https://www.petervanderwoude.nl/post/using-samsung-knox-mobile-enrollment-with-microsoft-intune/" target="_blank" rel="noopener" title="">Using Samsung Knox Mobile Enrollment with Microsoft Intune – All about Microsoft Endpoint Manager (petervanderwoude.nl)</a></li>
</ul>



<ul>
<li><a href="https://robinhobo.com/how-to-setup-samsung-knox-mobile-enrollment-with-microsoft-intune/" target="_blank" rel="noopener" title="">How to setup Samsung Knox Mobile Enrollment with Microsoft Intune – robinhobo.com</a></li>
</ul>



<ul>
<li><a href="https://intuneirl.com/2022/07/bring-android-to-work-manage-android-devices-with-intune/" target="_blank" rel="noopener" title="">Bring Android To Work – Manage Android Devices With Intune &#8211; Intune &#8211; In Real Life (intuneirl.com)</a></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2 class="wp-block-heading">App Management</h2>



<p>Deploying apps is also one of the essential device management operations in a managed environment. A manual process of assigning and configuring the apps for each new device is not very effective. You may easily set a dynamic policy with the apps to be installed using an MDM like Intune or can try to automate the app deployment.</p>



<p>Again, depending upon the platform to be managed, the app type and distribution mechanism differ. For example, if it&#8217;s a public store app, then for Windows, you have the new Winget-based Microsoft Store; for Android, it&#8217;s Enterprise Google Play Store; similarly, for Apple devices, you have VPP  apps. And the list of some of the blogs to get started with automating app deployment:</p>



<ul>
<li><a href="https://andrewstaylor.com/2022/11/15/packaging-and-publishing-intune-apps-using-winget-and-azure-devops-ci-cd-pipeline-packaging-as-code/" target="_blank" rel="noopener" title="">Packaging and publishing Intune apps using Winget and Azure Devops CI/CD Pipeline &#8211; packaging as code &#8211; Andrew Taylor (andrewstaylor.com)</a></li>
</ul>



<ul>
<li><a href="https://scloud.work/en/win32-app-deployment-automated/?amp=1" target="_blank" rel="noopener" title="">win32 App Deployment automated | scloud</a></li>
</ul>



<ul>
<li><a href="https://techlab.blog/updated-how-to-package-and-test-apps-using-rimo3/" target="_blank" rel="noopener" title="">Updated: How To Package And Test Apps Using Rimo3 &#8211; techlab.blog</a></li>
</ul>



<ul>
<li><a href="https://www.modernendpoint.com/managed/" target="_blank" rel="noopener" title="">Managed Modern Endpoint Blog |</a></li>
</ul>



<ul>
<li><a href="https://smsagent.blog/category/intune/" target="_blank" rel="noopener" title="">Intune (smsagent.blog)</a></li>
</ul>



<ul>
<li><a href="https://andrewstaylor.com/2022/11/08/quick-and-easy-application-inventory-with-intune/" target="_blank" rel="noopener" title="">Quick and easy application Inventory with Intune &#8211; Andrew Taylor (andrewstaylor.com)</a></li>
</ul>



<ul>
<li><a href="https://oliverkieselbach.com/tag/intune/" target="_blank" rel="noopener" title="">Intune – Modern IT – Cloud – Workplace (oliverkieselbach.com)</a></li>
</ul>



<ul>
<li><a href="https://jannikreinhard.com/2022/12/11/deploy-windows-store-apps-via-intune/" target="_blank" rel="noopener" title="">Deploy Windows Store Apps via Intune – Modern Device Management (jannikreinhard.com)</a></li>
</ul>



<ul>
<li><a href="https://365bythijs.be/2020/01/06/automating-3th-party-application-deployment-in-intune-with-patchmypc/" target="_blank" rel="noopener" title="">Automating 3rd Party application deployment in Intune with PatchMyPc – 365 by Thijs</a></li>
</ul>



<ul>
<li><a href="https://andrewstaylor.com/2022/12/13/microsoft-store-intune-integration-graph-commands/" target="_blank" rel="noopener" title="">Microsoft Store Intune Integration &#8211; Graph Commands &#8211; Andrew Taylor (andrewstaylor.com)</a></li>
</ul>



<ul>
<li><a href="https://call4cloud.nl/2020/11/the-powershell-win32-app-express/" target="_blank" rel="noopener" title="">Automate Win32App Deployments to Intune with PowerShell (call4cloud.nl)</a></li>
</ul>



<ul></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2 class="wp-block-heading">Automate your day-to-day Intune tasks</h2>



<p><strong>BAU</strong>, or <strong>Business As Usual</strong>, happens after the devices have been enrolled/registered and distributed to the end users. The end user&#8217;s devices must be supported, and you must carry out specific tasks, deploy apps, and create and publish reports. Most tasks are time-consuming and repetitive, making them the ideal candidates for automation. Again, I wouldn&#8217;t want to reinvent the wheel because plenty of blogs and articles can help you comprehend and begin automating these processes. I&#8217;ve included a couple of blogs below for your quick reference:</p>



<ul>
<li><a href="https://www.petervanderwoude.nl/post/introducing-a-simple-remote-device-manager-app-for-microsoft-intune/">Introducing a simple remote device manager app for Microsoft Intune – All about Microsoft Endpoint Manager (petervanderwoude.nl)</a></li>
</ul>



<ul>
<li><a href="https://www.olastrom.com/2022/remote-actions-in-endpoint-manager">olastrom.com &#8211; Remote actions in Endpoint Manager</a></li>
</ul>



<ul>
<li><a href="https://www.burgerhout.org/reset-your-device-with-a-simple-app/">Reset your device with a simple app (burgerhout.org)</a></li>
</ul>



<ul>
<li><a href="https://www.modernendpoint.com/managed/MMS-Intune-Management-PowerApp-Demo-Part-1-Creating-the-PowerAutomate-flows/">MMS Intune Management PowerApp Demo Part 1: Creating the PowerAutomate flows | (modernendpoint.com)</a></li>
</ul>



<ul>
<li><a href="https://uem4all.com/tag/power-apps/">Power Apps – Mobility, Management, &amp; Security (uem4all.com)</a></li>
</ul>



<ul>
<li><a href="https://365bythijs.be/2020/03/09/deploy-power-app-to-a-managed-home-screen-through-mem/">Deploy Power App to a Managed Home Screen through MEM – 365 by Thijs</a></li>
</ul>



<ul>
<li><a href="https://gregramsey.net/2020/04/07/how-to-use-logic-apps-to-query-intune-for-device-information/">How To: Use Logic Apps to Query Intune for Device Information | Greg&#8217;s Systems Management Blog (gregramsey.net)</a></li>



<li><a href="https://tech.nicolonsky.ch/">nicolonsky tech</a></li>
</ul>



<ul>
<li><a href="https://intuneirl.com/2022/11/automate-daily-reports-for-windows-update-compliance-using-logic-apps/" target="_blank" rel="noopener" title="">Automate Daily Reports for Windows Update Compliance using Logic Apps &#8211; Intune &#8211; In Real Life (intuneirl.com)</a></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2 class="wp-block-heading">Device Offboarding</h2>



<p>Similar to onboarding, offboarding devices or deleting corporate data from corporate or personal devices can also be automated. You can remove the device(s) from enrollment or delete the user from the portal. This eliminates the policies that were related to the user or device. Here are a few blogs to refer to:</p>



<ul>
<li><a href="https://www.inthecloud247.com/windows-autopilot-lifecycle-automation-with-logic-apps/" target="_blank" rel="noopener" title="">Windows Autopilot lifecycle automation with Logic Apps | Peter Klapwijk &#8211; In The Cloud 24-7 (inthecloud247.com)</a></li>
</ul>



<ul>
<li><a href="https://uem4all.com/tag/bulk-delete/" target="_blank" rel="noopener" title="">bulk delete – Mobility, Management, &amp; Security (uem4all.com)</a></li>
</ul>



<ul>
<li><a href="https://oliverkieselbach.com/2020/01/21/cleanup-windows-autopilot-registrations/" target="_blank" rel="noopener" title="">Cleanup Windows Autopilot registrations – Modern IT – Cloud – Workplace (oliverkieselbach.com)</a></li>
</ul>



<ul>
<li><a href="https://euc365.com/post/remove-autopilot-displayname/" target="_blank" rel="noopener" title="">Bulk Remove Autopilot DisplayName Property (euc365.com)</a></li>
</ul>



<ul>
<li><a href="https://uem4all.com/2020/04/04/mem-powerautomate-graph/" target="_blank" rel="noopener" title="">Microsoft Endpoint Manager Intune, Power Automate, and Microsoft Graph – send user notifications after device enrollment – Mobility, Management, &amp; Security (uem4all.com)</a></li>
</ul>



<ul>
<li><a href="https://byteben.com/bb/using-powershell-with-intune-graph-to-query-devices/" target="_blank" rel="noopener" title="">Using PowerShell with Microsoft Graph to query Intune Devices (byteben.com)</a></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Stay Updated</h2>



<p>There is so much happening in the device management world that it is impossible to catch up on everything.  But there are two <strong>super newsletters</strong> that you should subscribe to be always updated:</p>



<ul>
<li><a href="https://www.danielengberg.com/category/newsletter/">Newsletter Archives &#8211; Daniel Engberg</a></li>
</ul>



<ul>
<li><a href="https://andrewstaylor.com/category/newsletter">https://andrewstaylor.com/category/newsletter</a></li>
</ul>



<h2 class="wp-block-heading">Conclusion</h2>



<p>The purpose of this blog article was to provide you with a quick overview of how automating your everyday Intune operations may help you tremendously and to prompt you to implement automation so that, as an IT administrator, you can save time and improve your client device management environment.</p>



<p>Automating device management becomes necessary as the number of devices you manage increases daily. This is necessary since it will help you in a number of ways, including decreasing repetitive work and increasing productivity.</p>



<p>That&#8217;s all for this week. Thank you for reading, and please share your feedback. </p>
<!--kg-card-end: html-->