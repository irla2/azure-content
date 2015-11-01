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

## Step 1 : Creating an Azure Web App

Your first step is to create a new web app on Azure. An Azure web app is basically a container that holds all your application code and configurations on the cloud.

1. Log into the [Azure portal](https://portal.azure.com).
2. In the top-left corner if the portal, click the New button.
3. In the Create blade, select Web + Mobile, and then Web App.

  	![Web App blade][1]

4. In the Web App blade, configure your web app settings:
   - URL - enter the URL of your website
   - Subscription - select an existing subscription
   - Resource Group - select an existing resource group or create a new one
   - App Service Plan - select an app service plan, or create a new one. A service plan is basically the container that holds your app, with settings that determine the location, costs and resources associated with it.
   
5. Click **Create**. Your new web app is pinned to the Startboard, and will take a few minutes to be created. Once created, the web app blade opens and you get a notification that your deployment succeeded!

   ![New Web App created][2]

Clicking Browse at the top of the blade opens our web app with a default page displayed.

  	![New empty Web App open in browser][3]

## Step 2 : Uploading your Code

Great! You’ve got your new Azure web app up and running. Now, it’s time to upload some code into the container.

To do this we’re going to access the web app’s Kudo. Kudo is a diagnostic console that exposes Azure behind-the-scenes processes and is useful for capturing a memory dump, looking at deployment logs, viewing configuration parameters and much more.

1. Access your web app’s Kudo by adding 'scm' to your web app's URL as follows:
*http://<webappname>.scm.asurewebsites.net*
2. In the Kudo console, go to **Debug console | CMD**.

   ![Alt text; do not leave blank][4]

3. Browse to **site | wwwroot**.
4. Drag and drop a .zip file containing your code onto the right side of the screen above the CMD window.
[AZURE.NOTE] In this article, I'm uploading the Zend Framework 2 skeleton application but of course you can uplaod any code you want.

5. After Azure finished to upload your code, remove the existing 'hostingstart.html' file.

6. Open your app in a browser. Make sure to enter the correct path to the opening app file.
**Example:** *https://danieldemo.azurewebsites.net/zf2skeleton/public/*

   ![Alt text; do not leave blank][5]
   
## Step 3 : Enabling Z-Ray
Cool, you’ve got your code running on Azure. Now, how do we get Z-Ray working?

1. Open your web app blade.
2. Open the Tools menu. To do this, click the Tools icon at the top of the blade.

   ![Alt text; do not leave blank. Example of a Channel 9 video.][6]

3. In the Develop section, select **Zend Z-Ray**, and then **Enable Z-Ray for Azure**.

  	![Alt text; do not leave blank. Example of a Channel 9 video.][7]

4. Select your pricing tier, and click **Select**.
5. Last but not least, review the licensing info, and click **Purchase**.
After a short while you'll get a notification informing you that Z-Ray was successfully enabled. This means that Z-Ray is now enabled for your web app!

Well done! To start working with Z-Ray, simply refresh your web app in the browser. Z-Ray is displayed at the bottom of the page with all the info you need on your app right in front of you.

   ![Alt text; do not leave blank. Example of a Channel 9 video.][8]

##Summary
So, in just a few minutes, we created a new Azure web app, uploaded our code, and began using Z-Ray.

Using Z-Ray on Azure revolutionizes the way you develop PHP on the cloud. The combination of Z-Ray and Azure means you can use Z-Ray to introspect any code you have deployed on an Azure web app, thus enabling you to enjoy the best of the two worlds - Azure's web app services and Z-Ray's powerful introspection capabilities.

<!--Every topic should have next steps and links to the next logical set of content to keep the customer engaged-->
## What Next?

You've got Z-Ray working on your web app. What now? To learn how to use Z-Ray and more about its various features, take a look at the [Online Help](http://files.zend.com/help/Z-Ray-Azure/Content/home.htm)
One of the more exciting features about Z-Ray is the ability to extend it to show any info you want using extension API. These extensions of Z-Ray are called plugins, and they can be shared with other Z-Ray users using the Zend Gallery. To learn more about the Zend Gallery and available plugins, visit [Zend.com](http://www.zend.com/en/products/server/plugins)
If you'd like to extend Z-Ray to show info on your app, visit the extension API docuemntation on [GitHub](https://github.com/zend-server-plugins/Documentation).

<!--Image references-->
[1]: http://devzone.zend.com/wp-content/uploads/2015/06/web_app_blade.jpg
[2]: http://devzone.zend.com/wp-content/uploads/2015/08/webappcreated.jpg
[3]: http://devzone.zend.com/wp-content/uploads/2015/06/new_web_app3.jpg
[4]: http://devzone.zend.com/wp-content/uploads/2015/06/kudo1.jpg
[5]: http://devzone.zend.com/wp-content/uploads/2015/06/kudo2.jpg
[6]: http://devzone.zend.com/wp-content/uploads/2015/06/code_uploaded2.jpg
[7]: http://devzone.zend.com/wp-content/uploads/2015/08/tools_icon1.jpg
[8]: http://devzone.zend.com/wp-content/uploads/2015/08/pricing_tiers.jpg
