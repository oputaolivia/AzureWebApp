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

3. Click on __+ Create__

4. On the __Basics__ tab, Select an Azure subscription and Resource Group in the project details section. In the app service plan details section inputa the plan name, select the operating system and region.

5. In the pricing tier section, selsct a pricing plan.
> I chose a standard plan cause it has deployment slot.

6. Move to the __Review + Create__ tab, await validation and click on create.

7. Once the app service plan has been deployed, you can click on go to resource.

## Create a Web App within the App Service Plan
1. From the home page, search for __App Services__ and select it.

2. Click on __+ Create__ and the __+ Web App__.

3. On the __Basics__ tab, Select an Azure subscription and Resource Group in the project details section. In the instance details section, give the web app a name, select how it would be published, select a runtime that matches the project you are working with and select an operating system and region.

4. In the pricing plans details, select the App service plan that was created in the previous section.

5. Click on the __Review + Create__ tab, await validation and select create.

6. Once dployment is done, click on __Go to resource__.

## Fork and clone a GitHub repository
1. Open GitHub and search for a repo taht suits the run time that was used to create the app service, I am working with a Node.js application, Open the repository and select __fork__ and crreate a fork.

2. Fill in the necessary details to create a fork and click __Create fork__.

3. In the forked repository click on code and copy the github repo https link.

4. Open a terminal or CLI navigate to the directory for the project use the command to clone the repository
```
git clone <git-url>
```

## Run the application locally
1. To run application locally, first install all the dependencies using 
```
npm install
```
Change the __.env.sample__ file to __.env__ file and input the neccessary values.


2. Run the server using the command
```
node index.js
```

## Deploy the application to Azure Web App
1. In the Web App resource that was just created, select the __deployment center__ blade under the deployment section and select the source (I used github, given my code is on github) and authorize github.

2. Select an organization, the repository that would be deployed.

3. Use an authentication type of user-assigned identity

4. Click on __Save__
> Now the deployment is taking place, the CI/CD pipeline would be triggered.

5. 
## Establish a deployment slot
1. In the Web App resource that was just created, select the __deployment slots__ blade under the deployment section and click on __Add slot__.

2. Input a slot name (staging) and clone the settings of the current web app service and select __Add__.

3. Allocate 40% of thr traffic to the new staging slot that was created.
