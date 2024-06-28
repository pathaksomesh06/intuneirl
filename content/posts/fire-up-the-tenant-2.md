---
title: "Fire Up The Tenant!"
date: 2022-02-01T13:10:00"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<p>The foundation for configuring any services in the cloud is a “Tenant.” This post will help you plan/set up Intune as your Mobile Device Management solution. Following these steps, you will sign up for Intune tenant and add a domain, followed by adding test users.</p>



<h5 class="wp-block-grigora-kit-text grigora-kit-text block-id-text-1664002080007"><span style="text-decoration: underline;">Sign up or sign in to Microsoft Intune</span></h5>



<p>If you don’t have an Intune portal yet, you can sign in for a trial period – it allows you to evaluate Intune for 30 days.</p>



<p>Open <a href="https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20" rel="noreferrer noopener" target="_blank"><strong>Intune Sign-up page</strong></a><strong> </strong>and follow the steps as shown below:</p>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="602" height="291" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/1-1.jpg?resize=602%2C291&ssl=1" alt="" class="wp-image-211" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/1-1.jpg?w=602&ssl=1 602w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/1-1.jpg?resize=300%2C145&ssl=1 300w" sizes="(max-width: 602px) 100vw, 602px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="471" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-1.png?resize=750%2C471&ssl=1" alt="" class="wp-image-212" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-1.png?resize=1024%2C643&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-1.png?resize=300%2C188&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-1.png?resize=768%2C482&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/2-1.png?w=1265&ssl=1 1265w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="351" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/3-1.png?resize=750%2C351&ssl=1" alt="" class="wp-image-213" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/3-1.png?resize=1024%2C479&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/3-1.png?resize=300%2C140&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/3-1.png?resize=768%2C359&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/3-1.png?resize=1536%2C718&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/3-1.png?w=1835&ssl=1 1835w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="288" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/4.png?resize=750%2C288&ssl=1" alt="" class="wp-image-214" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/4.png?resize=1024%2C393&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/4.png?resize=300%2C115&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/4.png?resize=768%2C294&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/4.png?resize=1536%2C589&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/4.png?w=1852&ssl=1 1852w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-full"><img decoding="async" loading="lazy" width="750" height="356" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/5.png?resize=750%2C356&ssl=1" alt="" class="wp-image-215" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/5.png?w=1021&ssl=1 1021w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/5.png?resize=300%2C143&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/5.png?resize=768%2C365&ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="497" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/6.png?resize=750%2C497&ssl=1" alt="" class="wp-image-216" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/6.png?resize=1024%2C679&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/6.png?resize=300%2C199&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/6.png?resize=768%2C509&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/6.png?w=1346&ssl=1 1346w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="450" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/7.png?resize=750%2C450&ssl=1" alt="" class="wp-image-217" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/7.png?resize=1024%2C614&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/7.png?resize=300%2C180&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/7.png?resize=768%2C460&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/7.png?w=1512&ssl=1 1512w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="360" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/8.png?resize=750%2C360&ssl=1" alt="" class="wp-image-218" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/8.png?resize=1024%2C492&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/8.png?resize=300%2C144&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/8.png?resize=768%2C369&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/8.png?resize=1536%2C738&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/8.png?w=1920&ssl=1 1920w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<figure class="wp-block-image size-large"><img decoding="async" loading="lazy" width="750" height="390" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/9.png?resize=750%2C390&ssl=1" alt="" class="wp-image-219" srcset="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/9.png?resize=1024%2C532&ssl=1 1024w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/9.png?resize=300%2C156&ssl=1 300w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/9.png?resize=768%2C399&ssl=1 768w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/9.png?resize=1536%2C797&ssl=1 1536w, https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/09/9.png?w=1720&ssl=1 1720w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>That’s all for today. In the next post, I will walk you through managing iOS/iPadOS devices, in which I will explain all about <strong>D-U-N-S, ABM, DEP(ADE), APNs & VPP</strong>. </p>



<p>Managing Apple Devices will be a long series…so stay <strong>(In)tuned</strong>. Happy Learning 👩‍💻</p>

<!--kg-card-end: html-->
