---
title: Nuxeo Cloud Customer Console
labels:
    - nuxeo-cloud
description: Get an overview of the Nuxeo Cloud Console.
review:
    comment: ''
    date: '2023-06-15'
    status: ok
tree_item_index: 350
toc: true
---

The Nuxeo Cloud Customer Console provides our customers with increased self service capabilities. Among other useful features, the Cloud Customer Console primarily gives users the ability to build Dedicated Customer Images and deploy them to Customer Pre-Production Environments. Our long term goal is to enable more self service capabilities allowing customer increased visibility to hosted Nuxeo Cloud environments and related information.

## Dedicated Image Build and Deployment Pipelines

The Nuxeo Cloud Customer Console introduces the ability to build and deploy a dedicated Nuxeo Docker Image to your Pre-Production Cloud Environment.
-	**Image Build Pipeline** - The Image Build Pipeline starts with an LTS 2021 + HotFixes Docker image. Then combines it with your application Marketplace package and dependent add-ons to produce a Dedicated Customer Image. This Image Build is defined and managed as part of a Customer Project profile. This Dedicated Docker Image artifact can then be deployed to your Pre-Production & Production environments.
-	**Image Deployment Pipeline** - The Deployment pipeline is the action of deploying a Nuxeo Docker Image created by the Build Pipeline to a Pre-Production or Production environment. The same Image Build and Deployment process is used by the Nuxeo Cloud team to deploy Customer specific Nuxeo Docker Images artifacts to customer environments. The Nuxeo Docker Image is the artifact that is deployed and each image has a unique build number. The Nuxeo Cloud Customer Console references the build number to select and deploy to the Environment.

{{#> callout type='info' heading='Build Number'}}
All customers should provide the Build Number as part of all Production deployment JIRA requests going forward. The Build Number refers to the Nuxeo Docker Image you have tested in your Pre-Production environment and want deployed to Production.
{{/callout}}

## Overview Page

After logging into the Cloud Console, users will land on the Overview page which provides the following features:
1.	Add, Remove, Edit and View Customer Contact Information
2.	Link to Nuxeo Cloud documentation
3.	List of Production and Pre-Production Environments

{{!--     ### nx_asset ###
    path: /default-domain/workspaces/Product Management/Documentation/Documentation Screenshots/Nuxeo Cloud/Cloud Console Homepage
    name: cloud-console-homepage.png
    server#screenshot#up_to_date
--}}
![Cloud Console Homepage](nx_asset://675c9b0d-c30b-4ba9-869b-410d9375128e ?w=650,border=true)
 
Environment details can be accessed by clicking on the “eye” icon shown next to available environments listed on the Overview Page. At this time customers can only view and schedule deployments to Pre-Production environments within the Cloud Console. Production deployment requests must be made by submitting a JIRA SUPNXP ticket. 

### Product Version and Product Revision

For each environment, we display the Product Version and the Nuxeo Product Revision. These provide information on the latest HotFix deployed to each environment. 
Please note that versions are dynamically retrieved from the login page. If a customer uses a custom login page instead of the default Nuxeo login page, we will not be able to retrieve the version and will display _Not Available_.

## Environment Details and Deployments

Environment details for the selected environment are shown on this page. Customers are able to view environment details, recent Image Builds and Logs, recent Deploys, as well as initiate new Image Builds or Deploys. 

{{!--     ### nx_asset ###
    path: /default-domain/workspaces/Product Management/Documentation/Documentation Screenshots/Nuxeo Cloud/Cloud Console Env page
    name: cloud-console-env-page.png
    server#screenshot#up_to_date
--}}
![Cloud Console Env page](nx_asset://18fff4ed-6794-4dc5-adff-fdd1a4454b17 ?w=650,border=true)
 
### Image Builds

The Customer Cloud Console gives users the ability to create a new Image Build that can be deployed to Pre-Production environments. 

{{!--     ### nx_asset ###
    path: /default-domain/workspaces/Product Management/Documentation/Documentation Screenshots/Nuxeo Cloud/Cloud Console New build
    name: cloud-console-new-build.png
    server#screenshot#up_to_date
--}}
![Cloud Console New build](nx_asset://4c996bc2-d2e3-46b9-9e74-a7f688ca34ec ?w=350,border=true)
 
When creating a new Build customers are asked to provide the following: 
-	**Package Name** The name of the Nuxeo Marketplace Package to be used
-	**Package Version** The version of the Nuxeo Marketplace Package to be used
-	**Nuxeo Packages** There will be a list of packages set for the environment and should not be altered. You can include additional add-ons which your application requires. If you have questions please ask our support team.
-	**Product Version** This is the Base Nuxeo Version for ex LTS 2021 and will be predefined.
-	**Product Revision** The Nuxeo Hotfix version to be used. ex LTS 2021 HF25
-	**Cloud project** A cloud project is the container where the Image Build is managed. This is predefined by the Cloud Team based on the Nuxeo Version and your Application needs. 
-	**Status & Logs** The Build Image creation process provides a summary status and access to logs following the success or failure of the Build Deployment Pipeline. Logs can be accessed via Environment details page in the Build section. Build Image errors can be resolved by creating a Jira SUPNXP ticket to notify the Nuxeo Cloud team of the error.

### Pre-Production Deployments

The Cloud Console provides customers with the ability to deploy an Image Build to **Pre-Production Environments only**. 

{{!--     ### nx_asset ###
    path: /default-domain/workspaces/Product Management/Documentation/Documentation Screenshots/Nuxeo Cloud/Cloud Console New Deploy
    name: cloud-console-new-deployment.png
    server#screenshot#up_to_date
--}}
![Cloud Console New Deployment](nx_asset://5e773085-31d6-4956-b27a-4d3e2640450e ?w=350,border=true)
 
When creating a new Deployment, the customer is asked to identify the following: 
-	**Image Build #** The image build number created as a result of the image build process.
-	**Deployment Time** The preferred time for the deployment. If the “Deploy during next maintenance window” is selected, the Deployment Time will become read only and display the maintenance window start time. 
-	**Deploy on next maintenance window** This box should be checked if the deployment should occur during the next scheduled maintenance window. 
-	**Deployment Status & Details** Additional deployment information regarding the success or failure of the deployment can be found in the deployments table. More information will be provided on commonly found errors in the future. Deployment errors can be resolved by creating a Jira SUPNXP ticket to notify the Nuxeo Cloud team of the error. 

### Maintenance Windows

All customers have a pre-defined Maintenance Window for performing deployments. Customers have the option to perform Pre-Production deployment during the next scheduled maintenance window by selecting the “Deploy during next maintenance window” checkbox. 
The standard maintenance window for each region is as follows:
- US customers - 12AM - 2AM ET 
- EU customers - 12AM - 2AM CST 
- APAC customers - 12AM - 2AM JST
Customers may choose not to deploy during the maintenance window and provide a Deployment time outside the maintenance window. In these cases the maintenance window will be ignored.

## Production Deployments

Production deployments can be requested by following the JIRA ticketing process which can be found in the [How to Fill a JIRA Ticket]({{page space='studio' page='how-to-fill-a-jira-ticket'}}) page. JIRA tickets should include the Build Number when requesting Production Deployments to ensure that the correct Build Image is deployed to Production. 