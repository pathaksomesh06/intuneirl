---
title: "Say Hi! to the New Microsoft Store in Intune"
date: 2022-12-01T18:41:44"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>The brand-new Microsoft App Store is now generally available. Microsoft Store apps can now be searched for, browsed through, configured, and deployed through Intune. The new Microsoft Store app type is implemented via the Windows Package Manager. This app category provides a wider variety of apps, including Win32 and UWP apps.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>How does the &#8220;New&#8221; store differ from the &#8220;Legacy&#8221; store?</h2>



<p>If your tenant has the most recent updates, you may have noticed that two Windows Store apps are now available for you to pick from. They are:</p>



<ul>
<li>Microsoft Store App (New)</li>



<li>Microsoft Store App (Legacy)</li>
</ul>



<p>The new Microsoft store is based on the new Windows Package Manager or winget, which allows you to easily find the latest versions of the apps and push them to your end user&#8217;s Windows-managed devices. The new store also allows you to add EXEs and MSI packages from winget to APPX and MSIX.</p>



<p>In the new store, the Windows Package Manager framework backend has been connected to the Intune apps service so that, as an Intune Admin, you can easily search for any app in the store.</p>



<p>All the apps and their packages are maintained centrally by the ISV publisher of the app package. And as an Intune admin, you have complete control over what your users can install.</p>



<p>In the &#8220;legacy&#8221; store, there was no option to search for the apps.</p>



<p>Let me show you the experience in the Intune admin center:</p>



<ul>
<li>After logging into Intune admin center, navigate to the All apps blade, click on &#8220;Add App&#8221;</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-1.png?resize=750%2C222&#038;ssl=1" alt="" class="wp-image-932" width="750" height="222" srcset="https://irlimages.blob.core.windows.net/2022-12/image-1.png?resize=1024%2C302&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-1.png?resize=300%2C89&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-1.png?resize=768%2C227&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-1.png?resize=1536%2C454&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-12/image-1.png?w=1825&amp;ssl=1 1825w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<ul>
<li>You will notice the new store. Click &#8220;Select&#8221; to proceed with adding an app.</li>
</ul>



<ul>
<li>On the next screen, search for the app you want to install. For this demo, I will search for the Paint 3D app.</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-3.png?resize=750%2C162&#038;ssl=1" alt="" class="wp-image-935" width="750" height="162" srcset="https://irlimages.blob.core.windows.net/2022-12/image-3.png?resize=1024%2C221&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-3.png?resize=300%2C65&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-3.png?resize=768%2C166&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-3.png?resize=1536%2C331&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-12/image-3.png?w=1571&amp;ssl=1 1571w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p>You will observe the difference compared to the store&#8217;s previous options because it enables you to find apps using built-in search. </p>



<p>And all the app&#8217;s details, like the name, description, publisher, package ID, and privacy URL, are automatically pre-populated, so you don&#8217;t need to cut and paste anything.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-4.png?resize=750%2C646&#038;ssl=1" alt="" class="wp-image-936" width="750" height="646" srcset="https://irlimages.blob.core.windows.net/2022-12/image-4.png?resize=1024%2C881&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-4.png?resize=300%2C258&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-4.png?resize=768%2C661&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-4.png?w=1086&amp;ssl=1 1086w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="224" src="https://irlimages.blob.core.windows.net/2022-12/image-6.png?resize=750%2C224&#038;ssl=1" alt="" class="wp-image-939" srcset="https://irlimages.blob.core.windows.net/2022-12/image-6.png?resize=1024%2C306&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-6.png?resize=300%2C90&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-6.png?resize=768%2C229&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-6.png?w=1129&amp;ssl=1 1129w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<pre class="wp-block-code"><code>📢Win32 apps that are in the Microsoft Store are currently in preview. Not all Win32 apps will be available or searchable. The Win32 apps in preview will be identifiable with <strong>Win32</strong> and a banner.</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Winget</h2>



<p>The Windows Package Manager (also known as winget) is a free and open-source package manager designed by Microsoft for Windows 10 and 11. It consists of a command-line utility and a set of services for installing applications. Independent software vendors can use it as a distribution channel for their software packages.</p>



<p>I&#8217;ll run a help command, and you&#8217;ll see all the different app operations it can perform, like installing, searching, upgrading, and more.</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-7.png?resize=750%2C409&#038;ssl=1" alt="" class="wp-image-941" width="750" height="409" srcset="https://irlimages.blob.core.windows.net/2022-12/image-7.png?resize=1024%2C559&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-7.png?resize=300%2C164&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-7.png?resize=768%2C419&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-7.png?w=1094&amp;ssl=1 1094w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>I&#8217;ll use the command -s msstore to limit the results to only those found in the store as I quickly search for Apache. It discovers two packages, one of which has the XP prefix, suggesting that they are Win32 software.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-8.png?resize=603%2C101&#038;ssl=1" alt="" class="wp-image-942" width="603" height="101" srcset="https://irlimages.blob.core.windows.net/2022-12/image-8.png?w=804&amp;ssl=1 804w, https://irlimages.blob.core.windows.net/2022-12/image-8.png?resize=300%2C50&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-8.png?resize=768%2C129&amp;ssl=1 768w" sizes="(max-width: 603px) 100vw, 603px" data-recalc-dims="1" /></figure></div>


<p>If you run a show command using its ID to view information, you&#8217;ll see the app as an EXE file type. So it&#8217;s easy to find app packages and perform standard app operations against them.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-9.png?resize=750%2C398&#038;ssl=1" alt="" class="wp-image-943" width="750" height="398" srcset="https://irlimages.blob.core.windows.net/2022-12/image-9.png?resize=1024%2C544&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-9.png?resize=300%2C159&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-9.png?resize=768%2C408&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-9.png?w=1075&amp;ssl=1 1075w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Universal Windows Platform (UWP) App</h2>



<p>While searching for the apps in the new store, you will notice that the apps are listed as UWP apps. Let&#8217;s discuss this also.</p>



<p>UWP is Microsoft&#8217;s extension of the Windows Runtime platform that leverages the C++, C#, VB.NET, and XAML coding languages. The main idea for UWP is:</p>



<ul>
<li>Universal API toolkit.</li>



<li>Responsive design and scaling in apps.</li>



<li>Universal controls, styles, input, and interactions.</li>



<li>Cloud, A.I., and cognitive services.</li>



<li>Single Store for distribution.</li>



<li>One Software Development Kit (SDK).</li>
</ul>



<p>The goal for UWP is to let developers share code between apps and utilize a broad range of APIs; it does not necessarily mean that a UWP app is supposed to &#8220;run everywhere,&#8221; such as on phones, PCs, Xbox, HoloLens, and IoT devices.</p>



<p>UWP was introduced in Windows 10, which provides a common app platform available on every device that runs Windows 10. The UWP provides a guaranteed core API across devices. This means that developers can create a single app package that can be installed onto various devices. And, with that single app package, the Windows Store provides a unified distribution channel to reach all the device types your app can run on. Apps that target the UWP can call not only the WinRT APIs that are common to all devices but also APIs (including Win32 and .NET APIs) that are specific to the class of device that the app is running on.</p>



<p>UWP is Microsoft&#8217;s initiative to have everything in one place &#8211; Windows Store.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Independent Software Vendor</h2>



<p>ISV was the second term we noticed when exploring the new Windows Store application. </p>



<p>A software product made and sold by an independent software vendor (ISV) runs on one or more hardware or operating system (OS) platforms. ISVs often work with a hardware, software, or cloud platform vendor to offer software. When it comes to hardware, a software developer creates software compatible with the hardware platforms of one or more specific vendors and the OSes those platforms support. By including database technology from Microsoft, for example, an ISV may also incorporate software from a software platform provider into its offering.</p>



<p>For instance, any company that offers its software solution on a marketplace like Salesforce AppExchange is an ISV.</p>



<p>Computer hardware manufacturers and operating systems will test Independent software suppliers seeking to sell their software solutions on their marketplace and cloud computing platforms. They will, however, only permit—or ISV certifies—independent software suppliers who can provide the most useful and superior software solutions in their markets.</p>



<p>For example, Microsoft, a company that develops computer hardware (Xbox), operating systems (Windows), and a cloud platform (Azure),&nbsp;offers silver and gold ISV certifications to independent software vendors&nbsp;whose products can pass their rigorous quality tests and prove they can offer the top software solutions to Microsoft’s customers on each of their marketplaces.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Deploying Apps Using The New Windows Store </h2>



<p>Coming back to the new store! By now, you have an idea of the difference between the new &amp; legacy app store and UWP &amp; ISV. So, let&#8217;s publish the app we added in the first app.</p>



<p>For this case, I want to publish the Paint 3D app as &#8220;Available&#8221; in Company Portal so that the users can install it on their own. </p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-5.png?resize=750%2C261&#038;ssl=1" alt="" class="wp-image-938" width="750" height="261" srcset="https://irlimages.blob.core.windows.net/2022-12/image-5.png?resize=1024%2C356&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-5.png?resize=300%2C104&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-5.png?resize=768%2C267&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-5.png?resize=1536%2C534&amp;ssl=1 1536w, https://irlimages.blob.core.windows.net/2022-12/image-5.png?w=1567&amp;ssl=1 1567w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure></div>


<p>So, this app package remains where it is and isn&#8217;t getting imported into your Intune storage. When this app is later installed on a device, Intune instructs the device to install directly from its defined Microsoft Store location.</p>



<p>The user needs to open the company portal on his/her Windows 10/11 device and look for the apps available to install.</p>



<h2>Wrapping-Up</h2>



<p>This new approach has a number of benefits, especially the in-app curation flow, because there is currently a substantial amount of ISV support.</p>



<p>The connection between Intune and the new Microsoft Store is intended to pave the way for helping enterprises with this transition because, as we all know, Microsoft has stated that they will be closing the Microsoft Store for Business very soon!</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p class="has-small-font-size">References:</p>



<p class="has-small-font-size"><a href="https://learn.microsoft.com/en-gb/mem/intune/apps/store-apps-microsoft?WT.mc_id=EM-MVP-5004955">Add Microsoft Store apps to Microsoft Intune | Microsoft Learn</a></p>
<!--kg-card-end: html-->