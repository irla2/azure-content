<properties
   pageTitle="Introspecting your Code Using Z-Ray on Azure"
   description="Describes how to use Zend's Z-Ray on Azure to debug and profile PHP applications deployed on Azure web app service."
   services="Z-Ray on Azure"
   documentationCenter="dev-center-name"
   authors="DanielBerman"
   manager="manager-alias"
   editor=""/>

<tags
   ms.service="Z-Ray on Azure"
   ms.devlang="PHP"
   ms.topic="article"
   ms.tgt_pltfrm="may be required"
   ms.workload="required"
   ms.date="mm/dd/yyyy"
   ms.author="daniel.be@zend.com;@proudboffin"/>

# Introspecting your Code Using Z-Ray on Azure

So you’ve heard about Z-Ray, and you know that it’s now available for Azure web apps. How do you get it working on your code?

This tutorial will walk you through the entire process for getting Z-Ray to work on your code on Azure. You’ll learn how to create a new web app on Azure, upload your code, enable Z-Ray and start using it to introspect your code.

To follow the steps outline here, all you need is a Microsoft Azure account, some working code, and 5 minutes of your time.

Let’s get this show on the road!

  ![Alt text; do not leave blank. Describe image.][8]

## Step 1 : Creating an Azure Web App

Your first step is to create a new web app on Azure. An Azure web app is basically a container that holds all your application code and configurations on the cloud.

1. Log into the [Azure portal](https://portal.azure.com).
2. In the top-left corner if the portal, click the New button.
3. In the Create blade, select Web + Mobile, and then Web App.

  	![Alt text; do not leave blank. Collector car in racing red.][5]

4. In the Web App blade, configure your web app settings:
   - URL - enter the URL of your website
   - Subscription - select an existing subscription
   - Resource Group - select an existing resource group or create a new one
   - App Service Plan - select an app service plan, or create a new one. A service plan is basically the container that holds your app, with settings that determine the location, costs and resources associated with it.
   
5. Click **Create**.
Your new web app is pinned to the Startboard, and will take a few minutes to be created.

Once created, the web app blade opens and you get a notification that your deployment succeeded!

   ![Alt text; do not leave blank. Collector car in racing red.][5]

Clicking Browse at the top of the blade opens our web app with a default page displayed.
  	![Alt text; do not leave blank][6]

## Step 2 : Uploading your Code

Great! You’ve got your new Azure web app up and running. Now, it’s time to upload some code into the container.

To do this we’re going to access the web app’s Kudo. Kudo is a diagnostic console that exposes Azure behind-the-scenes processes and is useful for capturing a memory dump, looking at deployment logs, viewing configuration parameters and much more.

1. Access your web app’s Kudo by adding 'scm' to your web app's URL as follows:
*http://<webappname>.scm.asurewebsites.net*


2. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia.

   	    // Because toast alerts don't work when the app is running, the app handles them.
        // This uses the userInfo in the payload to display a UIAlertView.
        - (void)application:(UIApplication *)application didReceiveRemoteNotification:
        (NSDictionary *)userInfo {
            NSLog(@"%@", userInfo);
            UIAlertView *alert = [[UIAlertView alloc] initWithTitle:@"Notification" message:
            [userInfo objectForKey:@"inAppMessage"] delegate:nil cancelButtonTitle:
            @"OK" otherButtonTitles:nil, nil];
            [alert show];
        }


    > [AZURE.NOTE] Duis sed diam non <i>nisl molestie</i> pharetra eget a est. [Link 2 to another azure.microsoft.com documentation topic](web-sites-custom-domain-name.md)


Quisque commodo eros vel lectus euismod auctor eget sit amet leo. Proin faucibus suscipit tellus dignissim ultrices.

## Heading 2 (H2)

1. Maecenas sed condimentum nisi. Suspendisse potenti.

  + Fusce
  + Malesuada
  + Sem

2. Nullam in massa eu tellus tempus hendrerit.

  	![Alt text; do not leave blank. Example of a Channel 9 video.][7]

3. Quisque felis enim, fermentum ut aliquam nec, pellentesque pulvinar magna.




<!--Every topic should have next steps and links to the next logical set of content to keep the customer engaged-->
## Next steps

Vestibul ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nullam ultricies, ipsum vitae volutpat hendrerit, purus diam pretium eros, vitae tincidunt nulla lorem sed turpis: [Link 3 to another azure.microsoft.com documentation topic](storage-whatis-account.md).

<!--Image references-->
[5]: ./media/markdown-template-for-new-articles/octocats.png
[6]: ./media/markdown-template-for-new-articles/pretty49.png
[7]: ./media/markdown-template-for-new-articles/channel-9.png
[8]: ./media/markdown-template-for-new-articles/copytemplate.png

<!--Reference style links - using these makes the source content way more readable than using inline links-->
[gog]: http://google.com/        
[yah]: http://search.yahoo.com/  
[msn]: http://search.msn.com/    
