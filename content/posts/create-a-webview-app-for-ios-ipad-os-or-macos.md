---
title: "Create a Webview App For iOS, iPad OS or macOS"
date: 2022-10-04T00:00:17"
draft: false
tags: []
---

<!--kg-card-begin: html-->
<p>The major motive for exploring this was to have a website as an app and then publish it so that users can download and install it on their mobile devices. </p>



<p>Yes, I know what you might be thinking, and you are correct; why do I need to create an app when we can use Intune to achieve it? But sometimes requirements are that weird 😁. And as I said, the requirements&#8230;so these users are external and cannot have any M365 license (not even a standalone Intune license), and they should directly go to a secure location to download and install the apps.  </p>



<p>We have websites with a perfect mobile view, but it is expected to act as an application that helps the users view only the particular website instead of opening a browser and browsing it. This kind of application acts and works like a browser, but users should be able to install it as an app on their mobile devices. Sounds weird again&#8230;and I said..the requirements!🤦‍♂️🤷‍♂️ But, this was something new, and I was excited to go the developer way. Why wait, then? Let&#8217;s get started 💻</p>



<p>In this post, I will walk you through creating a web view application for the iOS family using a swift programming language.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>Pre-requisites </h4>



<ul><li>MacBook</li><li>Xcode</li><li>Access to Apple Developer Program</li><li>Access to app icon and other details</li></ul>



<p>Let’s get started.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>XCode</h4>



<p>For this minimal iOS app, I will use the Xcode IDE by Apple. Xcode is Apple&#8217;s integrated development environment for macOS and is used to develop software for macOS, iOS, iPadOS, watchOS, and tvOS.&nbsp;Xcode&nbsp;provides a unified user interface design, coding, testing, and debugging workflow. The Xcode IDE combined with the Swift programming language makes developing apps easy and fun. To test or run applications on an iPhone, iPad, Apple TV, or Apple Watch, all you need is a free Apple ID.</p>



<p>The best thing is it has a built-in default simulator that helps you to simulate the app you are developing, and you do not any third-party app for testing your app. By using that simulator, you can make a simulation of your application for almost all iOS devices depending upon the minimum required OS that you configure in the app settings.</p>



<p>Download Xcode from&nbsp;<a rel="noreferrer noopener" href="https://apps.apple.com/us/app/xcode/id497799835?mt=12" target="_blank"><strong>Appstore</strong></a>. </p>



<p>📢📢 <strong style="font-style: italic;">Xcode is around 13Gigs and will take time to download and install on your Mac.&nbsp;</strong></p>



<p>Minimum requirements for Xcode:&nbsp;<a rel="noreferrer noopener" href="https://developer.apple.com/support/xcode/" target="_blank">https://developer.apple.com/support/xcode/</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>Create the app</h4>



<p>On your Macbook,&nbsp;<strong>open Xcode</strong>&nbsp;and click on <strong>Create a new Xcode project</strong>.&nbsp;</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.56.56-1.png?resize=512%2C249&#038;ssl=1" alt="" class="wp-image-444" width="512" height="249" srcset="https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.56.56-1.png?resize=1024%2C498&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.56.56-1.png?resize=300%2C146&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.56.56-1.png?resize=768%2C374&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.56.56-1.png?w=1510&amp;ssl=1 1510w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure>



<p>On the next screen, under Application, select App and click next. In this case, you can use multiplatform as we create a webview app that should run on all iOS devices. </p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.58.28-2.png?resize=512%2C329&#038;ssl=1" alt="" class="wp-image-447" width="512" height="329" srcset="https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.58.28-2.png?resize=1024%2C657&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.58.28-2.png?resize=300%2C193&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.58.28-2.png?resize=768%2C493&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-11.58.28-2.png?w=1170&amp;ssl=1 1170w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure>



<p>Now, provide a&nbsp;<strong>Product Name</strong>&nbsp;and&nbsp;<strong>Organization Identifier,</strong>&nbsp;which will be used to define a&nbsp;Bundle Identifier&nbsp;for your app. You can also provide values for&nbsp;<strong>Team&nbsp;</strong>and&nbsp;<strong>Organization Name&nbsp;or leave it with the default values for now. When you press Next, you’ll be prompted to select the location where you will</strong> store the project. Select your preferred location and click on <strong>Create</strong>.</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224300.png?resize=512%2C335&#038;ssl=1" alt="" class="wp-image-448" width="512" height="335" srcset="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224300.png?resize=1024%2C669&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224300.png?resize=300%2C196&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224300.png?resize=768%2C502&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224300.png?w=1165&amp;ssl=1 1165w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure>



<p>The next page is for defining your configurations for the app. You can choose the version of iOS from the drop-down menu. </p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224601.png?resize=512%2C330&#038;ssl=1" alt="" class="wp-image-449" width="512" height="330" srcset="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224601.png?resize=1024%2C660&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224601.png?resize=300%2C193&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224601.png?resize=768%2C495&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-224601.png?w=1173&amp;ssl=1 1173w" sizes="(max-width: 512px) 100vw, 512px" data-recalc-dims="1" /></figure>



<p>Open ViewController.swift file from your left-hand pane, which contains the code we need to change.</p>



<h4>Time to write some code</h4>



<p>To use the system UI and web configuration, we first import the UI kit and Web kit in<strong> ViewController.swift</strong></p>



<pre class="wp-block-code"><code>import UIKit    
import WebKit</code></pre>



<p>Next, we extend&nbsp;ViewController&nbsp;class by implementing the <strong>WKNavigationDelegate</strong> protocol.</p>



<p><em>class ViewController: UIViewController, WKNavigationDelegate {</em></p>



<p>Then within the ViewController class, define the WKWebView property, which will be used to store the reference objects.</p>



<pre class="wp-block-code"><code>var webView: WKWebView!</code></pre>



<p>We will not get into iOS development. Use the below lines of code, and your working app should be ready to run in the simulator. </p>



<pre class="wp-block-code"><code>import UIKit
import WebKit

class ViewController: UIViewController {
class ViewController: UIViewController, WKNavigationDelegate {
    var webView: WKWebView!

    override func loadView() {
        webView = WKWebView()
        webView.navigationDelegate = self
        view = webView
    }

    override func viewDidLoad() {
        super.viewDidLoad()
       
        let url = URL(string: "https://www.intuneirl.com")!
        webView.load(URLRequest(url: url))
        webView.allowsBackForwardNavigationGestures = true
    }</code></pre>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-225032.png?resize=750%2C485&#038;ssl=1" alt="" class="wp-image-450" width="750" height="485" srcset="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-225032.png?resize=1024%2C662&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-225032.png?resize=300%2C194&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-225032.png?resize=768%2C497&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-225032.png?w=1167&amp;ssl=1 1167w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>Play Around</h4>



<p>The simulator app within Xcode presents the iPhone, iPad, Mac, or Apple Watch user interface in a window on your Mac computer. You interact with Simulator using the keyboard and the mouse to emulate taps, device rotation, and other user actions.</p>



<p>For this blog, we will stick to the basics of using a Simulator and perform all these steps using our own iOS webview app.</p>



<p>From the top bar, select the iOS device on which you would like to test your app and press the button with the &#8220;<strong>Play</strong>&#8221; icon to launch the simulator. </p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-12.39.13-1.png?resize=750%2C496&#038;ssl=1" alt="" class="wp-image-452" width="750" height="496" srcset="https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-12.39.13-1.png?resize=1024%2C677&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-12.39.13-1.png?resize=300%2C198&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-12.39.13-1.png?resize=768%2C508&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Screenshot-2022-10-03-at-12.39.13-1.png?w=1252&amp;ssl=1 1252w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-232711.png?resize=750%2C527&#038;ssl=1" alt="" class="wp-image-453" width="750" height="527" srcset="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-232711.png?resize=1024%2C720&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-232711.png?resize=300%2C211&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-232711.png?resize=768%2C540&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-232711.png?w=1322&amp;ssl=1 1322w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233619.png?resize=750%2C568&#038;ssl=1" alt="" class="wp-image-454" width="750" height="568" srcset="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233619.png?resize=1024%2C776&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233619.png?resize=300%2C227&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233619.png?resize=768%2C582&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233619.png?w=1208&amp;ssl=1 1208w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233640.png?resize=750%2C569&#038;ssl=1" alt="" class="wp-image-455" width="750" height="569" srcset="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233640.png?resize=1024%2C777&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233640.png?resize=300%2C228&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233640.png?resize=768%2C583&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233640.png?w=1196&amp;ssl=1 1196w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233655.png?resize=750%2C529&#038;ssl=1" alt="" class="wp-image-456" width="750" height="529" srcset="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233655.png?resize=1024%2C723&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233655.png?resize=300%2C212&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233655.png?resize=768%2C542&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233655.png?w=1308&amp;ssl=1 1308w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>You can also see the performance of your app in the simulator. It will show how much CPU or memory your app is consuming.</p>



<figure class="wp-block-image size-large is-resized"><img decoding="async" loading="lazy" src="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233726.png?resize=750%2C502&#038;ssl=1" alt="" class="wp-image-457" width="750" height="502" srcset="https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233726.png?resize=1024%2C685&amp;ssl=1 1024w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233726.png?resize=300%2C201&amp;ssl=1 300w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233726.png?resize=768%2C514&amp;ssl=1 768w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233726.png?resize=360%2C240&amp;ssl=1 360w, https://irlimages.blob.core.windows.net/2022-10/Annotation-2022-10-03-233726.png?w=1132&amp;ssl=1 1132w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>Publish The App</h4>



<p>Everything looks good till here. Now, follow the steps in this <a rel="noreferrer noopener" href="https://intuneirl.com/2022/08/code-sign-publish-your-ios-apps/" target="_blank">blog post to create a .ipa</a> for the app, and then you can publish it to Apple App Store or even distribute it through your MDM solution. </p>



<p>If you want to use MAM capabilities, wrap the app and distribute it. The steps are here &#8211;  <a href="https://intuneirl.com/2022/09/wrap-me-up/">Wrap me Up!</a>.</p>



<p>Awesome..I can imagine that feeling. You just created &amp; developed your first iOS app &#8211; High5✋</p>



<p>Share your feedback and comments, and keep learning. &#8220;<strong>Challenges drive Us</strong>&#8220;<strong> #mempowered</strong></p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="498" height="269" src="https://irlimages.blob.core.windows.net/2022-10/boom-gotcha.gif?resize=498%2C269&#038;ssl=1" alt="" class="wp-image-458" data-recalc-dims="1"/></figure>



<p><strong><em>Stay In(tuned) to create a webview app for Android. </em></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!--kg-card-end: html-->