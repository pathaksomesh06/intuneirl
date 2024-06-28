---
title: "Add, Distribute & Manage VPP Apps"
date: 2022-08-06T20:33:00"
draft: false
tags: []
---


<!--kg-card-begin: html-->

<p>In previous blogs, we discussed how to&nbsp;<a href="https://intuneirl.com/2022/07/registering-for-d-u-n-s/" target="_blank" rel="noreferrer noopener">register for DUNS</a>&nbsp;and&nbsp;<a href="https://intuneirl.com/2022/05/onboarding-to-apple-business-manager/" target="_blank" rel="noreferrer noopener">onboarding in ABM</a>; continuing with that, the next part is purchasing, distributing &amp; managing the VPP apps.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Why should we use ABM for App Management &amp; Distribution?</strong></h4>



<p>By using Apple Business Manager (ABM), an organization can easily purchase and manage apps &amp; books from Apple App Store. It can leverage any MDM solution to distribute the apps &amp; books to their end users or devices even when the app store is disabled on the device!</p>



<p>But before that, let&#8217;s understand the different roles in ABM.</p>



<p><strong>Users and Roles in ABM:</strong></p>



<p>There are different ways of creating or importing users in Apple Business Manager; e.g.</p>



<ul><li>You can create users manually in ABM&nbsp;</li><li>You can import users from SCIM from Azure AD</li><li>You can import users from Google Workspace</li><li>You can federate authentication with your AAD or Google Workspace</li></ul>



<p>For each user account, there is a user state also depending upon its status.</p>



<ul><li>New</li><li>Active</li><li>Deactivated</li><li>Locked</li></ul>



<p>P.S: When manually creating a user in ABM, it is mandatory to provide an&nbsp;<strong>e-mail address</strong>&nbsp;and&nbsp;<strong>assign a role</strong>&nbsp;to it. The e-mail address should not have been used with any other Apple services.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Roles in Apple Business Manager:</strong></h4>



<p>Every user in ABM must have at least one role, and each role has certain privileges. The below table will help you with a basic idea of the roles available in ABM:</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/Screenshot 2024-04-10 at 21.28.35.png" alt="" width="676" height="308"/></figure>



<p>The privileges (rights) with roles in ABM are:</p>



<ul><li>People Privileges</li><li>Device Privileges</li><li>Content Privileges</li><li>Staff Privileges</li><li>Basic Privileges</li></ul>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4><strong>Add a new user in ABM:</strong></h4>



<p>1. Log in to&nbsp;<a rel="noreferrer noopener" href="https://business.apple.com/#main/accounts" target="_blank">Apple Business Manager</a>&nbsp;with a user that has an Administrator role.</p>



<p>(The user signing up for the ABM for the first time by default becomes the first administrator in ABM).</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/Screenshot 2024-04-10 at 21.31.28.png" alt="" width="606" height="411"/></figure>



<p>2. Click&nbsp;<strong>Users&nbsp;</strong>in the left sidebar, click the&nbsp;<strong>Add</strong>&nbsp;button, enter the required details, and click <strong>Save</strong>.</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/Screenshot 2024-04-10 at 21.33.56.png" alt="" width="640" height="299"/></figure>



<p><strong>Create sign-in information for the new user:</strong></p>



<p>1. Sign in to Apple Business Manager and click Users, then search for the newly created&nbsp;user.</p>



<p>2. Select the user from the list and click <strong>Create Sign-in</strong>&nbsp;to create new sign-in&nbsp;information for the new user.</p>



<p>3. Select how you want to send the information to the user. You can either download the&nbsp;information as a pdf or CSV, or you can e-mail the information to the user.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<p>We have created users in ABM and assigned required roles to the user, so now let us discuss how to purchase &amp; distribute content.</p>



<p>As a best practice, you should always assign apps to devices instead of users, avoiding requiring a user to use an Apple ID on the device. However, if you are distributing enterprise books, they can’t be assigned to devices.&nbsp;</p>




<p>You can purchase apps and books in Apple Business Manager and can also purchase Custom Apps from developers as B2B apps.</p>



<p><em>Note:</em>&nbsp;You must set up your payment method before adding apps, even if they are free.</p>



<p>&nbsp;<strong>Search and Purchase App in ABM</strong></p>



<p>&nbsp;1. Log in to Apple Business Manager and click&nbsp;<strong>Apps and Books</strong>, then search for an app or<br>&nbsp;&nbsp;&nbsp;&nbsp;book in the search field.&nbsp;</p>



<figure class="wp-block-image is-resized"><img decoding="async" loading="lazy" src="https://irlscreenshots.blob.core.windows.net/wordpress-images/images/wordpress/2022/10/Screenshot2024-04-1021.36.04.png" alt="" width="960" height="432"/></figure>



<p>2. &nbsp;Select the app or book in the search results list that you want to purchase.</p>



<p>3. Select the&nbsp;<strong>location&nbsp;</strong>where the app or book licenses will be initially assigned.</p>



<p>4. Enter the number of licenses, and if necessary, change the payment method, then click<strong> Buy</strong></p>


<p>&nbsp;5. Availability of app licenses depends on the amount purchased. If you purchased:</p>



<ul><li>5000 licenses or fewer, they are immediately processed</li><li>5001 to 19,999 licenses, they are processed daily after 1:00 p.m., Pacific time</li><li>20,000 licenses or more, they are processed daily after 4:00 p.m., Pacific time</li></ul>



<p>Alternatively, you can force sync your VPP token in Intune to immediately sync for the purchase to be processed.</p>



<hr class="wp-block-separator has-alpha-channel-opacity"/>



<h4>&nbsp;<strong>Assign a Volume-Purchased App</strong></h4>



<p>&nbsp;Once the apps are synced to your Intune tenant, you can start distributing them. Follow the below steps to distribute VPP apps:</p>



<p>1. Log in to&nbsp;<a href="https://endpoint.microsoft.com/" rel="noreferrer noopener" target="_blank">Microsoft Endpoint Manager Portal</a>.&nbsp;</p>



<p>2. Select&nbsp;<strong>Apps</strong>&nbsp;&gt;&nbsp;<strong>All apps</strong>.</p>



<p>3. On the list of apps pane, choose the app you want to assign and then choose&nbsp;<strong>Properties&nbsp;</strong></p>



<p>4. On the&nbsp;<strong>Assignments</strong>&nbsp;tab, choose whether the app will be&nbsp;<strong>Required</strong>&nbsp;or&nbsp;<strong>Available for enrolled devices.</strong></p>



<p>5.<strong>&nbsp;</strong>Assing it to<strong>&nbsp;the&nbsp;</strong>user or device groups you want to assign the app.</p>



<p>(Photo Credits: Apple.com)</p>

<!--kg-card-end: html-->
