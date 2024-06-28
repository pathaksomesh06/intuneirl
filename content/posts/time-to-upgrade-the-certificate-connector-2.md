---
title: "Time To Upgrade the Certificate Connector!"
date: 2022-09-02T21:50:00"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>If your certificate connector is still on a version earlier than&nbsp;<strong>6.2101.13.0</strong>&nbsp;then it is the right time to upgrade it because, from today onwards, they are deprecated and will not be able to issue certificates to your devices.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-a52e60d.png/:/rs=w:1280" alt="" width="640" height="220"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>If you have a certificate connector configured, then you might be leveraging its functionality for issuing &amp; revoking:</p>



<ul><li>Private and public key pair (PKCS) certificates, or</li><li>PKCS imported certificates, or</li><li>Simple Certificate Enrollment Protocol (SCEP)</li></ul>



<p>In July&#8217;21, Microsoft published the lifecycle policy for certificate connectors, and as per Microsoft:</p>



<ol><li>Each new connector release will be supported six months after its release date. During this period, automatic updates can install a newer connector version (depending upon your network configuration).</li><li>If an out-of-support connector fails, it must update to the latest supported version.</li><li>If automatic updates of the connector are blocked, the manual update of the connector will be required within six months before support for the installed version ends.</li><li>Connectors out of support will continue functioning for up to 18 months after their release date. After 18 months, a connector&#8217;s functionality might fail due to service level improvements, updates, or addressing common security vulnerabilities that might surface in the future.</li></ol>



<p>This helps replace three separate certificate connectors for SCEP and PKCS and imported PKCS with a <strong>Unified Certificate Connector</strong>. Previously, from Intune portal, we had the option to download three different connectors viz SCEP, PKCS and PFX imported. </p>



<p>You just need to download and configure the new unified certificate connector, enabling multiple capabilities from a single connector. </p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Check the version installed in your environment:</strong></h4>



<p>You can verify the version of the connector from the server on which it is installed.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20132213.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="285"/></figure>



<p>This screenshot shows that the connector version is deprecated, which is why the MEM portal status shows an error.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-2849621.png/:/rs=w:1280" alt="" width="640" height="258"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Prerequisites for the Certificate Connector for Microsoft Intune:</strong></h4>



<p>Before installing and configuring the Certificate Connector for Microsoft Intune, let&#8217;s review the prerequisites and infrastructure requirements. These prerequisites can vary depending on the features you want to configure. However, the general requirements are as below:</p>



<ul><li>Windows Server 2012 R2 or later. </li><li>.NET v4.7.2</li><li>TLS 1.2</li><li>The server should have access to &#8220;<strong>autoupdate.msappproxy.net&#8221; </strong>and port 443 should be open to keeping the connector auto-updated</li><li>Disable <strong>Enhanced Security Configuration</strong> in IE</li><li>Details for proxy configuration of the NDES server </li><li>NDES service account details </li></ul>



<p>Please refer to the <a rel="noreferrer noopener" href="https://docs.microsoft.com/en-us/mem/intune/protect/certificate-connector-prerequisites" target="_blank">Prerequisites for using the Certificate Connector for Microsoft Intune &#8211; Azure | Microsoft Docs</a> for detailed permissions and requirements for the connector. </p>



<p><strong>Let&#8217;s get the ball rolling then.</strong>&nbsp;</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Uninstall the Deprecated Connector:</strong></h4>



<ul><li>Log in to the NDES server and uninstall the old connector.&nbsp;</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-7e71705.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="350"/></figure>



<ul><li>Launch an elevated command prompt and restart the IIS service</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/072315_1516.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="343" height="169"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Download the Latest Connector:</strong></h4>



<ul><li>&nbsp;Sign in to the&nbsp;<a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank">Microsoft Endpoint Manager admin center</a>.</li><li>Navigate to&nbsp;<strong>Tenant administration</strong>&nbsp;&gt;&nbsp;<strong>Connectors and tokens</strong>&nbsp;&gt;&nbsp;<strong>Certificate<br>&nbsp;connectors</strong>&nbsp;&gt;&nbsp;<strong>Add.</strong></li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-2ede18a.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="227"/></figure>



<ul><li>Select the <a rel="noreferrer noopener" href="https://go.microsoft.com/fwlink/?linkid=2168535" target="_blank"><u><em><strong>certificate connector</strong></em></u></a> link to download the connector installer. Save/Copy the file on the server where you will install the connector.</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/1-40c6907.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="640" height="251"/></figure>



<ul><li>Run the installer (<strong>IntuneCertificateConnector.exe</strong>) with NDES service account.</li><li>Review and agree to the license terms and conditions, and then select&nbsp;<strong>Install</strong>&nbsp;to<br>&nbsp;continue.</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20151913-9ec5a58.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="329" height="161"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20152027.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="240" height="148"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20152231.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="298" height="157"/></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Configure Intune Certificate Connector:</strong></h4>



<p>To configure the certificate connector, use the <strong>Certificate Connector for Microsoft Intune</strong> wizard. The configuration will start automatically if you choose to <em><strong>Configure Now</strong></em> in the previous step, or you can manually launch it by opening an elevated command prompt and running the below command:</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20153221.jpg/:/rs=w:1280" alt="" width="488" height="229"/></figure>



<ul><li>The <strong>Certificate Connector for Microsoft Intune</strong> wizard will start with the <em><strong>Welcome </strong></em>page. Click <strong>Next</strong> to start the configuration wizard:</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20153448-706469f.jpg/:/rs=w:1280" alt="" width="515" height="367"/></figure>



<ul><li>On <em><strong>Features</strong></em>, select the checkbox for each connector feature you want to install on this server, and then select <strong>Next</strong>. </li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20153853.jpg/:/rs=w:1280" alt="" width="575" height="404"/></figure>



<ul><li> On the <em>Proxy</em> page, add details for your proxy server if you require a proxy for internet access.</li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20154236.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="518" height="267"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20154604.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="506" height="74"/></figure>



<ul><li>Next, on the <em><strong>Prerequisites</strong></em><strong> </strong>page, the wizard runs several checks on the server before the configuration can begin. Review and resolve any errors or warnings received before you continue.</li><li>The next screen is the <em><strong>Azure AD Sign-In</strong></em><strong> page</strong>; use the default <strong>Public Commercial Cloud for Environment., and then select Sign In. The user account must be a Global Admin or an Intune Admin with an Intune license assigned, and the user must be a </strong><strong>synchronized account from your On-Prem Active Directory.</strong></li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20155118.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="634" height="441"/></figure>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20155140.jpg/:/rs=w:1280" alt="" width="636" height="445"/></figure>



<ul><li>On the <em><strong>Configure</strong></em><strong> </strong>page, the <strong>wizard applies the configuration to the connector for Intune</strong>. If successful, the utility continues to the <em><strong>Finish</strong></em><strong> </strong>page, where you select <strong>Exit</strong> to complete configuration of the connector. </li></ul>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Sk%C3%A4rmbild%202022-09-02%20160137.jpg/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="636" height="444"/></figure>



<ul><li>After the configuration completes successfully and the wizard closes, the Certificate the connector for Microsoft Intune is ready for use.</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Verify the New Connector:</strong></h4>



<p>The quick &amp; best way to verify is by checking the SCEP URL. All is set if it is giving the expected HTTP 403 error!&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-28b0250.png/:/cr=t:0%25,l:0%25,w:100%25,h:100%25/rs=w:1280" alt="" width="960" height="365"/></figure>



<p>The connector status should also reflect as <strong>active and healthy </strong>in the <strong>MEM Portal, </strong>indicating a successful upgrade. </p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://img1.wsimg.com/isteam/ip/efa64053-58a1-4924-93af-4078ceb0648a/Untitled-6eb59b6.png/:/rs=w:1280" alt="" width="960" height="400"/></figure>



<p>Once you verify that all the services are running fine, delete the old connector from Intune portal.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>That&#8217;s all for today. Hope you will find this post useful!</p>
<!--kg-card-end: html-->