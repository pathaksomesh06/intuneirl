---
title: "Integrate MTD With Intune"
date: 2022-08-01T20:45:00"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<p>Integrating a Mobile Threat Defense solution with Intune will help you protect corporate data and mobile devices against any network attack or malware attacks and can alert MDM admins if a device is compromised or tampered with. In this blog, we will discuss setting up an MTD connector and will use <strong>MVISION </strong>as the MTD product.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>McAfee MVISION Mobile detects malicious activity and can take actions locally on the device. When MVISION Mobile is integrated with an Intune, protection actions are performed by the MDM, providing a potent protection tool. When MVISION  Mobile is integrated with MAM, the risk posture is identified as mobile threats are detected when the app is launched. </p>



<p>We can configure MVISION Mobile Console with Microsoft Intune in three different modes: </p>



<ol><li>MDM only</li><li>MAM only</li><li>MDM and MAM</li></ol>



<h4><strong>Pre-requisites:</strong></h4>



<p>There are typically no prerequisites for integrating MVISION with MEM, as all the communications between MEM & MTD will be over the internet. However, specific requirements exist for the minimum supported iOS & Android devices.</p>



<ul><li>Android Version  –  v6.0 or higher </li><li>iOS Version – v10.0 or higher</li><li>MVISION Mobile App for Android  –  v4.12 or higher</li><li>For MDM with MAM – v4.17 or higher</li><li>Permission/Access – Initially GA & then minimum Intune Administrator or equivalent</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Configure the MTD Connector</strong></h4>



<p>Perform the below steps to set up the MTD Connection:</p>



<p>1. Log in to the <a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank">Microsoft Endpoint Manager</a> console.</p>



<p>2. Navigate to <strong>Tenant Administration</strong> > <strong>Connectors and tokens</strong> > <strong>Mobile Threat Defense > Add</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-28%20234531-0001.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="278"/></figure>



<p>3. Click <strong>McAfee MVISION Mobile</strong> as the MTD Connector.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-28%20234912.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="304"/></figure>



<p>4. Click <strong>Create.</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-28%20235145.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="337"/></figure>



<p>5. The connector is added in Intune but is not acting as a few more configurations are still required.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-28%20235232.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="253"/></figure>



<p>6. Open a new tab and log in to the <a href="https://auth.ui.mcafee.com/?redirect_uri=https%3A%2F%2Fmvision.mcafee.com" rel="noreferrer noopener" target="_blank">MVISION Mobile Console</a>. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20000153.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="340"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20000352.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="341"/></figure>



<p>7. Navigate to <strong>Manage > Integrations </strong>> <strong>MDM</strong>. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20000725.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="311"/></figure>



<p>8. Click Add <strong>MDM </strong>and select <strong>Microsoft Endpoint Manager.</strong></p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20000725.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="311"/></figure>



<p>9. The next step is to add the ‘<strong>MVISION Console</strong>,’ ‘MVISION Mobile iOS,’ and the ‘MVISION Mobile Android applications to the Azure Active Directory to enable this integration. When you click <strong>Add to Azure Active Directory</strong> button, Microsoft sign-in window opens, wherein you have to authenticate yourself.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20000746.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="284"/></figure>



<p>Repeat the step for all three options. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20001410.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="283"/></figure>



<p>10. Click the <strong>Next </strong>button, type a unique name in the MDM Name field for the environment in the Add MDM tab, field for the environment in the Add MDM and then click <strong>Next</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20155541.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="365" height="196"/></figure>



<p>11. The integration window will close, and Intune is added as MDM in MVISION. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20000609.png/:/rs=w:1280" alt="" width="640" height="285"/></figure>



<p>12. Back to the MEM portal, navigate <strong>Tenant Administration</strong> > <strong>Connectors and tokens > Mobile  Threat Defense. </strong>You will see<strong> </strong> McAfee MVISION Mobile showing as an active connector. Click on the connector and <strong>move the </strong>Connect Android and iOS Devices sliders to <strong>On</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-30%20172832.png/:/rs=w:1280" alt="" width="640" height="290"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>With these steps, MVISION is integrated with Intune as a Mobile Threat Defense solution, but still, there are a couple more settings you have to configure before it starts protecting your devices. </p>



<h4><strong>Add the MVISION app to Intune</strong></h4>



<p>To deploy the MVISION Mobile application on your corporate-owned devices, it is recommended that you push the app directly from the App Store for the iOS version and the Google Play Store for the Android version and deploy it to your devices with install intent as “<strong>Required</strong>.”</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-31%20232737.png/:/rs=w:1280" alt="" width="640" height="279"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-31%20232947.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="346"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Configure Auto-Activation of the MVISION App</strong></h4>



<p>Since you are deploying the app through Intune and the connector is also integrated, it helps with the auto-activation of the app on the end user’s devices. The steps for activation of the app on iOS and Android Enterprise devices are provided below. </p>



<p>1. Navigate to <strong>Apps > App configuration policies and Click on + Add</strong>. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-31%20233955.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="241"/></figure>



<p>2. From the dropdown, select “<strong>Managed Devices</strong>.”</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-31%20234057.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="218"/></figure>



<p>3. Provide the name and description and select <strong>iOS </strong>as the platform. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-31%20234234.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="265"/></figure>



<p>4. Search & select the MVISION app and press <strong>Next</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-31%20234426.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="270"/></figure>



<p>5. Choose Use Configuration designer and set up the configuration keys as shown below:</p>



<ul><li><strong>Tenant ID</strong>: This will be the tenant id of your MVISION subscription.</li><li><strong>Default Channel</strong>: The value for the default channel will also be available in the MVISION tenant.</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20110744.png/:/rs=w:1280" alt="" width="640" height="370"/></figure>



<p>6. In <strong>Assignments, </strong>select the groups you want to apply to this configuration. </p>



<p>7. Repeat the same steps for creating an App Configuration Policy for managed Android devices as shown below:</p>



<p>  –  Select the app from the app library</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20152640.png/:/rs=w:1280" alt="" width="640" height="311"/></figure>



<p>   –  Give permissions on external & internal storage</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20152848.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="301"/></figure>



<p>  –  Configure the app configurations for auto-activation</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20153017.png/:/rs=w:1280" alt="" width="640" height="300"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20153114.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="329"/></figure>



<p> –  Assign the policy to device group. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Configure Device Compliance Policy</strong></h4>



<p>With all these configurations done, it’s time to configure compliance policies to evaluate devices based on configured threat levels. </p>



<p>Microsoft Endpoint  Manager takes actions based on the Device Threat Level configured in the compliance policies. The device threat levels that can be configured are <strong>Secured</strong>, <strong>Low</strong>, <strong>Medium</strong>, and <strong>High</strong>. </p>



<p>As an Intune admin, you must configure the minimally acceptable device threat level in the <strong>compliance policy</strong>. These levels correspond to the McAfee MVISION Mobile severity levels as shown below:</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20161118-0001.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="355" height="140"/></figure>



<p>(As per McAfee, the minimum configured threat level should be Medium)</p>



<p>The MVISION app continuously collects file system, network stack, device, and application data on a real-time basis from the device. It sends the forensic data to the MVISION Mobile cloud to evaluate the device’s risk based on the threat level configured. You can configure conditional access policies to protect corporate data based on the device health attestation. For non-managed devices, you can configure app protection policies to perform selective wipes based on detected threats or block the device from accessing the corporate resources until it is marked as compliant. </p>



<p><strong>Create the compliance policy – Android Enterprise:</strong></p>



<p>1. Sign in to the <a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank">Intune </a>Portal.</p>



<p>2. Select <strong>Devices</strong> > <strong>Compliance policies</strong> > <strong>Policies</strong> > <strong>Create Policy.</strong></p>



<p>3. Select <strong>Android Enterprise – Fully Managed, dedicated, corporate-owned work profile</strong> from the dropdown menu and click <strong>Create</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20163429.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="293"/></figure>



<p>4. On the <strong>Basics</strong> tab, specify a <strong>Name </strong>and<strong> description </strong>for the policy.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20164112.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="339"/></figure>



<p>5. In the <strong>Compliance settings</strong> tab, expand the dropdown for <strong>Device Health </strong>and configure settings for <strong>Require the device to be at or under the Device Threat Level </strong>as shown below:</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20164353.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="630" height="387"/></figure>



<p>6. Select “<strong>Check basic integrity & certified devices</strong>” for SafetyNet device attestation under Google Play protect.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20165602.png/:/rs=w:1280" alt="" width="640" height="299"/></figure>



<p>7. Provide value for the Minimum OS version allowed by your organization. </p>



<p><strong>PS –  When a device doesn’t meet the minimum OS version requirement, it’s reported as non-compliant. </strong></p>



<p>8. Configure options under <strong>System Security. </strong></p>



<p>9. Set Intune app runtime integrity as “<strong>Required</strong>” and click <strong>Next</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20165648.png/:/rs=w:1280" alt="" width="640" height="355"/></figure>



<p>10. In the <strong>Actions for noncompliance</strong> tab, you can configure multiple actions to apply automatically to devices that don’t meet this compliance policy. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20165852.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="589" height="248"/></figure>



<p>11. Click Next to choose scope tags and assign the policy to your groups.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Create the compliance policy – iOS Devices:</strong></p>



<p>1. Sign in to the <a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank">Intune </a>Portal.</p>



<p>2. Select <strong>Devices</strong> > <strong>Compliance policies</strong> > <strong>Policies</strong> > <strong>Create Policy.</strong></p>



<p>3. Select <strong>iOS devices </strong>from the dropdown menu and click <strong>Create</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20170258.png/:/rs=w:1280" alt="" width="640" height="312"/></figure>



<p>4. On the <strong>Basics</strong> tab, specify a <strong>Name </strong>and<strong> description </strong>for the policy.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20170331.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="350"/></figure>



<p>5. In the <strong>Compliance settings</strong> tab, configure the below settings:</p>



<ul><li>Managed email – Configure if you want to configure the iOS native mail client.</li><li>Jailbroken devices – Block </li><li>Device Threat Level – Medium or High</li><li>Device Properties – Configure Min/Max iOS/iPadOS</li><li>System Security – Configure <strong>device passcode </strong>policies</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20171215.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="320"/></figure>



<p>6. In the <strong>Actions for noncompliance</strong> tab, you can configure multiple actions to apply automatically to devices that don’t meet this compliance policy. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20165852.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="589" height="248"/></figure>



<p>7. Click Next to choose scope tags and assign the policy to your groups.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Configure Groups in MVISION to sync policies</strong><br> </h4>



<p>As the last part of this configuration, you have to add groups in the MVISION console to sync the policies.</p>



<p>1. log in to <a href="https://auth.ui.mcafee.com/" rel="noreferrer noopener" target="_blank">MVISION Mobile Console</a>.</p>



<p>2. Navigate to the <strong>Manage </strong>page and select the <strong>Integrations </strong>tab. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20000609.png/:/rs=w:1280" alt="" width="640" height="285"/></figure>



<p>3. Click on Edit and <strong>Add MDM Step 3 Setup </strong>window opens. Click <strong>Next</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20001410.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="283"/></figure>



<p>4. In the group filter, you can specify either the full name or group initials of the groups to which the MVISION App Configuration Policies were assigned and click <strong>Next</strong>. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20172545.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="354" height="183"/></figure>



<p>5. Click the green plus icon to synchronize from the MDM Groups shown on the left.<br>   Once you select a group will appear in the Selected MVISION Mobile Console Groups on<br>   the right-hand side.  </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-07-29%20001618.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="278"/></figure>



<p>6. Click <strong>Next</strong>.</p>



<p>7. Specify the MDM alerts if you want to be notified when there are MDM sync errors and click <strong>SYNC Now</strong>.</p>



<p>And…your MTD connector is Up & Running to protect your devices and corporate data in real-time. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>End User Experience</strong></h4>



<p><strong>iOS Devices(supervised devices)</strong></p>



<p> – Activation Tasks are in sequential order (from left to right)</p>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20223235.png/:/rs=w:1280" alt="" width="596" height="222"/></figure></div>

<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20222358.png/:/rs=w:1280" alt="" width="471" height="238"/></figure></div>

<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20222518.png/:/rs=w:1280" alt="" width="589" height="247"/></figure></div>

<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20222635.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="578" height="259"/></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p><strong>Android Enterprise Devices (Corporate-Owned)</strong></p>


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-08-01%20225314.png/:/rs=w:1280" alt="" width="640" height="281"/></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/download-0002.jfif/:/rs=w:1280" alt=""/></figure></div>
<!--kg-card-end: html-->
