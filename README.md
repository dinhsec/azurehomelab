# Azure Cloud Detection & Analysis Home Lab

The purpose of this Azure Cloud Detection and Analysis Home Lab is to provide hands-on experience in working with Azure to configure and deploy Azure services and resources such as Virtual Machines, Azure Sentinel, and Log Analytics Workspace. The goal is to gain practical knowledge in implementing security best practices for virtual machine and network security, as well as utilizing Sentinel data connectors to forward data for analysis. Additionally, this lab provides an opportunity to explore and learn about Windows security event logs, configure security policies, utilize KQL to query logs, write custom analytic rules, and use pre-made analytic rules to detect and alert security events. The MITRE ATT&CK framework will also be utilized to map adversarial tactics, techniques, and procedures and add detection and mitigation procedures to ensure robust security measures for Azure cloud deployments.

## Setup

The first step is to login to the Azure Portal.

If you do not have an account you can sign up for a free Azure account using this link:
https://azure.microsoft.com/en-us/free/

From there we will need to navigate to the resource groups tab.

A resource group is a container that holds related resources for an Azure solution. The purpose of Azure groups are to group and manage related Azure resources together, which simplifies management, deployment, controlling access, tracking costs, and enabling disaster recovery.

![image](https://user-images.githubusercontent.com/118394420/221387177-f3f94133-72ef-4fb3-a131-ddf261530c35.png)

Then click on Create to create a resource group

![image](https://user-images.githubusercontent.com/118394420/221387262-11cdfb2f-852c-4db4-a3cd-5709117d0eec.png)

Add a name for your resource group, I will be naming it homelabrg

![image](https://user-images.githubusercontent.com/118394420/221387271-60f4a1f6-1965-4349-8bdd-df2a7a3b1ec7.png)

Then click on review + create and create your resource group.

![image](https://user-images.githubusercontent.com/118394420/221387348-3353f52b-06c8-4d40-b9a1-200df9001dff.png)
