# Azure Cloud Detection & Analysis Home Lab

The purpose of this Azure Cloud Detection and Analysis Home Lab is to provide hands-on experience in working with Azure to configure and deploy Azure services and resources such as Virtual Machines, Azure Sentinel, and Log Analytics Workspace. The goal is to gain practical knowledge in implementing security best practices for virtual machine and network security, as well as utilizing Sentinel data connectors to forward data for analysis. Additionally, this lab provides an opportunity to explore and learn about Windows security event logs, configure security policies, utilize KQL to query logs, write custom analytic rules, and use pre-made analytic rules to detect and alert security events. The MITRE ATT&CK framework will also be utilized to map adversarial tactics, techniques, and procedures and add detection and mitigation procedures to ensure robust security measures for Azure cloud deployments.

## Setup

The first step is to login to the Azure Portal

If you do not have an account you can sign up for a free Azure account using this link:
https://azure.microsoft.com/en-us/free/

### Setup Of Lab Resources
From there we will need to navigate to the resource groups tab

A resource group is a container that holds related resources for an Azure solution. The purpose of Azure groups are to group and manage related Azure resources together, which simplifies management, deployment, controlling access, tracking costs, and enabling disaster recovery

![image](https://user-images.githubusercontent.com/118394420/221387177-f3f94133-72ef-4fb3-a131-ddf261530c35.png)

Then click on Create to create a resource group

![image](https://user-images.githubusercontent.com/118394420/221387262-11cdfb2f-852c-4db4-a3cd-5709117d0eec.png)

Add a name for your resource group, I will be naming it homelabrg

![image](https://user-images.githubusercontent.com/118394420/221387271-60f4a1f6-1965-4349-8bdd-df2a7a3b1ec7.png)

Then click on review + create and create your resource group

![image](https://user-images.githubusercontent.com/118394420/221387348-3353f52b-06c8-4d40-b9a1-200df9001dff.png)

Then navigate to the virtual machines service page and create an Azure virtual machine

![image](https://user-images.githubusercontent.com/118394420/221387476-4ae4d703-99c7-46a5-ba0b-5bf7269149a5.png)

Click on the drop down button for the Resource group and select homelabrg to link the VM to our resource group and specify a VM name, make sure the image is Windows 10 Pro

![image](https://user-images.githubusercontent.com/118394420/221387598-a5fdbb43-0b31-48f1-bede-fd3c6f345200.png)

Then specify a username and password for the Administrator account leave the RDP ports default and then click the review + create button

![image](https://user-images.githubusercontent.com/118394420/221387662-1c6c6917-c1ac-4c3c-8698-988b5c3e9b5f.png)

Click the create button to create our VM and wait for the deployment to complete

![image](https://user-images.githubusercontent.com/118394420/221387733-732c8c95-61ee-4ac9-86a1-c1f3d071ff4b.png)

Once its deployed, click on the go to resource button to view the VM details

![image](https://user-images.githubusercontent.com/118394420/221387801-eb62fadb-fab1-49fa-ae92-65ec53022b47.png)

Note the Public IP address on the right side is what we will use to connect to our VM via RDP later on
Then click on the Networking tab on the left side to view our network security group, here we can see our inbound port rules, outbound portrules, etc

![image](https://user-images.githubusercontent.com/118394420/221387829-77d58a37-4848-4871-bdc9-23e900100f76.png)

Note the first rule named "RDP", what this rule is saying is that it will allow any source to connect via RDP to our VM. This is dangerous because an adversary scan and obtain the IP address of our VM making our VM vulnerable to brute-force or password spraying attacks.

To protect our VM from this vulnerability we can utilize something called Just In Time Access.

Navigate to the Microsoft Defender for Cloud service page.

![image](https://user-images.githubusercontent.com/118394420/221388084-51f634b3-eb6d-48c8-be16-15a82d77bc58.png)

Click on our labgroupvm under "Select workspaces to protect..." and click on the Enable all button and press save to enable to Microsoft Defender plan.

![image](https://user-images.githubusercontent.com/118394420/221388125-ec48cb22-a968-4e5a-9e7f-5767afc91994.png)

Then navigate to the Workload protections tab, this shows security alerts, overall security posture, vulnerability assessment, and threat intelligence.

![image](https://user-images.githubusercontent.com/118394420/221388240-e206172c-a184-4f72-b38f-017a179f2bd4.png)
