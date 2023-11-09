# test-cl-docs

---
sidebar_position: 6
slug: /Admin/OnboardingDocs/OnboardingVMbasedARMTemplate
---
# Onboarding Template for VM based Labs 


| SL No | Markdown               |
|-------|------------------------|
| 1     | # Heading level 1      |
| 2     | ## Heading level 2     |
| 3     | ### Heading level 3    |
| 4     | #### Heading level 4   |
| 5     | ##### Heading level 5  |
| 6     | ###### Heading level 6 |

To render an image in web, use the image URL: ![Azure Datacenter](https://azure.microsoft.com/en-us/blog/wp-content/uploads/2022/03/acdf7d3b-44b6-4095-bee0-376c1014eccb.webp)


a
> b

c











[demo](https://google.com){:target="_blank"}

### Overview

In this document you will be provided with end-to-end guidance on creating the CloudLabs Template for VM based labs through the CloudLabs Admin Portal.

In this document you will be going through with the below topics:

  - [Adding CloudLabs Template](#add-template)

  - [Creating & Adding ARM Template](#arm-template)

  - [MS Cloud License](#ms-cloud-licenses)

  - [Virtual Machine Configuration](#virtual-machine-configuration)

### Add Template

1. Navigate to **Templates** _(1)_ section that is available in the left menu and click on **+ ADD** _(2)_ button given in the top right corner.
 
  ![](/img/LabDeveloper/onboardingTemplate-add-cloudlabs-temlate.png)

2. For your convenience, this page is divided into **three** sections:

  A. The fields and their functionality are listed below:

   * **Name:** Provide the Lab or Event name for which you are creating the template to identify the template easily once it is created.
   
   * **Cloud Platform:** CloudLabs supports three cloud platforms -  **Microsoft Azure, Amazon Web Services & Google Cloud Platform**. Based on the current requirement choose **Microsoft Azure** as your Cloud Platform.
  
   * **Cloud Resource Usage:** This feature helps the system in calculating the usage of a Virtual Machine or all Cloud resources. You can select any option from the drop-down menu, but we recommend selecting **Cloud Resource Usage**.
  
   * **Code:** Use a code as an internal identifier; this code will also be concatenated in the name of the user Resource Group. As an example, if you use the code **demolab**, you'll be able to tell that the template is about a demo lab. The user's Resource Group will be named ODL-**demolab**-XXXXXX, where **demolab** is a lab code, **ODL** is the default prefix, and **xxxxx** is the CloudLabs-assigned user unique ID.
  
   * **Lab Code:** Leave it as default.

   * **Subscription Type:** Choose **Shared Subscription** as your Subscription Type from the dropdown.

   * **Description:** Provide a brief description to describe your lab, its resources and technologies as well as its learnings and benefits. It will be visible to the end users as well.
  
   * **Lab Launch Page Description:** Lab Launch page description is visible when you launch your lab environment. You can add any initial instructions to this page that you think are relevant for the users.

   ![](/img/LabDeveloper/image2.png)

  B. Moving on to next section, we will learn about the fields listed below:

   * **Custom Page Title:** In case you want to customize the title of the Hands-on Lab Registration page, you can provide a title in this field.
  
   * **Custom Logo URL:** If you want to customize the logo of the Hands-on Lab Registration page, you can provide the URL of the logo in this field.

   > **Note:** The default page title and logo will be displayed, but if you wish to change them, you can use this field. End-users will be able to see it on the Hands-on Lab registration page, allowing you to customize what you want them to see.

   * **Owner Email:** In this field you have to provide Email address of the person who is buildling/maintaining the Template.
  
   * **Reviewed By:** This field can be used to have reviewer information who will be reviewing the template configurations. 
  
   * **Deployment Plan:** This allows you to choose a number of Resource Groups required in your lab. The selected number of Resource Groups will be pre-created in your environment. To onboard a VM based lab, please select Single Resource group.
  
   * **Lab Guide URL:** A lab guide is a document that gives users all of the directions they need to complete a hands-on lab. The Lab guide URL can be provided here, and it will appear on the users' lab details page. The lab guide will be available to them once they have accessed the URL.
  
   * **Demo URL:** If you want to provide the users with some samples or quickstarts files for the lab, you can provide the file URL here.

   * **Help Document URL:** If you would like to provide users with a help manual that will assist them in completing the lab, you can place that document URL here. 
  
   * **Prerequisites URL:** If you wish to give people visibility into how the lab is set up or how the pre-requisites for the lab are defined, you may write a document and provide the URL here.
  
   > **Note** To allow the URLs to be entered here, all documents should be in GitHub Markdown or PDF format. The users will be able to access these documents just by clicking on the URLs.

   * **Usage Policy URL:** Usage policy is used to monitor cores/clusters of Azure resources. In the policy, we have to define a maximum limit of cores/clusters that is allowed for a user. Since we don't require Usage policy in VM based labs, you can leave it blank.

   * **Github Master Document URL:** This is a JSON-formatted document that is used to arrange the lab guide to a coherent way. We should first prepare the document in JSON format, with section-by-section raw GitHub URLs, as it only supports GitHub raw URLs. Once the document is complete, you can upload it to an Azure blob storage account and use the blob storage URL as directed here.

The URL is included here for a reason. We have a feature named _**Enable VM Access Over Http**_ which allows you to access the VM via browser. When your lab is ready, the environment you receive includes a VM on the left side of the browser and the Lab Guide on the right as shown below:

  ![](/img/LabDeveloper/image19.png)

For a successful setup of both the VM and the Lab Guide, we have some configurations to be done. In the next sections, we will learn more about _Enable VM Access Over Http_ feature (involves the setup of VM) and for now, we will focus on the Master document that involves Lab guide setup.

A master document contains the following information:

1. **Name:** Here you have to provide a name of your Lab.
2. **Language:** English
3. **Files:** In this section, you must provide the Raw File Path and Order of the lab guide file that should be available in GitHub.
    * **Raw File Path:** This is the raw URL of the documents in your GitHub account.
    * **Order:** Defines the sequence of the pages in your lab guide.

Example: You have a lab guide in GitHub which includes - Introduction to the Lab, three Exercises to be performed, and a Summary.
Rather than preparing one lengthy document, we'll break it down into individual pages on GitHub and fetch the Raw URL for each page. 
We will add the Raw URL of the pages in _**Raw File Path**_, with respect to the order value. 

Therefore, the lab guide's final output will follow the flow shown below:
  * Introduction of the Lab
  * Exercise 1
  * Exercise 2
  * Exercise 3
  * Summary


For your reference, here is a Master document sample - **<https://cloudlabsai.blob.core.windows.net/master-doc/master-doc.json>**

  ![](/img/LabDeveloper/image18.png)
  
  >**Note :** You can store the file in **Azure Blob Storage** from where you can have the URL of the stored file that can be accessible.
  
To learn more about Lab guides and Github Master Document, refer [Authoring Lab Guides.](https://docs.cloudlabs.ai/LabDeveloper/AuthoringLabGuides)


  * **Approx. Deployment Duration:** As we are deploying just a VM, you can add 5 minutes of deployment duration in this section. The expected deployment duration will be defined throughout this time period. The period you enter in this area will be displayed to users as a countdown along with the progress bar to the start of the Lab.
  
  * **Region:** Here you can choose one or more Azure regions where you want to have the Azure resource deployments. The selected regions will automatically get reflected in the Lab setup. For the VM based lab you can add two regions as East US and West US. 

  ![](/img/LabDeveloper/image3.png)

 >**Note :** In case you have a custom VM image stored in Azure Compute Gallery, then you need to provide the same regions where the image has been replicated.
 
  * **Attendee Lab Cost Limit :** Leave it as **Default**.

  * **Attendee Duration Limit(in Mins):** Leave it as **Default**.

  * **Excluding Output Parameters:** You can add one or more output parameter names that needs to be excluded from the **Environment details** tab. Enter **trainerUserName** and **trainerUserPassword** in the coloumn.
 
  * **User Lab Experience Types:** Leave it as **Default**.

  * **Idleness Resources:** Leave it as **Default**.

  * **Synchronization Resources:** Leave it as **Default**

  * **Control Panel Resources:** Leave it as **Default**

C. In the last section, we will learn about the features that can be enabled:
  
  * **Create Service Principal:** Keep the box **Unchecked**.

  * **Allow Global Admin Privilege:** Keep the box **Unchecked**.

  * **Enable Lab Validation:** This field is not required, but if needed it can be enabled.
  
   >**Info** Lab validation enables you to check whether lab tasks are completed appropriately. In case the user had issues performing the lab, that can be checked under validations. To onboard the lab validation kindly reach out to your point of contact or [CloudLabs Support](../../Admin/OnboardingDocs/ContactSupport.md)).
 
  * **Enable Leaderboard :** Keep the box **Unchecked**.

  * **Enable Custom RG Name:** Checking this box will allow you to enter a custom suffix for your resource group. Once the RG is deployed, it will have **<CustomPrefix>-XXXXXX** as the name. 
  
  For example: You provide a  _**Demo**_ as Custom Suffix for your resource group. So in your environment, the Resource Group name will be _**Demo-XXXXXXX**_ , where **XXXXXXX** is the unique user/deployment ID.

  * **Enable VM Access Over Http:** This option allows you to access the virtual machine through a web browser. If the Microsoft RDP client does not allow you to connect to the VM, here is another method to connect to the VM via a browser. After enabling this functionality, you must complete further setups in order to set up RDP over HTTPS access, which you will cover in **Virtual Machine Configuration**. 

  * **Enable VM Shadow:** COVID-19 has changed the way training and workshops are conducted. Virtual workshops are the new normal in the learning industry now. Shadow feature allows instructors to shadow the user's environment / VMs (virtual machines) and provide support in real-time. 
    * Shadow student’s lab environment 
    * Provide Support in real-time 
    * Observe progress 
    * Collaboration

  * **Dynamic RGs Available:** Leave the box **Unchecked**.

  * **Delete Deployment Info After Success:** You can check the box, if you want to clean up the deployment history from Azure Portal. This will not effect the deployed resources in the Azure.

  * **Any Post Manual Steps Required :** Leave the box **Unchecked**.

  * **Any Pre Manual Steps Required:** Leave the box **Unchecked**.

  * **Enable Optimize Disk Cost:** Leave the box **Unchecked**.

  * **Show Resources Tab:** Leave the box **Unchecked**.

  * **Install VM Agent For Idle Detection:** Leave the box **Unchecked**.
  
  * **Enable Lab Preview:** Leave the box **Unchecked**.

3. At last, click on **SUBMIT** button to save all the configurations. Once you've submitted the template, you'll be directed to the main Template page.

     ![](/img/LabDeveloper/image4.png)

4. The template you created will be listed as shown in the image below. 

     ![](/img/LabDeveloper/onboardingTemplate-temlate-list.png)

4. Now, you have to reopen the template to configure other available functionalities, so click on **Edit** button.

     ![](/img/LabDeveloper/onboardingTemplate-template-edit.png)

5. Here you will have access to the following functionalities in order to fully configure a CloudLabs Template:

  * ARM Template
  * Template Permissions
  * Custom Handlers
  * MS Cloud Licenses
  * Deployment Script Repository
  * Virtual Machine Configuration
  * Course Details
  * Template Audit

 ![](/img/LabDeveloper/image5.png)

Now you will have a look at each of the features to understand how they work.

#### ARM Template

As the name suggests, you will provide the ARM template files here to provision your lab environment.  

* **ARM template file:** The ARM Template is a JavaScript Object Notation (JSON) file that outlines your project's infrastructure and settings. The resources required for deployment as well as their properties must be specified in the template.
  
  An ARM Template has the following sections:

  - [x] **Parameters -** In the parameters section of the template, you specify which values you can input when deploying the resources.

  - [x] **Variables -** In the variables section, you construct values that can be used throughout your template. You don't need to define variables, but they often simplify your template by reducing complex expressions.

  - [x] **Resources -** In the resources section, you define the resources that will be deployed.

  - [x] **Outputs -** In the outputs section, you specify values that are returned from deployment. Typically, you return values from resources that were deployed.


* **Parameter file:** Rather than passing parameters as inline values in your ARM Template, you can use another JSON file that contains the parameter values. The parameter names in your parameter file and template file must match.


To learn more about ARM Template, check [Create and deploy your first ARM template.](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-first-template?tabs=azure-powershell)

Take the steps below to get started:

1. Click on the **+ ADD** button.

 ![](/img/LabDeveloper/image7.png)

2. Fill up the below given sections:

  * **Resource Group:** Select a resource group from the drop down.
  * **Custom Suffix:** This option will be available only if you select **Enable Custom RG Name** box that was mentioned in the previous section. Here you can give a custom name to your Resource Group.
  * **ARM Template URL:** Copy and paste the below mentioned URL:

      Below ARM template is having all the required resources to create a basic VM on Azure.

      ```
      https://cloudlabsai.blob.core.windows.net/templates/deploy-01.json
      ```

  * If you want to create an ARM template with specific VM configurations, navigate to the below mentioned URL:

     [User Specified ARM Template](../../Admin/OnboardingDocs/ConfigureUserSpecifiedARMTemplate.md)

  * **Parameter Template URL:** Copy and paste the below mentioned URL:

      Below Parameters file is having all the required Parameters that is needed to create a VM.

      ```
      https://cloudlabsai.blob.core.windows.net/templates/deploy-01-parameters.json
      ```

      > **Note:** If you are using custom VM image reference, then you need to provide the same values for parameters **adminUsername** & **adminPassword** that you provided when creating the VM from Azure Marketplace image.

  * Click on **SUBMIT** to save the configurations.

 ![](/img/LabDeveloper/image9.png)


#### MS CLOUD LICENSES

There are some conditions that must be met before a user can access Microsoft products. To fulfill those conditions, we have Microsoft licenses to provide software services and hosted applications for the users performing your lab.

This function grants you access to a variety of Microsoft licences which include Power BI Pro, Office 365 Business Essentials, Azure Active Directory Premium P1 and much more. Some of those are shown in the image below:

![](/img/LabDeveloper/image24.png)

Now we have a set of instructions listed below that will show you how to add a License:

1. Click on the **+ ADD** button.

![](/img/LabDeveloper/image20.png)

2. Perform the following steps to pick a license:
* **MS Cloud License:** Select the required license from drop down.
* Click on **SUBMIT** to save the configurations.

![](/img/LabDeveloper/image21.png)


#### VIRTUAL MACHINE CONFIGURATION

This feature allows you to configure your host virtual machine to complete the setup for RDP over HTTP access. 
As we stated earlier that once your lab is ready, the environment you receive will include a VM on the left side of the browser and the Lab Guide on the right. 

Therefore, by providing the required configuration here, it will reflect your host VM in your lab environment. 

Take the steps below to get started:

1. Click on the **+ ADD** button.

![](/img/LabDeveloper/image22.png)

2. Under **Add VM Configuration**, add following values:

* **Name:** Enter **labvm-{GET-DEPLOYMENT-ID}**.
* **Type:** Choose **RDP**
* **Server DNS Name:** Enter **LabVM DNS Name**
* **Server User Name:** Enter **LabVM Admin Username**
* **Server Password:** Enter **LabVM Admin Password**
* **Instructor Username:** Enter **TrainerUserName**
* **Instructor Password:** Enter **TrainerUserPassword**
* At last, click on **SUBMIT** to save the configurations.

![](/img/OnboardingDocs/VMconfig.png)

3. Leave the **COURSE DETAILS** , **TEMPLATE LAB ASSET** , **TEMPLATE AUDIT** tabs as default.

4. Scroll to the top and click on **Submit** to save the configurations.

   ![](/img/OnboardingDocs/submit-v2.png)
