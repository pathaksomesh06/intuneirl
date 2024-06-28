---
title: "Simplifying MDM Support with Power Virtual Agents and Power Apps"
date: 2023-06-28T20:20:20"
draft: false
tags: []
---

<p>IT support has developed into a crucial component of any modern organization as we become more reliant on digital tools and remote work. Yet, it can be daunting due to the amount of manual work involved, especially for large organizations. Thankfully, Microsoft’s Power Platform is here to simplify things.</p>
<p>This blog post will guide you through creating a self-service IT support bot using Power Virtual Agents and Microsoft Teams, particularly focusing on managing devices enrolled in Microsoft Intune. This blog will be followed by another post with a device management app with Power Apps, powered by Microsoft Teams and Azure AD.</p>
<hr>
<h2 id="getting-started">Getting Started</h2>
<p>Power Virtual Agents allows anyone, regardless of their technical expertise, to create intelligent chatbots capable of resolving common issues. It integrates seamlessly with Power Automate, Microsoft's tool for creating automated workflows between apps and services. I wanted my bot to be capable of automatically starting conversations and managing devices enrolled in Microsoft Intune. </p>
<h3 id="high-level-steps">High-Level Steps</h3>
<ol><li><strong>Set up Power Virtual Agents in Teams:</strong> The first step is adding Power Virtual Agents to Microsoft Teams. The bot is designed to automatically greet the user and offer a list of common issues.</li><li><strong>Define the Bot's Skills: </strong>Next step is defining topics - the specific areas the bot is equipped to discuss, like 'Device Compliance Status', 'Passcode Resets', 'Troubleshooting Guides', and 'Software Updates'. For each topic, it requires designing a conversation flow using an intuitive graphical interface. The flow often involves asking the user for more information, like a device ID.</li><li><strong>Integrate Power Automate: </strong>In all these scenarios, the bot's capabilities are powered by backend flows created in Power Automate. These flows start with an HTTP request trigger that receives the Device ID from the bot.</li></ol>
<h3 id="prerequisites">Prerequisites</h3>
<p>To create and manage Power Virtual Agents chatbots in Teams, you need:</p>
<ul><li>A license to use Teams</li><li>Licenses to use Power Virtual Agents</li><li>Required permissions for using Graph APIs</li><li>Intune Admin</li><li>Power Automate</li></ul>
<p>For this blog post, I have created a few common topics that are the most common support requests for managing devices enrolled in Intune. You can add additional scenarios such as Feature Update, Bitlocker Key, on-demand Sync, and much more.</p>
<p><strong>Let’s get started!</strong></p>
<hr>
<h3 id="create-a-bot">Create A Bot</h3>
<ul><li>Go to the <a href="https://web.powerva.microsoft.com/">Power Virtual Agents home page</a>.</li><li>In the navigation menu select <strong>Create</strong>. You can also select <strong>Home</strong> then select <strong>Create a Bot</strong>.</li></ul>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-22.png" class="kg-image" alt="" loading="lazy" width="1734" height="466" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-22.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-22.png 1000w, __GHOST_URL__/content/images/size/w1600/2023/06/image-22.png 1600w, __GHOST_URL__/content/images/2023/06/image-22.png 1734w" sizes="(min-width: 720px) 720px"></figure>
<ul><li>For <strong>Name your bot</strong>, enter a name for your bot.</li><li>For <strong>What language will your bot speak</strong>, select the language you want your bot to speak.</li><li>Select <strong>Create</strong>.</li></ul>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-24.png" class="kg-image" alt="" loading="lazy" width="1881" height="852" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-24.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-24.png 1000w, __GHOST_URL__/content/images/size/w1600/2023/06/image-24.png 1600w, __GHOST_URL__/content/images/2023/06/image-24.png 1881w" sizes="(min-width: 720px) 720px"></figure>
<hr>
<h3 id="create-topics">Create Topics</h3>
<p>Microsoft's Power Virtual Agents allows you to create topics to help guide conversations with users. Topics are essentially dialog trees that your bot can follow based on keywords or phrases provided by the user. Here's how to create new topics.</p>
<ul><li>Once in the Topics page, find the option "New Topic" usually at the top,ö and click on it. This will open a new topic creation page.</li><li>First, give a name to your topic. After that, input some trigger phrases. These are phrases that you anticipate your users might say that would make the bot start this topic. For example, I am creating a topic about 'Password Reset', trigger phrases could include "I want to reset my password", "How can I reset my domain password?" etc.</li><li>Once you've set up your trigger phrases, start creating the conversation flow for your bot. This is where you'll design the path of interaction the bot will take once a topic is triggered.</li><li>Use the <code>Message</code> node to send messages to the user.</li><li>Use the <code>Question</code> node to ask something to the user.</li><li>Use the <code>Condition</code> node to create conditional paths in your conversation.</li><li>Use the <code>Call an action</code> node to connect with Power Automate flows, which allow you to connect to external systems.</li><li>Use the <code>End with survey</code> node to close a conversation and ask for feedback.</li></ul>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-26.png" class="kg-image" alt="" loading="lazy" width="1855" height="464" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-26.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-26.png 1000w, __GHOST_URL__/content/images/size/w1600/2023/06/image-26.png 1600w, __GHOST_URL__/content/images/2023/06/image-26.png 1855w" sizes="(min-width: 720px) 720px"></figure>
<hr>
<h3 id="author-edit-the-conversation-flow">Author &amp; Edit The Conversation Flow</h3>
<p>Let's take an example of the Greetings topic. This is the first topic, which will initiate the dialog between your user and the Bot. Here, I have modified the sample topic in my bot.</p>
<p>First, I modified the trigger phases, so that the conversation can start. You can also modify the index.html file to let the Bot automatically start the conversation.</p>
<p>Next, I incorporated a "question" node where the bot greets the user by their name and provides them with a list of options for which the bot can offer assistance.</p>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-27.png" class="kg-image" alt="" loading="lazy" width="1557" height="851" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-27.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-27.png 1000w, __GHOST_URL__/content/images/2023/06/image-27.png 1557w" sizes="(min-width: 720px) 720px"></figure>
<p>Depending on the user's selection from the response options, I have implemented conditions to guide the conversation to the relevant topics. For instance, if a user chooses "Device Compliance", the bot will then direct the conversation toward the "Device Compliance" topic.</p>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-28.png" class="kg-image" alt="" loading="lazy" width="1618" height="714" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-28.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-28.png 1000w, __GHOST_URL__/content/images/size/w1600/2023/06/image-28.png 1600w, __GHOST_URL__/content/images/2023/06/image-28.png 1618w" sizes="(min-width: 720px) 720px"></figure>
<p>To achieve this transition, you need to have the topics created and configured.</p>
<p>Revisiting the example, let's assume the user chooses "device compliance". In this scenario, the bot transitions the conversation to the "device compliance" topic. Within this topic, I've also incorporated triggers so that if users need to verify the compliance of their registered device, they can directly access this topic.</p>
<p>To foster a more productive conversation, the bot is programmed to inquire about the specific device platform for which the user wishes to check compliance. This is a useful feature, considering it's common for a user to have multiple devices.</p>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-29.png" class="kg-image" alt="" loading="lazy" width="1329" height="734" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-29.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-29.png 1000w, __GHOST_URL__/content/images/2023/06/image-29.png 1329w" sizes="(min-width: 720px) 720px"></figure>
<p>Now we're at the point where you'll be interacting with Graph APIs. Based on the user's chosen platform, I've stored the response in a variable that's then utilized within Power Automate. I've employed the "call an action" node to invoke the Power Automate flows configured to execute this sequence.</p>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-30.png" class="kg-image" alt="" loading="lazy" width="1384" height="739" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-30.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-30.png 1000w, __GHOST_URL__/content/images/2023/06/image-30.png 1384w" sizes="(min-width: 720px) 720px"></figure>
<p>To ensure an interactive conversation, I've incorporated conditions to capture the user's response. For example, we can determine whether the user needs to be redirected to a service desk agent for additional support, or whether they are satisfied with the assistance they've received.</p>
<p>Let's consider a different scenario, such as a Passcode Reset. Since the passcode reset command is exclusively applicable to iOS and iPadOS devices, the bot will autonomously verify any such devices the user has registered in Intune and will display the device details. The user is then prompted to enter the device ID for the device that needs unlocking.</p>
<p>If the device unlock attempt is unsuccessful, the conversation is then routed to a readily available Service Desk agent for further assistance. The design as below:</p>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-31.png" class="kg-image" alt="" loading="lazy" width="1009" height="722" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-31.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-31.png 1000w, __GHOST_URL__/content/images/2023/06/image-31.png 1009w" sizes="(min-width: 720px) 720px"></figure>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-32.png" class="kg-image" alt="" loading="lazy" width="1110" height="726" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-32.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-32.png 1000w, __GHOST_URL__/content/images/2023/06/image-32.png 1110w" sizes="(min-width: 720px) 720px"></figure>
<hr>
<h2 id="quick-demo">Quick Demo</h2>
<figure class="kg-card kg-video-card kg-width-regular" data-kg-thumbnail="https://www.intuneirl.com/content/media/2023/06/Topics---IRL-EnterpriseElf-_-Power-Virtual-Agents_thumb.jpg" data-kg-custom-thumbnail="">
            <div class="kg-video-container">
                <video src="__GHOST_URL__/content/media/2023/06/Topics---IRL-EnterpriseElf-_-Power-Virtual-Agents.webm" poster="https://img.spacergif.org/v1/1920x930/0a/spacer.png" width="1920" height="930" playsinline="" preload="metadata" style="background: transparent url('__GHOST_URL__/content/media/2023/06/Topics---IRL-EnterpriseElf-_-Power-Virtual-Agents_thumb.jpg') 50% 50% / cover no-repeat;"></video>
                <div class="kg-video-overlay">
                    <button class="kg-video-large-play-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                            <path d="M23.14 10.608 2.253.164A1.559 1.559 0 0 0 0 1.557v20.887a1.558 1.558 0 0 0 2.253 1.392L23.14 13.393a1.557 1.557 0 0 0 0-2.785Z"></path>
                        </svg>
                    </button>
                </div>
                <div class="kg-video-player-container">
                    <div class="kg-video-player">
                        <button class="kg-video-play-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                                <path d="M23.14 10.608 2.253.164A1.559 1.559 0 0 0 0 1.557v20.887a1.558 1.558 0 0 0 2.253 1.392L23.14 13.393a1.557 1.557 0 0 0 0-2.785Z"></path>
                            </svg>
                        </button>
                        <button class="kg-video-pause-icon kg-video-hide">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                                <rect x="3" y="1" width="7" height="22" rx="1.5" ry="1.5"></rect>
                                <rect x="14" y="1" width="7" height="22" rx="1.5" ry="1.5"></rect>
                            </svg>
                        </button>
                        <span class="kg-video-current-time">0:00</span>
                        <div class="kg-video-time">
                            /<span class="kg-video-duration">2:30</span>
                        </div>
                        <input type="range" class="kg-video-seek-slider" max="100" value="0">
                        <button class="kg-video-playback-rate">1×</button>
                        <button class="kg-video-unmute-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                                <path d="M15.189 2.021a9.728 9.728 0 0 0-7.924 4.85.249.249 0 0 1-.221.133H5.25a3 3 0 0 0-3 3v2a3 3 0 0 0 3 3h1.794a.249.249 0 0 1 .221.133 9.73 9.73 0 0 0 7.924 4.85h.06a1 1 0 0 0 1-1V3.02a1 1 0 0 0-1.06-.998Z"></path>
                            </svg>
                        </button>
                        <button class="kg-video-mute-icon kg-video-hide">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                                <path d="M16.177 4.3a.248.248 0 0 0 .073-.176v-1.1a1 1 0 0 0-1.061-1 9.728 9.728 0 0 0-7.924 4.85.249.249 0 0 1-.221.133H5.25a3 3 0 0 0-3 3v2a3 3 0 0 0 3 3h.114a.251.251 0 0 0 .177-.073ZM23.707 1.706A1 1 0 0 0 22.293.292l-22 22a1 1 0 0 0 0 1.414l.009.009a1 1 0 0 0 1.405-.009l6.63-6.631A.251.251 0 0 1 8.515 17a.245.245 0 0 1 .177.075 10.081 10.081 0 0 0 6.5 2.92 1 1 0 0 0 1.061-1V9.266a.247.247 0 0 1 .073-.176Z"></path>
                            </svg>
                        </button>
                        <input type="range" class="kg-video-volume-slider" max="100" value="100">
                    </div>
                </div>
            </div>
            
        </figure>
<hr>
<h3 id="wrapping-up">Wrapping Up</h3>
<p>The combination of Power Virtual Agents and Power Automate can significantly streamline IT support and device management. Not only does it automate many manual tasks, but it also ensures users get immediate help when needed, and IT administrators have the tools they need to manage devices effectively.</p>
<p>I hope this walkthrough inspires you to explore how Microsoft’s Power Platform can transform your organization. Remember, every organization is unique, so feel free to tweak the steps to best suit your needs. Happy building!</p>