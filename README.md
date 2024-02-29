# SIEM-Implementation-in-Azure-Cloud

In this guide, we'll dive into deploying a security information and event management (SIEM) solution in Azure Cloud, boosting your hands-on experience. You'll implement advanced techniques to enhance threat detection capabilities, while gaining practical skills in remediation actions to resolve cyber security incidents effectively. From configuring the SIEM to analyzing security events, you'll strengthen your expertise in cyber defense.

## Tools Used

- Azure cloud
- Microsoft Sentinel

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

![image](https://i.imgur.com/HhAeXbU.png)

You can see that it uses user and entity behavior analytics (UEBA) for anomaly detection.

## Part 5: Enable Artificial Intelligence in SIEM

### Step 1: Enabling User and Entity Behavior Analytics (UEBA)

We will be turning on the User and Entity Behavior Analytics (UEBA) feature, which utilizes AI to detect and alert users to any unusual behavior within the system.

*Access the settings section to enable this feature. Navigate to settings and locate the "User and Entity Behavior Analytics" button.*

![image](https://i.imgur.com/wOYcjPd.png)

*Click on "User and Entity Behavior Analytics" and proceed to select "Azure Active Directory," applying it to existing data sources to activate the AI-powered detection capabilities.*

![image](https://i.imgur.com/u3p0AtY.png)

### Step 2: Configuring Automation Playbooks

While in the settings section, we will configure Microsoft Sentinel to use automation playbooks for enhanced operational efficiency.

*Grant permissions to Microsoft Sentinel by navigating back one page and selecting the arrow next to the playbook permission option.*

![image](https://i.imgur.com/DzuKbad.png)

*Choose the resource group where Microsoft Sentinel is deployed and apply the necessary changes to configure permissions effectively.*

![image](https://i.imgur.com/lTl8CdZ.png)

By following these steps, you have successfully enabled UEBA and configured automation playbooks within Microsoft Sentinel, setting the stage for enhanced security monitoring and response capabilities.

## Part 6: Creating a Watchlist to Detect Cybersecurity Threats

### Step 1: Creating a Watchlist for Tor Exit Nodes

*Begin by navigating to the watchlist section in the configuration menu of Microsoft Sentinel.*

![image](https://i.imgur.com/wSncpEe.png)

*Click on "Add New" to create a new watchlist.*

![image](https://i.imgur.com/r3UbeSx.png)

*Provide a name for the watchlist and an alias that is easy to remember and will be used later in analytics rules.*

*You have the option to create the watchlist from a local file or from Azure Storage. I will be using a CSV file of Tor exit nodes for my example.*

*Validate the file preview to ensure correctness, then select a unique search key to optimize query performance.*

*Review the configuration and proceed to create the watchlist. Upon successful validation, create the watchlist, which will be available for immediate use.*

Step 2: Viewing and Modifying Watchlists

*After creating the watchlist, you can view it by selecting it from the watchlist section. Click on "View watchlist logs" to see the watchlist's contents.*

Watchlists are easily modifiable. You can update them by selecting "Update watchlists" and "Edit watchlist items." This feature is particularly useful when multiple analytics rules use the same information, allowing for centralized updates.

## Part 7: Creating a Detection Rule For Cybersecurity Threat

### Step 1: Creating an Analytics Rule to Detect Threats from Tor Network

*Navigate to the configuration section of Microsoft Sentinel and select "Analytics."*

![image](https://i.imgur.com/xOQhBuk.png)

*Choose to add a new scheduled query rule.*

*Provide an appropriate name for the rule, such as "Successful Sign-ins from Tor Network," and specify the relevant tactics and techniques. Adjust the severity level as needed.*

*In the rule logic section, utilize Kql (Kusto Query Language) to specify the criteria for detecting threats.

![image](https://i.imgur.com/LxndNra.png)

*Test the query with current data to evaluate potential alerts generated per day.*

*In the alert enrichment section, map entities such as account (user ID and display name) and IP address (address).*

*Customize alert details by adding fields such as IP address and user account name to the alert name and description.*

*Configure query scheduling to run at specified intervals and look for data within a defined timeframe.*

*Proceed to incident settings, enabling incident creation from alerts and enabling alert grouping to group alerts with matching IP addresses and usernames into the same incident.*

*Review and create the analytics rule, ensuring that all settings are configured correctly.*

Step 2: Testing and Verification

*After creating the analytics rule, search for it in Microsoft Sentinel to confirm its creation.*

![image](https://i.imgur.com/SkA7qQE.png)

*Upon successful creation, proceed to test the rule by creating a new account and signing in from an anonymous IP address, triggering the analytics rule to detect the threat.*

## Part 8: Creating a User Account in Azure for SIEM Investigation

### Step 1: Preparation and Account Creation

Start by disabling security defaults in Azure AD to avoid any potential interruptions.

*Navigate to Azure Active Directory and select "Properties." Scroll down to "Manage Security Defaults" and change the status from enabled to disabled. Provide a reason, such as "testing," and save the changes.*

![image](https://i.imgur.com/poDuBua.png)

*With security defaults disabled, proceed to create a new user account.*

*Navigate to "Users" under "Manage" in Azure AD, then select "Create new user."*

*Enter a user principal name , generate a new password, and enable the account. Fill in basic details such as job title and company name.*

*After completing the user creation process, copy the user principal name and password for future use.*

### Step 2: Role Assignment

*Assign roles to the newly created user.*

*Go back to the user list, select the created user, and click on "Add assignment" under the "Manage" section.*

*Search for roles such as "Security Reader" and "Contributor" for Azure resources.*

![image](https://i.imgur.com/Mc6B1o8.png)

*Assign the appropriate roles, ensuring that the user has the necessary permissions for the intended tasks.*

### Step 3: Logging In and Testing

Log in to the newly created account using the provided credentials. Use a different browser window for distinction.

*Attempt to log in with both a secure and insecure password to observe Microsoft's password policy in action.*

*Access Azure resources and verify that the user has the expected permissions, including access to Azure Active Directory and the designated resource group.*

*Confirm that multi-factor authentication (MFA) is disabled for the account to assess Microsoft Sentinel's detection capabilities.*

By following these steps, you have prepared the environment and created a new user account for testing purposes. Proceed to log in and perform various activities to evaluate Microsoft Sentinel's ability to detect any unusual or potentially malicious behavior.

## Part 9: Infiltrating User Account to Generate Incidents in SIEM

### Step 1: Accessing Azure Portal

Put on the hacker hat and open the Brave browser for anonymity.

*Create a new private window with Tor in the Brave browser.*

*Access the Azure portal and use the credentials of the newly created account to log in.*

![image](https://i.imgur.com/oJT4FI4.png)

### Step 2: Perform Malicious Activities

As an attacker, establish persistence by changing the password. 

*Navigate to the account settings and select "Change password." Provide the old and a new complex password.*

![image](https://i.imgur.com/Fyv1nhi.png)

Another action an attacker might do would be to disable diagnosic settings.

*Disable diagnostic settings in the resource group and Microsoft Sentinel to avoid detection. Delete diagnostic settings for both.*

Consider using the Azure Portal's Web shell interface to run scripts for escalating privileges or performing crypto mining activities.

By following these steps, you can simulate malicious activities and assess Microsoft Sentinel's ability to detect and respond to security threats effectively.

## Part 10: Exploring Created Cybersecurity Incidents in SIEM

Let's dive into investigating incidents.

### Accessing Incidents:

Upon logging in, navigate to the dashboard. Here, you'll notice the number of new incidents displayed.

### Prioritizing Incidents:

To prioritize incidents, focus on those with the highest severity. Click on "Manage incidents" or navigate through the "Threat Management" tab and select "Incidents."

### Analyzing Incidents:

Review the incidents listed in the table. Pay attention to details such as IP addresses and time ranges. Note any anomalies or patterns.

### Understanding Incident Relationships:

Explore related incidents and their commonalities. Understand why multiple incidents occur and their correlation.

### Initiating Investigation:

To start the investigation, select the incidents you want to investigate by checking the boxes. Click on "Action" and assign an owner and status (e.g., Active).

### Establishing Accountability:

Assigning incidents ensures clear accountability within the team. It prevents confusion about who is responsible for resolving each incident.

### Investigating Incidents:

Click on an incident to view a brief description on the right side. Select "View full details" for more information. Begin the investigation process by analyzing the incident details.

## Part 11: How to Investigate Cybersecurity Incidents in SIEM

Now let's dive into the incident investigation process.

![image](https://i.imgur.com/sYnYcuY.png)

### Understanding Incident Details:

The incident window is divided into three sections. On the left side, you'll find essential details about the incident, including a summary and entities involved, such as usernames and IP addresses.

### Accessing Evidence:

You'll also have access to evidence, including events, alerts, and bookmarks. Clicking on any entity will reveal more details. For example, clicking on an event will display results in a new window.

### Analyzing Results:

From the results, you can gather crucial information. For instance, you may discover that a successful login originated from a suspicious IP address, such as one associated with Tor exit nodes.

### Using External Tools:

To further investigate, you might use external tools like abuse.ipdb to check if the IP address is malicious. Simply copy and paste the address into the tool to retrieve relevant reports.

### Refining Query Results:

As you analyze logs, you may notice discrepancies or missing information. Adjust your query parameters to refine the results. For example, removing certain arguments can clarify the event's outcome.

### Exploring User Activity:

Dig deeper into the user's activity to identify patterns or anomalies. You can search for the user's activities within Microsoft Sentinel or through incident investigation. This helps consolidate all user-related activities for better analysis.

### Examining Graphical Representations:

Graphs and timelines provide a visual representation of user activities and alerts. By examining these graphs, you can spot trends or irregularities in the user's behavior.

### Understanding Query Complexity:

Queries may contain multiple lines and combine different tables. Understanding query complexity is essential for interpreting results accurately.

### Reviewing Activity Logs:

Review each activity log thoroughly. Pay attention to operation names, activity statuses, and associated services. This information helps you understand the user's actions within the system.

### Deciding Next Steps:

Based on the evidence gathered, it's time to decide on the next course of action. Consider factors like the user's role, department, and the severity of the incident. In some cases, disabling the account may be necessary to prevent further damage.
