# SIEM-Implementation-in-Azure-Cloud

In this guide, we'll dive into deploying a security information and event management (SIEM) solution in Azure Cloud, boosting your hands-on experience. You'll implement advanced techniques to enhance threat detection capabilities, while gaining practical skills in remediation actions to resolve cyber security incidents effectively. From configuring the SIEM to analyzing security events, you'll strengthen your expertise in cyber defense. Get ready to elevate your cybersecurity skills and tackle real-world challenges head-on!

## Tools Used

- Azure cloud
- Microsoft Sentinel

## Environments Used

- 

## Part 1: Setup Lab Resources

Ensure you have a free Azure subscription for deploying Microsoft Sentinel.

If you don't have an Azure account, register [here](https://azure.microsoft.com/en-us/free/).

We will be using Microsoft Sentinel All-in-One for this project.

Sentinel all-in-one is an official Microsoft solution designed to expedite the deployment process of Microsoft Sentinel.

hile manual configuration of Microsoft Sentinel is an option, this solution simplifies and accelerates the process significantly.

The deployment option encompasses various features, including workspace retention settings, daily cap, commitment tiers, user and entity behavior analytics, and health diagnostics for analytics rules and data connectors.

*Access the official GitHub repository for Sentinel All-in-One deployment [here](https://github.com/Azure/Azure-Sentinel/tree/master/Tools/Sentinel-All-In-One)*

*In case of any questions or issues during deployment or usage, refer to the resources provided in the GitHub repository or seek assistance from Microsoft support.*

## Part 2: Create SIEM in Azure Cloud

### Step 1: Deploying Microsoft Sentinel

*Click on the "Deploy to Azure" button to initiate the deployment process for Microsoft Sentinel.*

![image](https://i.imgur.com/vfXaCSc.png)

This action redirects you to the Azure portal, where you'll deploy Microsoft Sentinel using a predefined template.

### Step 2: Selecting Location and Configuration

*Choose the location for deployment, considering factors such as regulatory requirements and cost implications.  Opt for a location closest to your operational area.*

*Define the resource group and workspace name, ensuring they reflect the purpose of the solution. For this demonstration, name it "Security Monitoring."*

### Step 3: Setting Ingestion Limits and Data Retention

*Determine the daily ingestion limit in gigabytes. Since there's a ten-gigabyte free daily limit, input ten in this field.*

*Retain the default data retention period of 90 days, during which Microsoft stores data for free.*

### Step 4: Configuring Settings

*Enable Sentinel Health Diagnostics under Settings to monitor the health of Microsoft Sentinel.*

![image](https://i.imgur.com/it8ZWag.png)

*Optionally enable artificial intelligence and user/entity behavior analytics for advanced threat detection.*

### Step 5: Exploring Content Hub and Data Connectors

*Explore the Content Hub, which offers pre-configured solutions categorized into three sections.*

*Select all solutions within each category for comprehensive monitoring.*

![image](https://i.imgur.com/0rcwc3m.png)

*Choose data connectors based on your data sources, prioritizing Azure Active Directory for sign-in data.*

![image](https://i.imgur.com/WnNLq6Q.png)

*Even if lacking licenses, select all data connectors for future scalability.*

### Step 6: Enabling Analytics Rules

*Check the box to enable analytics rules, which automate threat detection.*

*Select severity levels such as low and information to encompass all threat categories.*

![image](https://i.imgur.com/AhhuBIw.png)

### Step 7: Review and Deployment

*Review your settings to ensure they align with your requirements.*

*Proceed to create Microsoft Sentinel once validation passes.*

During deployment, you may encounter failures for specific connectors due to licensing constraints. However, this won't impact the overall functionality.

## Part 3: Exploring Deployed Cybersecurity Artifacts

### Step 1: Identifying the Deployment Error

*Despite successful deployment, an error related to data connectors requiring a license has been encountered.*

*Assure that other aspects of the deployment are correctly configured.*

### Step 2: Accessing the Resource Group

*Navigate to the Azure portal and search for "resource groups."*

![image](https://i.imgur.com/P775AoI.png)

*Select the resource group where Microsoft Sentinel was deployed, typically named according to its purpose, such as "monitoring"*

### Step 3: Reviewing Resource Group Contents

*Within the resource group, observe over 300 records comprising various services.*

![image](https://i.imgur.com/0afPhlV.png)

*Key components include container instances, storage accounts, API connections, deployment scripts, and crucially, the log analytics workspace where all data is stored.*

### Step 4: Exploring Templates

Explore a template to understand its contents by clicking on it and selecting "Deploy."

Templates typically consist of display names and descriptions, such as "Threat Intelligence Analytics Rule template 35."

Recognize that deploying numerous templates manually can be time-consuming, underscoring the importance of automation.

### Step 5: Understanding Log Analytics Workspace

Acknowledge that Microsoft Sentinel operates atop the log analytics workspace.

Monitoring the workspace is essential for detecting issues like query performance or execution errors.

Locate the log analytics workspace within the resource group and proceed.

### Step 6: Configuring Diagnostic Settings

*Within the log analytics workspace, navigate to the monitoring section and select "Diagnostic settings."*

*Create a new diagnostic setting with a descriptive name like "Sentinel."*

*Choose to collect all logs and metrics.*

![image](https://i.imgur.com/Xpc5Hqo.png)

*Specify the destination as the log analytics workspace associated with Sentinel and save the settings.*

## Part 4: Exploring Created Cloud SIEM Solution

### Step 1: Accessing Microsoft Sentinel

*Proceed to Microsoft Sentinel by searching for it in the search bar*

![image](https://i.imgur.com/t4xXh5F.png)

Upon arrival at the overview section, gain insight into basic information about Microsoft Sentinel.

Utilize the left-hand menu, categorized into four sections: General, Management, Content Management, and Configuration.

### Step 2: Exploring Logs

*Navigate to the "Logs" tab to search for data using the Kusto Query Language (KQL).*

![image](https://i.imgur.com/FqvqMWW.png)

Data is organized into various tables, accessible by clicking the triangle icon.

*Note that some tables may not yet be present due to incomplete data ingestion.*

Explore tables such as Azure Activity and Interactive User Sign-Ins, providing insights into portal actions and authentication details.

### Step 3: Understanding Data Connectors

*Navigate to the "Data connectors" section"

![image](https://i.imgur.com/glYTS2e.png)

*Observe the status of data connectors, typically ranging from 9 to 10 connected connectors.*

*Filter connectors by status to view all data sources linked to Microsoft Sentinel.*

*Click on each connector for detailed information, including data type, log count, and populated tables.*

![image](https://i.imgur.com/UXepV1a.png)

### Step 4: Analyzing Analytics

*Navigate to the "Analytics" tab, where the core detection rules are implemented.*

![image](https://i.imgur.com/UEJrIlI.png)

Benefit from the deployment of 339 detection rules, aiding in threat monitoring and detection.

Review examples of detection rules, such as network port sweeps and suspicious application content.

### Step 5: Addressing Anomalies

*Explore the "Anomalies" section, where robust anomaly detection templates are employed.*

![image]()

*Recognize the use of user and entity behavior analytics (UEBA) for anomaly detection.*

*Prepare to address any anomalies and fine-tune thresholds to minimize false positives.*

![image]()

*Note the current issue with UEBA and prioritize resolving it as the initial task within Microsoft Sentinel.*

## Part 5: Enable Artificial Intelligence in SIEM

### Step 1: Enabling User and Entity Behavior Analytics (UEBA)

*Begin by exploring the User and Entity Behavior Analytics (UEBA) feature, which utilizes AI to detect and alert users to any unusual behavior within the system.*

*Access the settings section to enable this feature. Navigate to settings and locate the "User and Entity Behavior Analytics" button.*

*Click on "User and Entity Behavior Analytics" and proceed to select "Azure Active Directory," applying it to existing data sources to activate the AI-powered detection capabilities.*

### Step 2: Configuring Automation Playbooks

*While in the settings section, configure Microsoft Sentinel to use automation playbooks for enhanced operational efficiency.*

*Grant permissions to Microsoft Sentinel by navigating back one page and selecting the arrow next to the playbook permission option.*

*Choose the resource group where Microsoft Sentinel is deployed and apply the necessary changes to configure permissions effectively.*

### Step 3: Finalizing Setup

*With UEBA enabled and automation playbooks configured, Microsoft Sentinel is now equipped with powerful capabilities.*

*Prepare to create impactful artifacts within Microsoft Sentinel to enhance security operations and streamline workflows.*

By following these steps, you have successfully enabled UEBA and configured automation playbooks within Microsoft Sentinel, setting the stage for enhanced security monitoring and response capabilities. Stay tuned for the next video, where you'll delve into the creation and utilization of watchlists to further bolster your security operations.

## Part 6: Creating a Watchlist to Detect Cybersecurity Threats

### Step 1: Creating a Watchlist for Tor Exit Nodes

*Begin by navigating to the watchlist section in the configuration menu of Microsoft Sentinel.*

*Click on "Add New" to create a new watchlist.*

*Provide a name for the watchlist, such as "Tor Exit Nodes," and an alias that is easy to remember and will be used later in analytics rules.*

*You have the option to create the watchlist from a local file or from Azure Storage. Download the prepared CSV file containing all the Tor exit node IP addresses and drag it into the appropriate field.*

*Validate the file preview to ensure correctness, then select a unique search key to optimize query performance.*

*Review the configuration and proceed to create the watchlist. Upon successful validation, create the watchlist, which will be available for immediate use.*

Step 2: Viewing and Modifying Watchlists

*After creating the watchlist, you can view it by selecting it from the watchlist section. Click on "View watchlist logs" to see the watchlist's contents presented in a SQL query syntax format.*

*Watchlists are easily modifiable. You can update them by selecting "Update watchlists" and "Edit watchlist items." This feature is particularly useful when multiple analytics rules use the same information, allowing for centralized updates.*

Step 3: Moving Forward

*With the watchlist for Tor exit nodes created and functional, the next step is to create an analytics rule to detect threats originating from the Tor network.*

*Stay tuned for the next section, where we will dive into creating our first analytics rule to enhance threat detection capabilities within Microsoft Sentinel.*

By following these steps, you have successfully created a watchlist for monitoring Tor exit nodes in Microsoft Sentinel, setting the stage for proactive threat detection and response. Stay tuned for the next video, where we'll continue to strengthen your security operations with analytics rules.

## Part 7: Creating a Detection Rule For Cybersecurity Threat

### Step 1: Creating an Analytics Rule to Detect Threats from Tor Network

*Navigate to the configuration section of Microsoft Sentinel and select "Analytics."*

*Choose to add a new scheduled query rule.*

*Provide an appropriate name for the rule, such as "Successful Sign-ins from Tor Network," and specify the relevant tactics and techniques. Adjust the severity level as needed.*

*In the rule logic section, utilize Kql (Kusto Query Language) to specify the criteria for detecting threats. Begin by calling the watchlist function to retrieve a list of IP addresses.*

*Specify the table to be used for data retrieval, such as the signing log table, which contains all signing events.

*Refine the query to filter results based on the IP address field and include only matches found in the watchlist.*

*Further filter results for failed logins and customize the columns to display using the project argument.*

*Test the query with current data to evaluate potential alerts generated per day.*

*In the alert enrichment section, map entities such as account (user ID and display name) and IP address (address).*

*Customize alert details by adding fields such as IP address and user account name to the alert name and description.*

*Configure query scheduling to run at specified intervals and look for data within a defined timeframe.*

*Proceed to incident settings, enabling incident creation from alerts and enabling alert grouping to group alerts with matching IP addresses and usernames into the same incident.*

*Review and create the analytics rule, ensuring that all settings are configured correctly.*

Step 2: Testing and Verification

*After creating the analytics rule, search for it in Microsoft Sentinel to confirm its creation.*

*Upon successful creation, proceed to test the rule by creating a new account and signing in from an anonymous IP address, triggering the analytics rule to detect the threat.*

By following these steps, you have successfully created an analytics rule in Microsoft Sentinel to detect threats originating from the Tor network. Stay tuned for the next video, where we'll test the rule and explore its effectiveness in threat detection.

## Part 8: Creating a User Account in Azure for SIEM Investigation

### Step 1: Preparation and Account Creation

*Start by disabling security defaults in Azure AD to avoid any potential interruptions.*

*Navigate to Azure Active Directory and select "Properties." Scroll down to "Manage Security Defaults" and change the status from enabled to disabled. Provide a reason, such as "testing," and save the changes.*

*With security defaults disabled, proceed to create a new user account.*

*Navigate to "Users" under "Manage" in Azure AD, then select "Create new user."*

*Enter a user principal name (e.g., Ozai), generate a new password, and enable the account. Fill in basic details such as job title and company name.*

*After completing the user creation process, copy the user principal name and password for future use.*

### Step 2: Role Assignment

*Assign roles to the newly created user.*
*Go back to the user list, select the created user, and click on "Add assignment" under the "Manage" section.*
*Search for roles such as "Security Reader" and "Contributor" for Azure resources.*

*Assign the appropriate roles, ensuring that the user has the necessary permissions for the intended tasks.*

Step 3: Logging In and Testing

*Log in to the newly created account using the provided credentials. Use a different browser window for distinction.*

*Attempt to log in with both a secure and insecure password to observe Microsoft's password policy in action.*

*Access Azure resources and verify that the user has the expected permissions, including access to Azure Active Directory and the designated resource group.*

*Confirm that multi-factor authentication (MFA) is disabled for the account to assess Microsoft Sentinel's detection capabilities.*

By following these steps, you have prepared the environment and created a new user account for testing purposes. Proceed to log in and perform various activities to evaluate Microsoft Sentinel's ability to detect any unusual or potentially malicious behavior.

## Part 9: Infiltrating User Account to Generate Incidents in SIEM

### Step 1: Accessing Azure Portal

*Put on the hacker hat and open the Brave browser for anonymity.*

*Create a new private window with Tor in the Brave browser.*

*Access the Azure portal and use the credentials of the newly created account to log in.*

### Step 2: Perform Malicious Activities

*As an attacker, establish persistence by changing the password. Navigate to the account settings and select "Change password." Provide the old and a new complex password.*

*Disable diagnostic settings in the resource group and Microsoft Sentinel to avoid detection. Delete diagnostic settings for both.*

*Attempt to tamper with auditing and health monitoring settings in Microsoft Sentinel. Try clicking on "Configure" to access settings.*

*Consider using the Azure Portal's Web shell interface to run scripts for escalating privileges or performing crypto mining activities.*

*Optionally, create a virtual machine (VM) for generating additional logs in the environment. Choose a generic name to conceal actions.*

### Step 3: Accessing Cloud Shell

*Click on the Cloud Shell button and select PowerShell.*

*Attempt to create a new storage account to store files and scripts. Use existing resource groups if necessary.*

### Step 4: Wait for Detection

*After performing malicious activities, wait for Microsoft Sentinel to detect threats. Detection rules run every five minutes.*

*Take a break and return later to explore newly created incidents in Microsoft Sentinel.*

*Prepare to respond to detected threats effectively in the next steps.*

By following these steps, you can simulate malicious activities and assess Microsoft Sentinel's ability to detect and respond to security threats effectively.

## Part 10: Exploring Created Cybersecurity Incidents in SIEM

Investigating Incidents in Microsoft Sentinel

Accessing Incidents Dashboard:

Open Microsoft Sentinel.
Observe that there are 17 new incidents in the dashboard.
Note that the incidents are in the "New" state, indicating that no one is currently working on them.
Choose to manage incidents or navigate through the threat management tab to access incidents.

Prioritizing Incidents:

Prioritize incidents based on severity, with a focus on those with the highest severity.
For example, prioritize incidents related to successful sign-ins from the Tor network due to their potential impact.

Reviewing Incident Details:

Observe that incidents include various types of security alerts, such as user account creation without expected attributes, service principal authentication attempts from new countries, anomalous single-factor sign-ins, etc.
Investigate each incident to understand its nature and potential correlation with others.

Identifying Correlation Issues:

Note that incidents lack entities, which hinders correlation and consolidation of related alerts.
Understand that proper entity configuration is crucial for effective incident correlation.

Starting the Investigation:

Select multiple incidents for investigation by clicking on the checkbox next to each incident.
Click on "Action" and assign the incidents to yourself, changing their status to "Active" to initiate investigation.
Establish accountability by ensuring clear ownership of each incident.

Initiating Investigation Process:

Click on any selected incident to view its brief description.
Choose to view full details to access comprehensive information about the incident, including affected entities, timestamps, and severity.

By following these steps, you can effectively navigate and investigate incidents in Microsoft Sentinel, ensuring prompt response and resolution to potential security threats.

## Part 11: How to Investigate Cybersecurity Incidents in SIEM

Investigating Incidents in Microsoft Sentinel

Incident Overview:

The incident window is divided into three sections.
On the left side, essential details about the incident are displayed, including a brief summary and information about the entities involved, such as the username and IP address.

Accessing Evidence:

Evidence includes events, alerts, and bookmarks related to the incident.
Clicking on any entity reveals more details. For example, clicking on events reveals specific events related to the incident.

Verifying IP Address:

Copy the IP address associated with the incident and check it using a freely available service like Abuse IPDB.
Confirm that the IP address is related to Tor exit nodes and view relevant reports.

Adjusting Query for Result Type:

Notice that the log doesn't indicate a successful login due to a flaw in the query.
Remove the project argument from the query to display the result type.
Confirm that the login was successful.

Analyzing User Login History:

Adjust the query to check the user's login history for the past week.
Examine the login locations and identify any anomalies, such as logins from different countries or Tor exit nodes.

Investigating User Activities:

Explore other activities related to the user, such as role assignments and Azure activity.
Use the entity behavior section to search for and select the user to view all activities in one place.

Reviewing Azure Activity Logs:

Analyze Azure activity logs to understand the user's actions, such as attempts to delete resource diagnostic settings and create storage accounts.
Identify successful and unsuccessful actions performed by the user.

Deciding Next Actions:

Consider the user's department and role responsibilities to determine if the activities are suspicious.
Decide to disable the account to prevent further unauthorized access and lateral movement.

By following these steps, you can thoroughly investigate incidents in Microsoft Sentinel and take appropriate actions to secure your system.

## Part 12: How to Remediate Cybersecurity Incident

Securing Your Azure Environment

Disabling Compromised Account:

Access Azure Active Directory and navigate to the users section.
Locate the compromised account by its acronym (e.g., O.C.).
Click on the account and choose the option to edit.
Uncheck the "enable" status and save the changes to disable the account.

Deleting Virtual Machine:

Search for virtual machines in Azure.
Locate the VM that poses a threat and delete the resource.

Enabling Diagnostic Settings:

Search for a log analytics workspace and select the instance.
Add diagnostic settings to enable logging for all relevant logs.
Set the destination as the log analytics workspace for Microsoft Sentinel and save the changes.

Enabling Auditing and Health Monitoring in Sentinel:

Access Microsoft Sentinel from the dashboard and navigate to settings.
Enable auditing and health monitoring to ensure comprehensive monitoring of the environment.

Closing Incidents:

Close all incidents assigned for investigation.
Select the incidents, click on actions, and change the status to closed.
Choose the appropriate classification reason (e.g., true positive, suspicious activity).
Add a comment summarizing the findings and actions taken before applying the changes.

By following these steps, you have effectively identified and remediated a threat within your Azure environment using Microsoft Sentinel. Adding comments to incidents and maintaining a record of findings is essential for future investigations and knowledge sharing among analysts. Closing incidents ensures that all identified threats are properly addressed and mitigated.
