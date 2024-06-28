---
title: "iOS App Distribution – From Private Apps to Enterprise Apps"
date: 2022-12-27T00:58:39"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<h2>Overview</h2>



<p>Apple provides a wide range of application distribution options, each of which serves a particular purpose. This guide will dive into the different distribution methods and when to use each, depending on your distribution needs.</p>



<p>Whether you&#8217;re an Intune administrator, creating apps for the App Store, or focusing on creating customized private apps for business or enterprise, this post will walk you through all your options for distributing iOS apps.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>It all begins with an idea!</h2>



<p>Everything begins with a problem you want to solve. Once you figure it out and know what to build, you create an app, and it makes it into the hands of your end users, most often through the App Store.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-20 (1).png?resize=512%2C118&#038;ssl=1" alt="" class="wp-image-974" width="512" height="118" srcset="https://irlimages.blob.core.windows.net/2022-12/image-20 (1).png?resize=1024%2C235&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-20 (1).png?resize=300%2C69&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-20 (1).png?resize=768%2C176&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-20 (1).png?w=1216&amp;ssl=1 1216w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>


<p>It appears simple, and it is for many apps on the store. However, there are several ways to distribute an app. And it all depends on your customer. It all comes down to determining the best way to reach your target audience. Your customers could be members of the general public, businesses, or enterprise users. There are various ways to distribute your app depending on its intended audience.</p>



<p>There are four distribution methods that we&#8217;re going to discuss in this post:</p>



<ul>
<li>Ad hoc</li>



<li>App Store</li>



<li>In-house</li>



<li>Custom apps</li>
</ul>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-19 (1).png?resize=512%2C146&#038;ssl=1" alt="" class="wp-image-973" width="512" height="146" srcset="https://irlimages.blob.core.windows.net/2022-12/image-19 (1).png?resize=1024%2C292&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-19 (1).png?resize=300%2C86&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-19 (1).png?resize=768%2C219&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-19 (1).png?w=1426&amp;ssl=1 1426w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Different types of distribution methods</em></figcaption></figure></div>


<p>I&#8217;ll explain all the approaches by using the distribution path of an app that started as a prototype, went through the App Store, was then adapted for a business, and was distributed privately in a few different ways.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Personal Team</h2>



<p>As the first step, you will download&nbsp;Xcode and will log in with your Apple ID to build your prototype. But how would you get this prototype to run on your devices? Sign in to Xcode using your Apple ID and take advantage of the free Personal Team account that comes with it. This isn&#8217;t a real distribution method because, with this approach, you can only deploy it to a limited number of devices, and the app will expire after a few days. Here&#8217;s what Xcode looks like when logged in with a personal team. </p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-21 (1).png?resize=647%2C505&#038;ssl=1" alt="" class="wp-image-975" width="647" height="505" srcset="https://irlimages.blob.core.windows.net/2022-12/image-21 (1).png?w=862&amp;ssl=1 862w, https://irlimages.blob.core.windows.net/2022-12/image-21 (1).png?resize=300%2C234&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-21 (1).png?resize=768%2C600&amp;ssl=1 768w" sizes="(max-width: 647px) 100vw, 647px" data-recalc-dims="1" /></figure></div>


<p>You create and run your app. Xcode installs it on your device, but for it to launch, you must trust your device&#8217;s developer certificate.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full"><img decoding="async" loading="lazy" width="550" height="227" src="https://irlimages.blob.core.windows.net/2022-12/image-23 (1).png?resize=550%2C227&#038;ssl=1" alt="" class="wp-image-977" srcset="https://irlimages.blob.core.windows.net/2022-12/image-23 (1).png?w=550&amp;ssl=1 550w, https://irlimages.blob.core.windows.net/2022-12/image-23 (1).png?resize=300%2C124&amp;ssl=1 300w" sizes="(max-width: 550px) 100vw, 550px" data-recalc-dims="1" /></figure></div>


<p>You need to trust the developer certificate by going into settings, general, profiles, and device management.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-24.png?resize=512%2C300&#038;ssl=1" alt="" class="wp-image-978" width="512" height="300" srcset="https://irlimages.blob.core.windows.net/2022-12/image-24.png?resize=1024%2C600&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-24.png?resize=300%2C176&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-24.png?resize=768%2C450&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-24.png?w=1453&amp;ssl=1 1453w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>The user</em> has to manually trust the developer&#8217;s<em> certificate</em></figcaption></figure></div>


<h3>Personal team app distribution in a nutshell:</h3>



<ul>
<li>Intended for students, teachers and getting started</li>



<li>Apps will be deployed to devices you own</li>



<li>Intended for a few apps and a few devices</li>



<li>Certain capabilities are not available with free accounts (ex: CloudKit)</li>



<li>Apps cannot be distributed on the App Store</li>
</ul>



<p>Features like CloudKit, Siri, or APNS aren&#8217;t available, and there&#8217;s no way you can publish your &#8220;grocery&#8221; app to the store with this program so let&#8217;s move to the next distribution stage.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Ad-hoc Distribution</h2>



<p>Until now, you&#8217;ve been mostly just testing the app in the simulator or on your device or your friend&#8217;s devices and would also have got the feedback. So the next step is to sign-up for the &#8220;Apple Developer Program&#8221;. If you don&#8217;t already have an account, you need to sign-up for one &#8211; either as a company or an individual and once you&#8217;re signed up, you&#8217;re ready to start distributing the app.</p>



<p>When you leverage ad hoc distribution, a limited number of users can install your app directly from their devices for testing. The process requires that you register their devices from the developer&#8217;s website. <strong><em>However, you can register 100 devices per product family per year for development and testing</em></strong>.<br>To install an app on a device for a user, you need to know their device&#8217;s identifier, which you can find either from the Finder sidebar or from Xcode. Once you have the identifier, you can register the device with the Apple Developer website. After registering the device, you can create a build and install it for the user. There are several different ways to do this, depending on the device and the app.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-25.png?resize=512%2C294&#038;ssl=1" alt="" class="wp-image-980" width="512" height="294" srcset="https://irlimages.blob.core.windows.net/2022-12/image-25.png?resize=1024%2C588&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-25.png?resize=300%2C172&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-25.png?resize=768%2C441&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-25.png?w=1073&amp;ssl=1 1073w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Registering a Device</em></figcaption></figure></div>


<p>You can connect your device to your Mac or use Apple&#8217;s configurator to install the app. You can also host the app and have it installed automatically over the air.</p>



<p>This is a manual way of achieving a limited distribution to a small group. This program is designed to let you deploy to registered devices for testing. It&#8217;s not a long-term or scalable distribution solution, and the provisioning profiles used to sign these apps expire yearly, so eventually, the apps will stop working or need to be re-signed.</p>



<h3>Add-hoc app distribution in a nutshell:</h3>



<ul>
<li>Meant for testing apps on registered devices</li>



<li>Short-term distribution solution</li>



<li>Apps expire and will eventually stop working</li>



<li>Device limits reset once per year</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>App Store</h2>



<p class="has-text-align-left has-medium-font-size">By now, your user base is growing, and you realize that ad-hoc distribution is not the right fit for you. So you decide to distribute your all-star grocery app to the Apple app store.</p>



<p class="has-medium-font-size">The App Store offers beta testing features that are easier to use and allow more users to participate. TestFlight makes it easy for developers and users to test apps, and installation and updates are simple. Beta builds last for three months; for a user, installing an app is a familiar and simple process. TestFlight also offers beta testing for users who are not developers through app review.</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-26 (1).png?resize=420%2C268&#038;ssl=1" alt="" class="wp-image-982" width="420" height="268" srcset="https://irlimages.blob.core.windows.net/2022-12/image-26 (1).png?w=839&amp;ssl=1 839w, https://irlimages.blob.core.windows.net/2022-12/image-26 (1).png?resize=300%2C191&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-26 (1).png?resize=768%2C490&amp;ssl=1 768w" sizes="(max-width: 420px) 100vw, 420px" data-recalc-dims="1" /></figure></div>


<p class="has-medium-font-size">Before submitting an app to the App Store, ensure it meets review guidelines and is stable and ready for a broader audience. However, if you&#8217;re only releasing the app to your App Store Connect team members, you don&#8217;t need to review it. And TestFlight, which is only available to Apple Developer Program members, will help you test the app before submission.</p>



<p>Once you&#8217;re satisfied with the stability of your build, the next step is submitting it to the App Store.</p>



<p>The users for your app can be both the general public and enterprises; anyone can sign up for the Apple Developer Program to distribute to the App Store. Apps are available to the general public based on the markets you choose to support, making them public stores or enterprise apps.</p>



<h3>Public app store distribution in a nut-shell:</h3>



<ul>
<li>Know and follow the App Store Review Guidelines</li>



<li>Keep the app current</li>



<li>Make sure the app is appropriate for the general public</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>In-House Distribution</h2>



<p>So now your grocery app is on the Apple app store, a highly rated app. Things are progressing very fast, and you need to customize your app as a business app intended to be used privately and internally by an organization. There are two ways to distribute apps internally -&gt; In-House and Custom Apps. Let&#8217;s first discuss in-house distribution.</p>



<p>In-house distribution lets you control the entire distribution process and host the app yourself. </p>



<p>It requires membership in the Apple Developer Enterprise Program. Still, there are strict eligibility requirements to get into that program, and it is meant for those cases that can&#8217;t be solved by custom app distribution. Distribution is handled completely outside of the App Store by the organizations and is usually through MDM. There are a few important aspects of in-house distribution that you should be aware of:</p>



<ol>
<li>Apps deployed through in-house distribution can only be accessed by your employees. </li>



<li>Apps need to be signed with a distribution certificate owned by the organization, which needs to be protected.</li>



<li>Distribution certificates expire every three years, and the provisioning profiles expire annually.</li>



<li>There&#8217;s no TestFlight access for enterprise accounts.</li>
</ol>



<h3>In-House app distribution in a nutshell:</h3>



<ul>
<li>Users must be employees</li>



<li>Distribution certificates should be protected</li>



<li>The certificate lifecycle needs to be managed</li>



<li>DIY Beta Testing and Hosting</li>



<li>Apps require periodic access to the internet</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Custom Apps</h2>



<p>Distributing business apps as custom app is a new way forward. Custom apps are designed for private distribution to organizations that manage apps on behalf of their employees. These can be apps you develop in-house for distribution to your employees, or they can be apps you develop and make available directly to specific businesses/customers that you designate (e.g. your grocery app).</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-27.png?resize=406%2C220&#038;ssl=1" alt="" class="wp-image-983" width="406" height="220" srcset="https://irlimages.blob.core.windows.net/2022-12/image-27.png?w=811&amp;ssl=1 811w, https://irlimages.blob.core.windows.net/2022-12/image-27.png?resize=300%2C162&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-27.png?resize=768%2C416&amp;ssl=1 768w" sizes="(max-width: 406px) 100vw, 406px" data-recalc-dims="1" /></figure></div>


<p>Custom apps are purchased using Apple Business Manager and deployed through MDM, e.g. Intune. The benefit of using custom apps is that you make a standard version of your apps available on the public App Store and, at the same time, can also design a tailored version of your app for specific customers that will be only available to them.</p>



<p>Custom Apps apps don&#8217;t expire, so you don&#8217;t need to worry about distribution certificates being revoked or expiring. Additionally, Custom Apps makes it easier to work with third-party developers, as you can get and distribute an app without having access to the source code, and there&#8217;s no need to re-sign binaries. Additionally, Custom Apps&#8217; auto-update infrastructure makes sure your app is always up-to-date.</p>



<h3>Here are the high-level steps for creating custom apps:</h3>



<div class="is-layout-constrained wp-block-group"><div class="wp-block-group__inner-container">
<p>Step 1: Account setup</p>



<ul>
<li>Accept both the Apple Developer Program License Agreement and the Paid Application agreement.</li>



<li>Provide tax and banking in App Store Connect</li>



<li>Leverage roles in defining proper access for all team members</li>
</ul>



<p>Step 2: New App ID and App Record (<a href="https://developer.apple.com/account" target="_blank" rel="noopener" title="">developer.apple.com/account</a>)</p>



<p>Step 3: Upload a valid build</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-28.png?resize=498%2C289&#038;ssl=1" alt="" class="wp-image-984" width="498" height="289" srcset="https://irlimages.blob.core.windows.net/2022-12/image-28.png?w=996&amp;ssl=1 996w, https://irlimages.blob.core.windows.net/2022-12/image-28.png?resize=300%2C174&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-28.png?resize=768%2C446&amp;ssl=1 768w" sizes="(max-width: 498px) 100vw, 498px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Upload a build and attach it to the working version in App Store Connect</em></figcaption></figure></div></div></div>



<p>Step 4: Beta test with TestFlight</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-29.png?resize=491%2C278&#038;ssl=1" alt="" class="wp-image-985" width="491" height="278" srcset="https://irlimages.blob.core.windows.net/2022-12/image-29.png?w=982&amp;ssl=1 982w, https://irlimages.blob.core.windows.net/2022-12/image-29.png?resize=300%2C170&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-29.png?resize=768%2C434&amp;ssl=1 768w" sizes="(max-width: 491px) 100vw, 491px" data-recalc-dims="1" /></figure></div>


<p>Step 5: List the app for sale as a Custom App</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-32.png?resize=500%2C245&#038;ssl=1" alt="" class="wp-image-988" width="500" height="245" srcset="https://irlimages.blob.core.windows.net/2022-12/image-32.png?w=999&amp;ssl=1 999w, https://irlimages.blob.core.windows.net/2022-12/image-32.png?resize=300%2C147&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-32.png?resize=768%2C376&amp;ssl=1 768w" sizes="(max-width: 500px) 100vw, 500px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Mark it as private</em></figcaption></figure></div>

<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-35.png?resize=512%2C149&#038;ssl=1" alt="" class="wp-image-991" width="512" height="149" srcset="https://irlimages.blob.core.windows.net/2022-12/image-35.png?resize=1024%2C297&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-35.png?resize=300%2C87&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-35.png?resize=768%2C223&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-35.png?w=1155&amp;ssl=1 1155w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Provide the customer&#8217;s DEP ID and organization name</em></figcaption></figure></div>


<p>Step 6: Submit for review</p>


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-39.png?resize=498%2C100&#038;ssl=1" alt="" class="wp-image-995" width="498" height="100" srcset="https://irlimages.blob.core.windows.net/2022-12/image-39.png?w=996&amp;ssl=1 996w, https://irlimages.blob.core.windows.net/2022-12/image-39.png?resize=300%2C60&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-39.png?resize=768%2C154&amp;ssl=1 768w" sizes="(max-width: 498px) 100vw, 498px" data-recalc-dims="1" /></figure></div>


<pre class="wp-block-code"><code><strong><em>Note, once an app is submitted for review as either a custom app or a public app, you can't go back and change the audience from public to private for vice versa later on</em></strong>.</code></pre>



<p>Once the app is approved and available, your customer can purchase and distribute the app through Apple Business Manager.</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-41.png?resize=512%2C304&#038;ssl=1" alt="" class="wp-image-997" width="512" height="304" srcset="https://irlimages.blob.core.windows.net/2022-12/image-41.png?resize=1024%2C607&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-41.png?resize=300%2C178&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-41.png?resize=768%2C455&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-41.png?w=1495&amp;ssl=1 1495w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure></div>


<h3>Custome apps distribution in a nutshell:</h3>



<ul>
<li>The customer is required to have Apple Business Manager</li>



<li>Apps have to support the countries they will be distributed in</li>



<li>Redemption codes will not be made publicly available</li>



<li>Reviewers need to access the full functionality of the app</li>



<li>Once submitted, apps can not be moved between public and private availability</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Summary</h2>



<p>We&#8217;ve covered the four distribution methods that you have to choose from:</p>



<ul>
<li>Ad Hoc lets you distribute to a limited private audience for testing.</li>



<li>The App Store lets you distribute apps to the general public.</li>



<li>In-House and Custom App distribution let you distribute apps privately.</li>
</ul>



<p>The easiest way to decide which is right for you is to think about the audience for your app. A brief summary is shown below:</p>


<div class="wp-block-image">
<figure class="aligncenter size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-12/image-42.png?resize=750%2C345&#038;ssl=1" alt="" class="wp-image-998" width="750" height="345" srcset="https://irlimages.blob.core.windows.net/2022-12/image-42.png?resize=1024%2C471&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-12/image-42.png?resize=300%2C138&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-12/image-42.png?resize=768%2C353&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-12/image-42.png?w=1458&amp;ssl=1 1458w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /><figcaption class="wp-element-caption"><em>Distribution Scenarios</em></figcaption></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h2>Wrapping it up!</h2>



<p>I hope this article provided you with more in-depth knowledge of iOS app distribution strategies and explained the advantages and disadvantages of each. Depending on your app&#8217;s needs, one distribution method may be more optimal. If you enjoyed reading my post, please spread the word about them and follow my page.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p class="has-small-font-size">Ref: https://developer.apple.com/</p>
<!--kg-card-end: html-->