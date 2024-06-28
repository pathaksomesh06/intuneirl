---
title: "Integrating Adobe With OneDrive for Business on iOS/iPadOS Devices Enrolled in Intune"
date: 2023-06-30T08:22:29"
draft: false
tags: []
---

<p>With the burgeoning growth of remote work and digital environments, many organizations are relying heavily on cloud storage solutions like Microsoft OneDrive for Business and mobile device management (MDM) systems like Microsoft Intune. Adding to this, Adobe Acrobat Reader is a ubiquitous tool for managing PDF files, widely used in professional settings. This post will guide you through the process of integrating Adobe with OneDrive for Business on iOS/iPadOS devices that are enrolled in Intune.</p>
<hr>
<h2 id="prerequisites">Prerequisites</h2>
<p>Before getting started, ensure that you have the following:</p>
<ol><li>An active Office 365 subscription with OneDrive for Business.</li><li>Microsoft Intune is set up for your organization.</li><li>iOS devices enrolled in Intune.</li><li>Adobe Acrobat Reader is installed on your iOS devices.</li></ol>
<hr>
<h3 id="some-pre-work">Some Pre-Work</h3>
<p>Adobe Acrobat updated their application to include deeper integration with Microsoft including access to OneDrive for Business files. This integration allows users to access their OneDrive for Business files from the Acrobat app. The improvements have a few configuration changes which will require that Intune admins approve the Adobe Acrobat app to connect to the Intune service. This is a one-time approval that you may not have had to do historically when connecting Adobe Acrobat and OneDrive for Business.</p>
<p>There are two options for this one-time approval:</p>
<ol><li>Use the latest Adobe Acrobat iOS and enable the OneDrive feature:</li></ol>
<p></p>
<figure class="kg-card kg-image-card"><img src="https://techcommunity.microsoft.com/t5/image/serverpage/image-id/262281iF6BB9FBFB38FBDC6/image-size/large?v=v2&amp;px=999" class="kg-image" alt="thumbnail image 1 captioned Adobe Acrobat Reader for PDF approval prompt" loading="lazy"></figure>
<ol start="2"><li>Then associate the product with your organization:</li></ol>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-34.png" class="kg-image" alt="" loading="lazy" width="438" height="700"></figure>
<hr>
<h3 id="configurations-required-in-intune">Configurations Required In Intune</h3>
<ol><li>Configure OneDrive for Business with Intune. You can add ODB as an app store or as a VPP app. I prefer using VPP apps with device-based licensing.</li></ol>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-35.png" class="kg-image" alt="" loading="lazy" width="1363" height="313" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-35.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-35.png 1000w, __GHOST_URL__/content/images/2023/06/image-35.png 1363w" sizes="(min-width: 720px) 720px"></figure>
<ol start="2"><li>Add Adobe Reader as a VPP app and deploy it to the required group. </li></ol>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-36.png" class="kg-image" alt="" loading="lazy" width="1434" height="306" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-36.png 600w, __GHOST_URL__/content/images/size/w1000/2023/06/image-36.png 1000w, __GHOST_URL__/content/images/2023/06/image-36.png 1434w" sizes="(min-width: 720px) 720px"></figure>
<ol start="3"><li>Configure the SSO profile to allow Adobe Reader for SSO</li></ol>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-37.png" class="kg-image" alt="" loading="lazy" width="775" height="476" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-37.png 600w, __GHOST_URL__/content/images/2023/06/image-37.png 775w" sizes="(min-width: 720px) 720px"></figure>
<ol start="4"><li>Configure App Protection Policy to keep the personal &amp; corporate data separated:</li></ol>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-38.png" class="kg-image" alt="" loading="lazy" width="752" height="585" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-38.png 600w, __GHOST_URL__/content/images/2023/06/image-38.png 752w" sizes="(min-width: 720px) 720px"></figure>
<hr>
<h3 id="configurations-required-at-end-user-side">Configurations Required at End User Side</h3>
<p>After the device enrollment and app distribution process is complete, the only action required from the user is to activate the "Intune App Protection" switch within the Adobe Reader application. To do this follow the below steps:</p>
<ol><li>Launch the Adobe Reader app on the device</li><li>Navigate to "Preferences"</li><li>Toggle the "Intune App Protection" switch to ON</li><li>Follow the prompts for App Protection Policy for setting app PIN.</li></ol>
<figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2023/06/image-39.png" class="kg-image" alt="" loading="lazy" width="720" height="903" srcset="__GHOST_URL__/content/images/size/w600/2023/06/image-39.png 600w, __GHOST_URL__/content/images/2023/06/image-39.png 720w" sizes="(min-width: 720px) 720px"></figure>
<p>That's all needed!</p>
<h3 id="time-for-demo">Time For Demo</h3>
<figure class="kg-card kg-video-card kg-width-regular" data-kg-thumbnail="https://www.intuneirl.com/content/media/2023/06/Adobe-ODB_thumb.jpg" data-kg-custom-thumbnail="https://www.intuneirl.com/content/images/2023/06/Untitled.png">
            <div class="kg-video-container">
                <video src="__GHOST_URL__/content/media/2023/06/Adobe-ODB.mp4" poster="https://img.spacergif.org/v1/720x960/0a/spacer.png" width="720" height="960" playsinline="" preload="metadata" style="background: transparent url('__GHOST_URL__/content/images/2023/06/Untitled.png') 50% 50% / cover no-repeat;"></video>
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
                            /<span class="kg-video-duration">0:49</span>
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
<p>There you have it! Adobe Acrobat Reader is now linked with OneDrive for Business on your Intune-enrolled iOS devices. Users can now open, edit, and save PDFs directly to their OneDrive for Business, offering greater flexibility and along with protecting your corporate data.</p>