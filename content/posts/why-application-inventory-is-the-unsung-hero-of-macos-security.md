---
title: "Application Inventory: The Unsung Hero of macOS Security"
date: 2024-05-06T11:09:00"
draft: false
tags: []
---

<p>In the ever-evolving threat landscape, keeping your organization's macOS devices secure is paramount. While Mobile Device Management (MDM) solutions offer a valuable layer of control, a critical piece of the puzzle often gets overlooked: <strong>application inventory</strong>.</p><p>This blog post dives into the importance of a comprehensive application inventory for macOS devices, explores the limitations of MDM reporting, and highlights the security benefits gained from improved application visibility.</p><hr><h3 id="the-silent-threat-unseen-applications">The Silent Threat: Unseen Applications</h3><p>Imagine a blind spot in your home security system. That's essentially what an incomplete application inventory creates for your macOS environment. MDM solutions often focus on device details and pre-approved applications.However, this leaves a gap for unauthorized applications, potentially exposing your network to vulnerabilities.</p><p>Malware can disguise itself as legitimate applications, making it crucial to have a complete picture of everything running on your Macs. Additionally, outdated or unmaintained software can pose security risks.</p><h3 id="beyond-pre-approved-apps">Beyond Pre-Approved Apps</h3><p>While mostly all MDM excels at managing pre-approved applications, it often felt like a shortcoming when it comes to comprehensive application discovery. Here are some limitations to consider:</p><ul><li><strong>Limited Visibility:</strong> MDM might not report on all applications, especially those installed outside the designated channels (e.g., user downloads).</li><li><strong>Version Control Challenges:</strong> Version tracking for discovered applications may be limited, making it difficult to identify outdated software with known vulnerabilities.</li><li><strong>Static Reporting:</strong> MDM reports typically provide a snapshot in time, sometimes limiting to capture applications continuously installed, removed, or updated.</li></ul><h3 id="the-power-of-application-inventory">The Power of Application Inventory</h3><p>A robust application inventory solution fills the gaps left by MDM, offering significant security benefits:</p><ul><li><strong>Enhanced Threat Detection:</strong>&nbsp;By identifying all applications, you can discover unauthorized software that might harbor malware.</li><li><strong>Vulnerability Management:</strong>&nbsp;Identify outdated applications with known vulnerabilities and prioritize patching to minimize the attack surface.</li><li><strong>Improved Compliance:</strong>&nbsp;Ensure adherence to software licensing agreements and internal security policies by monitoring application usage.</li><li><strong>Streamlined Security Audits:</strong>&nbsp;A complete application inventory simplifies security audits by providing a centralized view of your software landscape.</li></ul><hr><h3 id="beyond-security-the-added-value-of-application-inventory">Beyond Security: The Added Value of Application Inventory</h3><p>The benefits of application inventory extend beyond just security. It empowers you to:</p><ul><li><strong>Optimize Software Licensing:</strong>&nbsp;Gain insights into software usage patterns, allowing for informed decisions about licensing costs.</li><li><strong>Identify Shadow IT:</strong>&nbsp;Discover unsanctioned software deployments and improve overall IT governance.</li><li><strong>Simplify Software Deployment:</strong>&nbsp;Plan and deploy software updates more effectively through a comprehensive understanding of your application ecosystem.</li></ul><hr><h3 id="taking-control-building-a-comprehensive-inventory-with-intune-and-azure-log-analytics">Taking Control: Building a Comprehensive Inventory with Intune and Azure Log Analytics</h3><p>Traditionally, building a comprehensive application inventory required additional tools. However, by leveraging Microsoft Intune and Azure Log Analytics, you can achieve this with a custom script.</p><p><strong>The Power of Automation:</strong></p><p>The script utilizes a bash script running on macOS devices enrolled in Intune. This script gathers application data and sends it securely to your Azure Log Analytics workspace for centralized analysis.</p><p><strong>Benefits of this Approach:</strong></p><ul><li><strong>Centralized Visibility:</strong>&nbsp;Gain a holistic view of all applications installed across your macOS devices.</li><li><strong>Continuous Updates:</strong>&nbsp;Schedule automatic script execution to ensure your inventory stays up-to-date.</li><li><strong>Seamless Integration:</strong>&nbsp;Leverages existing tools within the Microsoft ecosystem for a streamlined solution.</li></ul><h3 id="building-the-macos-application-inventory-script">Building the macOS Application Inventory Script</h3><p>The following lines define variables for the&nbsp;<code>CustomerId</code>&nbsp;(your Azure Log Analytics workspace ID) and&nbsp;<code>SharedKey</code>&nbsp;(your workspace's primary key).&nbsp;These are placeholders; you'll need to replace them with your actual values before deployment.</p><pre><code class="language-bash">#!/bin/bash

# Replace these with your actual Workspace ID and Primary Key
CustomerId="your_workspace_id"
SharedKey="your_primary_key"
</code></pre><p>The script retrieves the computer name using&nbsp;<code>scutil --get ComputerName</code>.</p><p>It then extracts the device serial number using&nbsp;<code>system_profiler SPHardwareDataType</code>&nbsp;and&nbsp;<code>awk</code>&nbsp;to filter the output for the line containing "Serial"</p><pre><code class="language-bash">ComputerName=$(scutil --get ComputerName)
DeviceSerialNumber=$(system_profiler SPHardwareDataType | awk '/Serial/ {print $4}')
</code></pre><p>This section is the heart of application data collection:</p><ul><li>It defines a variable&nbsp;<code>Applications</code>&nbsp;as an opening bracket for a JSON array.</li><li>The script iterates through lines retrieved using&nbsp;<code>system_profiler SPApplicationsDataType</code>.</li><li>It uses conditional statements (<code>if</code>&nbsp;and&nbsp;<code>elif</code>) to identify lines containing "Location:" (indicating app location) and "Version:".</li><li>For "Location:",&nbsp;it extracts the application name using&nbsp;<code>basename</code>&nbsp;to remove the path and ".app" extension.</li><li>For "Version:",&nbsp;it extracts the version number using&nbsp;<code>awk</code>.</li><li>It then constructs a JSON object for each application with details like&nbsp;<code>AppName</code>,&nbsp;<code>AppVersion</code>,&nbsp;<code>ComputerName</code>,&nbsp;and&nbsp;<code>DeviceSerialNumber</code>.</li><li>The loop keeps adding these application objects (separated by commas) to the&nbsp;<code>Applications</code>&nbsp;variable.</li><li>Finally,&nbsp;it removes the trailing comma from the JSON array using&nbsp;<code>sed</code>.</li></ul><pre><code class="language-bash">Applications="["

IFS=$'\n'
for line in $(system_profiler SPApplicationsDataType); do
  if [[ "$line" =~ "Location:" ]]; then
    appName=$(basename "$line" .app)  # Extracts only the app name, removing path and .app extension
  elif [[ "$line" =~ "Version:" ]]; then
    appVersion=$(echo "$line" | awk -F": " '{print $2}')
    Applications+="{\"AppName\": \"$appName\", \"AppVersion\": \"$appVersion\", \"ComputerName\": \"$ComputerName\", \"DeviceSerialNumber\": \"$DeviceSerialNumber\"},"
  fi
done
IFS=$' \t\n'

# JSON format
Applications=$(echo $Applications | sed 's/,\]/\]/')
</code></pre><p>It passes the&nbsp;<code>CustomerId</code>&nbsp;(workspace ID),&nbsp;<code>SharedKey</code>&nbsp;(primary key),&nbsp;the prepared&nbsp;<code>Applications</code>&nbsp;JSON data (containing application details),&nbsp;and a log type identifier ("Mac_app_inventory_CL") for reference within Log Analytics.</p><pre><code class="language-bash"># Send data
send_data "$CustomerId" "$SharedKey" "$Applications" "Mac_app_inventory_CL"</code></pre><p>So, let's put together all the blocks and build our complete script:</p><pre><code class="language-bash">#!/bin/bash

# Replace these with your actual Workspace ID and Primary Key
CustomerId="your_workspace_id"
SharedKey="your_primary_key"

# Function to create the authorization signature
function generate_signature() {
    local customerId="$1"
    local sharedKey="$2"
    local date="$3"
    local contentLength="$4"
    local method="$5"
    local contentType="$6"
    local resource="$7"
    
    local stringToHash="$method\n$contentLength\n$contentType\nx-ms-date:$date\n$resource"
    local decodedKey=$(echo "$sharedKey" | base64 -d | xxd -p -u -c 256)
    local hash=$(echo -ne "$stringToHash" | xxd -p -u -c 256 | xxd -r -p | openssl dgst -sha256 -mac HMAC -macopt hexkey:$decodedKey -binary | base64)
    
    echo "SharedKey $customerId:$hash"
}

# Function to send data to Log Analytics
function send_data() {
    local customerId="$1"
    local sharedKey="$2"
    local data="$3"
    local logType="$4"
    
    local method="POST"
    local contentType="application/json"
    local resource="/api/logs"
    local date=$(date -u +%a,\ %d\ %b\ %Y\ %H:%M:%S\ GMT)
    local contentLength=$(echo -n "$data" | wc -c | tr -d ' ')
    local signature=$(generate_signature "$customerId" "$sharedKey" "$date" "$contentLength" "$method" "$contentType" "$resource")
    local uri="https://$customerId.ods.opinsights.azure.com$resource?api-version=2016-04-01"
    
    response=$(curl --silent --location "$uri" \
         --header "Authorization: $signature" \
         --header "Log-Type: $logType" \
         --header "x-ms-date: $date" \
         --header "Content-Type: $contentType" \
         --data "$data")
    echo "$response"
}

# Main data collection and processing
ComputerName=$(scutil --get ComputerName)
DeviceSerialNumber=$(system_profiler SPHardwareDataType | awk '/Serial/ {print $4}')

# Collecting dynamic application data
Applications="["

appCount=0  # Initialize application count
IFS=$'\n'
for line in $(system_profiler SPApplicationsDataType); do
    if [[ "$line" =~ "Location:" ]]; then
        appName=$(basename "$line" .app)  # Extracts only the app name, removing path and .app extension
    elif [[ "$line" =~ "Version:" ]]; then
        appVersion=$(echo "$line" | awk -F": " '{print $2}')
        Applications+="{\"AppName\": \"$appName\", \"AppVersion\": \"$appVersion\", \"ComputerName\": \"$ComputerName\", \"DeviceSerialNumber\": \"$DeviceSerialNumber\"},"
        ((appCount++))  # Increment application count
    fi
done
IFS=$' \t\n'

# Remove the last comma for JSON format correctness
Applications=$(echo $Applications | sed 's/,\]/\]/')

# Debug output to check everything is captured correctly
echo "Debug: Prepared JSON Data: $Applications"

# Send data
send_data "$CustomerId" "$SharedKey" "$Applications" "Mac_app_inventory_CL"

# Print completion message
echo "Application inventory collected and uploaded to Azure Log Analytics workspace. The total count of apps discovered and uploaded are $appCount."
</code></pre><hr><h3 id="deployment">Deployment:</h3><div class="kg-card kg-callout-card kg-callout-card-red"><div class="kg-callout-emoji">💡</div><div class="kg-callout-text">It is advisable that you run the script locally on a test Mac to see the data before you push it to all production machines!</div></div><p>You need to deploy the script to all your Macs enrolled with Intune. Steps are as below:&nbsp;</p><ul><li>Sign in to the Microsoft Intune admin center.</li><li>Select Devices &gt; macOS &gt; Shell scripts &gt; Add.</li><li>In Basics, enter the required properties, and select Next.</li><li>In Script settings, configure as below and select Next:</li></ul><figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2024/05/image.png" class="kg-image" alt="" loading="lazy" width="1543" height="1660" srcset="__GHOST_URL__/content/images/size/w600/2024/05/image.png 600w, __GHOST_URL__/content/images/size/w1000/2024/05/image.png 1000w, __GHOST_URL__/content/images/2024/05/image.png 1543w" sizes="(min-width: 720px) 720px"></figure><ul><li>Select&nbsp;<strong>Assignments</strong>&nbsp;&gt;&nbsp;<strong>Select groups to include</strong>.&nbsp;</li></ul><hr><h3 id="end-results">End Results</h3><p>Once the script executes successfully, it transmits the collected data to your Azure Log Analytics workspace. This data will be stored in a new table named&nbsp;<strong>Mac_app_inventory_CL </strong>. Within this table, you'll find all the application inventory details gathered by the script from the device.</p><ul><li>Testing locally first on a test machine:</li></ul><figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2024/05/Screenshot-2024-05-06-at-21.28.02.png" class="kg-image" alt="" loading="lazy" width="2000" height="1045" srcset="__GHOST_URL__/content/images/size/w600/2024/05/Screenshot-2024-05-06-at-21.28.02.png 600w, __GHOST_URL__/content/images/size/w1000/2024/05/Screenshot-2024-05-06-at-21.28.02.png 1000w, __GHOST_URL__/content/images/size/w1600/2024/05/Screenshot-2024-05-06-at-21.28.02.png 1600w, __GHOST_URL__/content/images/2024/05/Screenshot-2024-05-06-at-21.28.02.png 2000w" sizes="(min-width: 720px) 720px"></figure><ul><li>Data in Azure Log Analytics Workspace:</li></ul><figure class="kg-card kg-image-card"><img src="__GHOST_URL__/content/images/2024/05/image-1.png" class="kg-image" alt="" loading="lazy" width="2000" height="1218" srcset="__GHOST_URL__/content/images/size/w600/2024/05/image-1.png 600w, __GHOST_URL__/content/images/size/w1000/2024/05/image-1.png 1000w, __GHOST_URL__/content/images/size/w1600/2024/05/image-1.png 1600w, __GHOST_URL__/content/images/2024/05/image-1.png 2276w" sizes="(min-width: 720px) 720px"></figure><hr><h3 id="conclusion"><strong>Conclusion</strong></h3><p>In conclusion, maintaining a comprehensive inventory of applications on Mac endpoints is crucial for several reasons. It enhances visibility into installed applications, aids in security compliance by ensuring all software is up-to-date, and helps IT departments manage resources more effectively. The limitations of standard MDM reporting functionalities often necessitate a more hands-on approach, as demonstrated through the use of our custom script.</p><p>The script not only automates the collection of application data but also seamlessly uploads this inventory to Azure Log Analytics. This integration provides a centralized and accessible location for monitoring and analysis, enabling organizations to make informed decisions based on accurate and up-to-date application usage data.</p><p>It empowers you to overcome the reporting limitations of MDM solutions by providing a deeper insight into the applications installed on your network's endpoints.</p><p><strong>Next Steps:</strong></p><ul><li>Experiment with the script to customize and extend its capabilities according to your organization's specific needs.</li><li>Consider integrating this script into your regular IT audit processes to ensure continuous compliance and security.</li><li>Stay updated with the latest in script automation and endpoint management by subscribing to my blog and following on social media channels.</li></ul>