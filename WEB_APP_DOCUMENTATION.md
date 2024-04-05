# Deploying a Node.js Application on Azure using Web App
---

# Table of Contents
1. [Set up an App Service Plan](#set-up-an-app-service-plan)
2. [Create a Web App within the App Service Plan](#create-a-web-app-within-the-app-service-plan)
3. [Fork and clone a GitHub repository](#fork-and-clone-a-github-repository)
4. [Run the application locally](#run-the-application-locally)
5. [Deploy the application to Azure Web App](#deploy-the-application-to-azure-web-app)
6. [Establish a deployment slot](#establish-a-deployment-slot)

## Set up an App Service Plan
1. Login to the [Azure Portal](https://portal.azure.com/).
2. In the search bar, search for __App Service Plan__ and select it.
![1](https://github.com/oputaolivia/AzureWebApp/assets/72948572/b71ab5d9-c294-4222-84ca-4aaf1bd58b22)

3. Click on __+ Create__
![2](https://github.com/oputaolivia/AzureWebApp/assets/72948572/85601cb0-2399-4a78-bfc9-36daa32b55c7)

4. On the __Basics__ tab, Select an Azure subscription and Resource Group in the project details section. In the app service plan details section inputa the plan name, select the operating system and region.
![3](https://github.com/oputaolivia/AzureWebApp/assets/72948572/d87b27be-2fe0-41c5-a9ba-2bf1b43535eb)

5. In the pricing tier section, selsct a pricing plan.
> I chose a standard plan cause it has deployment slot.
![4](https://github.com/oputaolivia/AzureWebApp/assets/72948572/7eefb35f-183b-4ff2-8493-ce7d31389833)

6. Move to the __Review + Create__ tab, await validation and click on create.
![5](https://github.com/oputaolivia/AzureWebApp/assets/72948572/01584363-464f-47fb-929b-e24d62a8b18e)

7. Once the app service plan has been deployed, you can click on go to resource.
![6](https://github.com/oputaolivia/AzureWebApp/assets/72948572/8bd29a08-6563-4dd8-8549-056685e72694)

## Create a Web App within the App Service Plan
1. From the home page, search for __App Services__ and select it.
![1](https://github.com/oputaolivia/AzureWebApp/assets/72948572/b0d00842-6e26-4fd8-94ed-76b919017e7f)

2. Click on __+ Create__ and the __+ Web App__.
![2](https://github.com/oputaolivia/AzureWebApp/assets/72948572/840886af-6e79-4d5b-a64c-42216dc3ae8b)

3. On the __Basics__ tab, Select an Azure subscription and Resource Group in the project details section. In the instance details section, give the web app a name, select how it would be published, select a runtime that matches the project you are working with and select an operating system and region.
![3](https://github.com/oputaolivia/AzureWebApp/assets/72948572/776d64ed-04ab-42d7-93c0-99f2cc96ffbd)

4. In the pricing plans details, select the App service plan that was created in the previous section.
![4](https://github.com/oputaolivia/AzureWebApp/assets/72948572/f0d3bdfa-517d-4700-9e6a-fac4b07428f3)

5. Click on the __Review + Create__ tab, await validation and select create.
![5](https://github.com/oputaolivia/AzureWebApp/assets/72948572/43c0074e-b9dc-4c57-8a4f-3743d73ef3d8)

6. Once dployment is done, click on __Go to resource__.
![6](https://github.com/oputaolivia/AzureWebApp/assets/72948572/e5125cbd-b6dc-4267-85ac-4fcf97a40f72)

## Fork and clone a GitHub repository
1. Open GitHub and search for a repo taht suits the run time that was used to create the app service, I am working with a Node.js application, Open the repository and select __fork__ and crreate a fork.
![1](https://github.com/oputaolivia/AzureWebApp/assets/72948572/95ef5259-08f3-4ac2-967e-65eea5154e57)

2. Fill in the necessary details to create a fork and click __Create fork__.
![2](https://github.com/oputaolivia/AzureWebApp/assets/72948572/6d2a332a-14a7-4333-9231-7306582ce915)

3. In the forked repository click on code and copy the github repo https link.
![3](https://github.com/oputaolivia/AzureWebApp/assets/72948572/9376989e-3d72-4d05-8bf6-545d9aa072f1)

4. Open a terminal or CLI navigate to the directory for the project use the command to clone the repository
```
git clone <git-url>
```
![4](https://github.com/oputaolivia/AzureWebApp/assets/72948572/6b07aa96-afd5-4c6d-ad65-88637abaff3f)

## Run the application locally
1. To run application locally, first install all the dependencies using 
```
npm install
```
Change the __.env.sample__ file to __.env__ file and input the neccessary values.
![1](https://github.com/oputaolivia/AzureWebApp/assets/72948572/abaf9a45-90a3-4c76-88b7-b0f043b52d53)

2. Run the server using the command
```
node index.js
```
![2](https://github.com/oputaolivia/AzureWebApp/assets/72948572/59f9498c-e4b3-4df4-b2bf-b917ca1c43b9)

## Deploy the application to Azure Web App
1. In the Web App resource that was just created, select the __deployment center__ blade under the deployment section and select the source (I used github, given my code is on github) and authorize github.
![1](https://github.com/oputaolivia/AzureWebApp/assets/72948572/e3e4bb8b-5db4-4420-bc87-d1b1bd2b36e4)

2. Select an organization, the repository that would be deployed.
![2](https://github.com/oputaolivia/AzureWebApp/assets/72948572/a42d8f4e-6ac7-46ec-a292-a440f15f53b1)

3. Use an authentication type of user-assigned identity
![3](https://github.com/oputaolivia/AzureWebApp/assets/72948572/5fdc7f96-b3e7-41fd-988e-8a40f1a2e144)

4. Click on __Save__
> Now the deployment is taking place, the CI/CD pipeline would be triggered.
![4](https://github.com/oputaolivia/AzureWebApp/assets/72948572/8de8462d-656f-400b-8266-e08bfc6d8d93)

5. 
## Establish a deployment slot
1. In the Web App resource that was just created, select the __deployment slots__ blade under the deployment section and click on __Add slot__.
![1](https://github.com/oputaolivia/AzureWebApp/assets/72948572/27e61546-1fce-473b-87b9-c9dc67b0d8d0)

2. Input a slot name (staging) and clone the settings of the current web app service and select __Add__.
![2](https://github.com/oputaolivia/AzureWebApp/assets/72948572/157361c1-7158-4b75-b638-961bdc089451)

3. Allocate 40% of thr traffic to the new staging slot that was created.
![3](https://github.com/oputaolivia/AzureWebApp/assets/72948572/112b1eeb-a496-4904-b1c7-126f9f6a59f3)
