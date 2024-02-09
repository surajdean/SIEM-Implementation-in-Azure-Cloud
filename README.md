# SIEM-Implementation-in-Azure-Cloud

In this guide, fill in later

## Tools Used

- Azure cloud
- PuTTy
- VirtualBox
- T-Pot

## Environments Used

- Windows 10 VM

## Part 1: Setup Lab Resources

Step 1: Prepare for Deployment

    Ensure you have a free Azure subscription for deploying Microsoft Sentinel.
    If you don't have an Azure account, register for one using the provided link.
    Access the official GitHub repository for Sentinel all-in-one deployment provided in the resources.

Step 2: Understanding Sentinel All-in-One

    Sentinel all-in-one is an official Microsoft solution designed to expedite the deployment process of Microsoft Sentinel.
    Version two, released in April 2023, streamlines initial configuration tasks for Sentinel.
    While manual configuration of Microsoft Sentinel is an option, this solution simplifies and accelerates the process significantly.
    The deployment option encompasses various features, including workspace retention settings, daily cap, commitment tiers, user and entity behavior analytics, and health diagnostics for analytics rules and data connectors.

Step 3: Exploring Features

    Content Hub solutions provided within the deployment offer pre-configured packages of analytics, rules, dashboards, and automation tasks specific to Microsoft Sentinel.
    Data connectors from sources such as Azure Active Directory and Microsoft 365 Defender are enabled, facilitating immediate data ingestion from diverse sources.
    Analytics rules utilizing selected data connectors with severity filtering are also activated.

Step 4: Deploying Microsoft Sentinel

    Navigate to the deployment option provided in the GitHub repository.
    Review the supported connectors listed, ensuring compatibility with your requirements.
    Note that some connectors may require licenses, but this deployment project is entirely free.
    Microsoft Sentinel offers ten gigabytes of free data ingestion per day for the first month, providing ample time to familiarize yourself with the platform.
    Deploy Microsoft Sentinel to your Azure environment following the instructions provided in the repository.

Step 5: Post-Deployment Considerations

    Once Microsoft Sentinel is deployed and configured, explore its functionalities and capabilities.
    Take advantage of the pre-configured analytics rules, dashboards, and automation tasks provided by Content Hub solutions.
    In case of any questions or issues during deployment or usage, refer to the resources provided in the GitHub repository or seek assistance from Microsoft support.

By following these steps, you'll be able to efficiently deploy Microsoft Sentinel using the all-in-one solution, leveraging its features for enhanced threat detection and response capabilities within your Azure environment.

## Part 2: Create SIEM in Azure Cloud

Step 1: Deploying Microsoft Sentinel

    Click on the "Deploy to Azure" button to initiate the deployment process for Microsoft Sentinel.
    This action redirects you to the Azure portal, where you'll deploy Microsoft Sentinel using a predefined template.

Step 2: Selecting Location and Configuration

    Choose the location for deployment, considering factors such as regulatory requirements and cost implications.
    Opt for a location closest to your operational area. For example, North Europe.
    Define the resource group and workspace name, ensuring they reflect the purpose of the solution. For this demonstration, name it "Security Monitoring."

Step 3: Setting Ingestion Limits and Data Retention

    Determine the daily ingestion limit in gigabytes. Since there's a ten-gigabyte free daily limit, input ten in this field.
    Retain the default data retention period of 90 days, during which Microsoft stores data for free.

Step 4: Configuring Settings

    Enable Sentinel Health Diagnostics under Settings to monitor the health of Microsoft Sentinel.
    Optionally enable artificial intelligence and user/entity behavior analytics for advanced threat detection.

Step 5: Exploring Content Hub and Data Connectors

    Explore the Content Hub, which offers pre-configured solutions categorized into three sections.
    Select all solutions within each category for comprehensive monitoring.
    Choose data connectors based on your data sources, prioritizing Azure Active Directory for sign-in data.
    Even if lacking licenses, select all data connectors for future scalability.

Step 6: Enabling Analytics Rules

    Check the box to enable analytics rules, which automate threat detection.
    Select severity levels such as low and information to encompass all threat categories.

Step 7: Review and Deployment

    Review your settings to ensure they align with your requirements.
    Proceed to create Microsoft Sentinel once validation passes.
    Expect the deployment to take 10 to 15 minutes.
    During deployment, you may encounter failures for specific connectors due to licensing constraints. However, this won't impact the overall functionality.
    After deployment, explore your newly deployed Microsoft Sentinel together to understand its capabilities and available artifacts.

By following these steps, you'll effectively deploy Microsoft Sentinel, enabling robust security monitoring within your Azure environment.

## Part 3: Exploring Deployed Cybersecurity Artifacts

## Part 4: Exploring Created Cloud SIEM Solution

## Part 5: Enable Artificial Intelligence in SIEM

## Part 6: Creating a Watchilist to Detect cybersecurity Threats

## Part 7: Creating a Detection Rule For Cybersecruity Threat

## Part 8: Creating a User Account in Azure for SIEM Investigation

## Part 9: Infiltrating User Account to Generate Incidents in SIEM

## Part 10: Exploring Created Cybersecurity Incidents in SIEM

## Part 11: How to Investigate Cybersecurity Incidents in SIEM

## Part 12: How to Remediate Cybersecuirty Incident
