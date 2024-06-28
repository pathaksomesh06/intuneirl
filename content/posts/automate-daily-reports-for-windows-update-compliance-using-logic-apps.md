---
title: "Automate Daily Reports for Windows Update Compliance using Logic Apps"
date: 2022-11-11T02:02:15"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>In this blog post, I will show how to create and schedule a custom report for monitoring Windows Update using a combination of KQL and Azure Automation. The Windows Update Compliance is offered through the Azure portal and helps you monitor security, quality, and feature updates for Windows 10 or 11. It also gives you a report of the device and updates issues related to compliance that need attention.</p>



<p>The Update Compliance dashboard has lots of data; in the workspace, you will find numerous tables holding different data types. You can use KQL queries to get the data you are interested in! Let&#8217;s get started then with creating some KQL queries and automating them as email or even getting posted in the Teams channel. We will cover the following:</p>



<ul><li>Creating a blank logic app and workflow.</li><li>Adding a Recurrence trigger that specifies the schedule to run the workflow.</li><li>Add a custom query to the workflow.</li><li>Add an action that sends an email</li><li>Add a webhook for Teams</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Logic Apps</h2>



<p>Azure Logic Apps, from Microsoft Azure, is <strong>a cloud-based Platform-as-a-Service (PaaS) </strong>used to automate tasks, workflows, etc. It helps create and design automated workflows that integrate services, systems, and applications.</p>



<p>Below are the steps to create a logic app:</p>



<ol><li>Sign in to the <a href="https://portal.azure.com/">Azure portal</a> with your Azure account.</li></ol>



<ol start="2"><li>In the Azure search box, enter <code>logic apps</code>, and select <strong>Logic apps</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-21.png?resize=662%2C227&#038;ssl=1" alt="" class="wp-image-741" width="662" height="227" srcset="https://irlimages.blob.core.windows.net/2022-11/image-21.png?w=883&amp;ssl=1 883w, https://irlimages.blob.core.windows.net/2022-11/image-21.png?resize=300%2C103&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-21.png?resize=768%2C264&amp;ssl=1 768w" sizes="(max-width: 662px) 100vw, 662px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>On the <strong>Logic apps</strong> page, select <strong>Add</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-22.png?resize=483%2C134&#038;ssl=1" alt="" class="wp-image-742" width="483" height="134" srcset="https://irlimages.blob.core.windows.net/2022-11/image-22.png?w=644&amp;ssl=1 644w, https://irlimages.blob.core.windows.net/2022-11/image-22.png?resize=300%2C83&amp;ssl=1 300w" sizes="(max-width: 483px) 100vw, 483px" data-recalc-dims="1" /></figure></div>


<ol start="5"><li>On the <strong>Create Logic App</strong> pane, on the <strong>Basics</strong> tab, provide the following basic information about your logic app:</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/safe-ge9bd20bec_1920-1-1.jpg?resize=750%2C652&#038;ssl=1" alt="" class="wp-image-744" width="750" height="652" srcset="https://irlimages.blob.core.windows.net/2022-11/safe-ge9bd20bec_1920-1-1.jpg?resize=1024%2C890&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/safe-ge9bd20bec_1920-1-1.jpg?resize=300%2C261&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/safe-ge9bd20bec_1920-1-1.jpg?resize=768%2C667&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/safe-ge9bd20bec_1920-1-1.jpg?w=1229&amp;ssl=1 1229w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>When you&#8217;re ready, select <strong>Review + Create</strong>. On the next page, validate and click <strong>Create</strong>.</li></ol>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Design The Workflow</h2>



<p>As the next step, we will add the Recurrence trigger, which runs the workflow based on a specified schedule. Every workflow must start with a trigger, which fires when a specific event happens or when new data meets a specific condition. </p>



<ol><li>On the workflow designer, under the search box, select <strong>Built-in</strong>.</li></ol>



<ol start="2"><li>In the search box, enter recurrence, and select the Recurrence trigger.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-24.png?resize=617%2C325&#038;ssl=1" alt="" class="wp-image-745" width="617" height="325" srcset="https://irlimages.blob.core.windows.net/2022-11/image-24.png?w=822&amp;ssl=1 822w, https://irlimages.blob.core.windows.net/2022-11/image-24.png?resize=300%2C158&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-24.png?resize=768%2C405&amp;ssl=1 768w" sizes="(max-width: 617px) 100vw, 617px" data-recalc-dims="1" /></figure></div>


<ol start="3"><li>On the <strong>Recurrence</strong> shape, select the <strong>ellipses</strong> (<strong>&#8230;</strong>) button, and then select <strong>Rename</strong>. Rename the trigger with this description: <code>Daily Report</code>.</li></ol>



<ol start="4"><li>Inside the trigger, change these properties as required</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-25.png?resize=607%2C175&#038;ssl=1" alt="" class="wp-image-746" width="607" height="175" srcset="https://irlimages.blob.core.windows.net/2022-11/image-25.png?w=809&amp;ssl=1 809w, https://irlimages.blob.core.windows.net/2022-11/image-25.png?resize=300%2C86&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-25.png?resize=768%2C221&amp;ssl=1 768w" sizes="(max-width: 607px) 100vw, 607px" data-recalc-dims="1" /></figure></div>


<ol start="5"><li>In the workflow designer, under the Recurrence trigger, click S<strong>Add an Action</strong></li></ol>



<ol start="6"><li>In the search box, enter <strong>Run query and visualize results</strong>.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-26.png?resize=257%2C119&#038;ssl=1" alt="" class="wp-image-747" width="257" height="119" srcset="https://irlimages.blob.core.windows.net/2022-11/image-26.png?w=343&amp;ssl=1 343w, https://irlimages.blob.core.windows.net/2022-11/image-26.png?resize=300%2C139&amp;ssl=1 300w" sizes="(max-width: 257px) 100vw, 257px" data-recalc-dims="1" /></figure></div>


<ol start="7"><li>Sign in with user credentials or select Service Principal and fill in the Parameters for creating a connection.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-27.png?resize=593%2C247&#038;ssl=1" alt="" class="wp-image-748" width="593" height="247" srcset="https://irlimages.blob.core.windows.net/2022-11/image-27.png?w=790&amp;ssl=1 790w, https://irlimages.blob.core.windows.net/2022-11/image-27.png?resize=300%2C125&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-27.png?resize=768%2C320&amp;ssl=1 768w" sizes="(max-width: 593px) 100vw, 593px" data-recalc-dims="1" /></figure></div>


<ol start="8"><li>In the <strong>Query</strong> field, enter the Log Analytics query you want to report on. For example, I want to schedule a report on the compliance of the latest 2 security patches, so I have used the below query:</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-28.png?resize=560%2C404&#038;ssl=1" alt="" class="wp-image-749" width="560" height="404" srcset="https://irlimages.blob.core.windows.net/2022-11/image-28.png?w=746&amp;ssl=1 746w, https://irlimages.blob.core.windows.net/2022-11/image-28.png?resize=300%2C217&amp;ssl=1 300w" sizes="(max-width: 560px) 100vw, 560px" data-recalc-dims="1" /></figure></div>


<ol start="9"><li>Keep <strong>HTML Table </strong>as chart type, as this will give you the same output as shown in Log Analytics table </li></ol>



<ol start="10"><li>Add an action that sends you an email when the query is executed.</li></ol>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-29.png?resize=593%2C506&#038;ssl=1" alt="" class="wp-image-750" width="593" height="506" srcset="https://irlimages.blob.core.windows.net/2022-11/image-29.png?w=790&amp;ssl=1 790w, https://irlimages.blob.core.windows.net/2022-11/image-29.png?resize=300%2C256&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-29.png?resize=768%2C655&amp;ssl=1 768w" sizes="(max-width: 593px) 100vw, 593px" data-recalc-dims="1" /></figure></div>


<p>You can customize the mail body, CC, To &amp; From attributes to fit your requirement.</p>



<ol start="11"><li>If you also want this report sent to your Teams channel, add the WebHook URL for your Teams.</li></ol>



<p>As the last step, save your Logic App and click <strong>Run</strong> to test it.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-30.png?resize=437%2C419&#038;ssl=1" alt="" class="wp-image-751" width="437" height="419" srcset="https://irlimages.blob.core.windows.net/2022-11/image-30.png?w=583&amp;ssl=1 583w, https://irlimages.blob.core.windows.net/2022-11/image-30.png?resize=300%2C288&amp;ssl=1 300w" sizes="(max-width: 437px) 100vw, 437px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Verify The Report</h2>



<p>Open your email client app, and you should see this email with the report attached in your inbox.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-31.png?resize=478%2C361&#038;ssl=1" alt="" class="wp-image-752" width="478" height="361" srcset="https://irlimages.blob.core.windows.net/2022-11/image-31.png?w=637&amp;ssl=1 637w, https://irlimages.blob.core.windows.net/2022-11/image-31.png?resize=300%2C227&amp;ssl=1 300w" sizes="(max-width: 478px) 100vw, 478px" data-recalc-dims="1" /></figure></div>


<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-11/image-33.png?resize=750%2C324&#038;ssl=1" alt="" class="wp-image-755" width="750" height="324" srcset="https://irlimages.blob.core.windows.net/2022-11/image-33.png?resize=1024%2C442&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-11/image-33.png?resize=300%2C129&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-11/image-33.png?resize=768%2C331&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-11/image-33.png?resize=1536%2C663&amp;ssl=1 1536w, https://i0.wp.com/intuneirl.com/wp-content/uploads/2022/11/image-33.png?w=1820&amp;ssl=1 1820w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Conclusion</h2>



<p>Pretty neat &amp; simple 😊. With this article, we saw how easily the queries in Windows Compliance could be automated/scheduled. Rest, it&#8217;s all your imagination and scripting power to extend it as per your business requirement.</p>



<p>Signing off for the day. Keep learning &amp; keep sharing. </p>



<p>Cheers 🍻</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<div class="is-layout-flow wp-block-group has-small-font-size"><div class="wp-block-group__inner-container">
<p>References:</p>



<div class="is-layout-flow wp-block-group"><div class="wp-block-group__inner-container">
<p><a href="https://learn.microsoft.com/en-us/azure/logic-apps/?WT.mc_id=EM-MVP-5004955">https://learn.microsoft.com/en-us/azure/logic-apps/?WT.mc_id=EM-MVP-5004955</a></p>



<p><a href="https://learn.microsoft.com/en-us/windows/deployment/update/update-compliance-using?WT.mc_id=EM-MVP-5004955">Using Update Compliance &#8211; Windows Deployment | Microsoft Learn</a></p>
</div></div>
</div></div>
<!--kg-card-end: html-->