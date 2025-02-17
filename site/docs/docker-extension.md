---
title: Livecycle Docker Extension
sidebar_position: 11
---

# Livecycle Docker Extension 🐳

## Overview

The Livecycle Docker Extension enables you to share your local development environment with your team, so you can get feedback much earlier in the development workflow, without the hassle of staging environments or CI builds.
The Livecycle Docker extension embeds a standalone version of the Preevy CLI, which provides all the network and collaboration capabilities. The extension creates a Preevy profile which can also be used to provision ephemeral environments.  

## Key Features

- Simple Docker for desktop UI
- Instant sharing of running applications/services:
  - Share HTTPS links so teammates can quickly access and review your web UI and backend services at runtime.
  - Instant, secure tunneling to frontend and backend services with [public or private access](https://preevy.dev/recipes/private-services). Access to private services can be restricted to your teammates' Google or GitHub accounts.
- Share to the cloud -  deploy your local environment to the cloud for longer-term feedback and collaboration.
- Tools to debug your environment - log inspection, shell, and container inspection.
- Provision remote ephemeral environments using the Preevy CLI.

## Getting Started

### Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop) 4.10 or higher.

### Steps

1. **Installing the extension**

   Navigate to this [link](https://open.docker.com/extensions/marketplace?extensionId=livecycle/docker-extension) or search for "Livecycle" in the Docker Desktop Extensions Marketplace. Click the "Install" button to install the extension.

   ![Livecycle Docker Extension](https://github.com/livecycle/preevy/assets/51878265/e1960b89-0a9a-4641-8748-3e775555aa65)

2. **Setting up a Livecycle account**

   Once you have installed the extension and opened it, you will be greeted with a login screen. You can choose to log in with your GitHub account or Google account. If you previously used Livecycle and created an organization, you can log in with your Livecycle account.

   ![Livecycle Docker Extension](https://github.com/livecycle/preevy/assets/51878265/8f996b07-797f-4633-b11e-bfcf902b17ab)

3. **Getting shareable URLs**
   
   As soon as you log in, you will be able to see a list of running docker compose applications and all the services that are running in them. To get a public shareable URL for every service, click on "Share" button below the service name.

   ![Livecycle Docker Extension](https://github.com/livecycle/preevy/assets/51878265/54044c48-d204-4320-9f9d-b885e8294df2)

   You can choose to between Local and Cloud. The local option will create a tunnel to your local machine, and the cloud option will put your application to the cloud and create a tunnel to it. You can choose depending on your use case. For example, if you want the environment to stay for few amount of time, you can choose the local option. If you want the environment to stay for a longer time, and team can access it over few days, you can choose the cloud option.

   In this flow we will choose the local option, click [here](#Share-to-the-cloud) to learn more about the cloud option. After that, you will be prompted to choose the access level. You can choose between public and private access. If you choose public access, you will get a public URL that you can share with anyone. If you choose private access, you will get a private URL that requires authentication and can only be used by your organization members. Then click on the "Share" button to get the shareable URL.

   ![Livecycle Docker Extension](https://github.com/livecycle/preevy/assets/51878265/0cd6bd7a-2608-4253-b1b0-e0e6eca496dd)

4. **Accessing the shared URL**

   URLs created by the extension are consistent, shareable, and can be used by a browser or any other http client.
   Using these URLs, your team members will be able to see and interact with your local version of the app as long as the tunnel is open and your workstation is running.  
   Private environments require adding team members to your organization, and upon access, your team members will be prompted to authenticate.
   
   ![Livecycle Docker Extension](https://github.com/livecycle/preevy/assets/51878265/cc2d9c8f-35cd-4d71-a61b-0a4041786bec)

5. **Accessing Livecycle dashboard**

   You can also access the Livecycle dashboard to see the logs and debug your application. Click on the "Open Link" button to open the Livecycle dashboard. On the dashboard, you can see all the running applications and services.
   The Livecycle dashboard requires authentication and organization membership, similar to private environments/services 

   ![Livecycle Docker Extension](https://github.com/livecycle/preevy/assets/51878265/c94b28d6-debc-471b-9621-82c73dbc79fe)

6. **Debugging, inspecting, and logging**

   Once you have opened the Livecycle dashboard, you can see all the environments/apps that are running. Click on the name of the environment for which you want to see the logs, terminal, etc. You can view the logs, terminal, and container inspection for each service.

   ![Livecycle Docker Extension](https://github.com/livecycle/preevy/assets/51878265/04e00790-beaf-4f22-bd6e-ca7f497f5aaa)

That's it! You have successfully installed the Livecycle Docker Extension and shared your local development environment with your team.

Also, you can check out the video below for a step-by-step guide how to get started with the Livecycle Docker Extension and use Local Share feature.

<p align="center"><iframe width="816" height="480" src="https://www.youtube.com/embed/SxDn889s5zg?si=6PiAXzPMmLPpF0Bb" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe></p>

## Deploy to cloud

With the Livecycle Docker Extension, you can make your local environment accessible to your team members even when your machine is offline. This is achieved by deploying your application to the cloud and creating a tunnel to it. This functionality is particularly useful when you want to share your environment with your team members for an extended period.

### Deploy a new shareable environment to the cloud
   
After following the steps in the [Getting Started](#getting-started) section to set up the Livecycle Docker Extension, instead of selecting the local option, choose the cloud option. Subsequently, you will be prompted to select a cloud provider. You can choose between AWS, GCP, and Azure. Alternatively, use Kubernetes if you have a Kubernetes cluster. Ensure you have the necessary credentials for the chosen cloud provider, and for Kubernetes, make sure you have the kubeconfig file.

  ![Livecycle Docker Extension](https://github.com/livecycle/preevy/assets/51878265/e44b5071-4014-4a6e-b59a-23cefee77908)

For this example, I will choose AWS as my cloud provider. As shown, it will ask for the region, Bundle ID, etc. You can leave the region as default or choose the region you prefer. Some fields are optional, so you can leave them blank. After that, click on the "Share" button to obtain the shareable URL.

   ![Livecycle Docker Extension](https://github.com/livecycle/preevy/assets/51878265/2ed52d3d-87ce-48eb-b4c8-1a0b1013144d)

Now, you can observe that the environment is successfully deployed to AWS, and you can access it using the shareable URL. Additionally, you can view the environment in the Livecycle dashboard, similar to the local environment, and access features such as the terminal, logs, etc..

### Deploy a local environment to the cloud

  You can also deploy an existing local environment to the cloud. To do that, simply click on the 3 dots next to the environment name and click on the "Deploy" option. After that, you will be prompted to choose the cloud provider. Choose the cloud provider you want and follow the steps in the [Deploy a new shareable environment to the cloud section](#deploy-a-new-shareable-environment-to-the-cloud) or if you don't get the prompt to choose the cloud provider, it will deploy the provider you choose previously for the environment. Like in my case, I choose AWS previously, so it will deploy to AWS.

  ![Livecycle Docker Extension](https://github.com/Pradumnasaraf/candy/assets/51878265/b350d3a9-4e8c-4236-a28b-88cf4a7a95c5)

  After that, a new environment will be created with the same name as the local environment. So, now you have two environments, one local and one cloud. To make sure the environment is deployed to the cloud, you can see the cloud icon next to the environment name. You can also see the environment in the Livecycle dashboard just like the local environment and access terminal, logs, etc.

  ![Livecycle Docker Extension](https://github.com/Pradumnasaraf/candy/assets/51878265/a624018b-0261-46f6-94eb-b32fe1e019f7)

  If are having any issues or want to give feedback, you can join the [Livecycle Community](https://community.livecycle.io) on Slack.

Also, you can check out the video below for a step-by-step guide how to use Deploy to the cloud feature.

<p align="center"><iframe width="816" height="480" src="https://www.youtube.com/embed/bslCiIkWQ5A?si=1_Mqt0tUdlOic0Bi" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe></p>

## FAQ

See the [Docker Extension FAQ](/FAQs/docker-extension).