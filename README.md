# Google Cloud with Nexmo SMS
<img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image1.jpeg" width=200>

## Introduction

For system-wide visibility into Google Cloud resources and applications, user can leverage google messaging and monitoring services such as Google Monitoring Service to get notification for critical events such as CPU usage, disk usage, application performance, etc. To receive such notifications as SMS on mobile, user can use the Google Cloud with Nexmo SMS app that makes it easy to set up, operate, and send notifications from the Google Cloud. This app collects the published messages from Google Monitor services and immediately deliver them to subscriber’s mobile as SMS.

Google Cloud with Nexmo SMS app is a web service which sends SMS using Nexmo Messaging APIs. This service communicates with Google Monitoring service and sends SMS notification to the configured phone number whenever defined condition is true.

## Use Case

For Google cloud resources and applications, enable Google Compute Engine (GCE) administrator to receive real-time SMS notifications wherever they are.

Using GCE Monitoring service user can set thresholds for following:

-   CPU Usage

-   Read disk I/O

-   Write disk I/O

-   Byte Received

## Prerequisites 

-   Python 2.7

-   Compute Engine instance user with administrative privileges

-   Google account and Google Compute Instance

-   Nexmo subscription and corresponding Nexmo API keys (Keys and Secret). To access the API keys, see appendix section

-   Git package

-   Supported OS: Ubuntu 14.04

## Features

-   Enable and disable SMS functionality

-   Send Compute Engine notifications as SMS

-   User friendly UI

-   Real time notification

-   Easy integration and configuration with Google Monitoring

## Steps to deploy the Google Cloud with Nexmo SMS

To install the Google Cloud with Nexmo SMS app on Ubuntu 14.04 OS, follow the below steps:

1.  Login to the terminal using **SSH** or any other media.

2.  Clone the Google Cloud with Nexmo SMS repository to the desire directory.

    **```cd ~```**

    **```sudo apt-get install git -y```**
	
    **```git clone```**[**```https://github.com/AdvaiyaLabs/Google-Cloud-with-Nexmo SMS.git```**](https://github.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS.git)

3.  Change the directory to the Google Cloud with Nexmo SMS.

    **```cd Google-Cloud-with-Nexmo-SMS```**
4.  Run the following command to install and configure the Nexmo services.

    **```sudo python install.py```**
	
    The above steps will install following libraries on Google Cloud with Nexmo SMS instance:
    -   Django 1.8.5

   -   Nexmo library

   -   Httplib2

## Google firewall settings

1.  Login to the Google Cloud console.
2.  Go to menu and select **Networking** under **Compute** section.

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image4.png" width=200>
3.  On **Networks** dashboard, click the **default** link.

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image5.png" width=200>
4.  Click on the **Add firewall rule** link as shown in the below image:

     <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image6.png" width=400>
5.  Set the firewall rule, allow port **9033** and IP range **0.0.0.0/0**:

	<img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image7.png" height=600>
6.  Click on **Create**.

## Steps to use the Google Cloud with Nexmo SMS

1.  On Google Cloud console, click on **Menu** and select **Compute Engine** option.
2.  Copy **External IP** of the instance where you have deployed the GCNotifer app from the instance list.

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image8.png" width=600>
3.  Go to the browser and paste/type &lt;**&lt;Compute Engine Instance IP&gt;:9033**&gt; (replace Compute Engine Instance IP with your instance public IP address).
4.  Login with default credentials - username: **admin** and password: **admin.**

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image9.png" width=400>
5.  Set the value according to the label shown. To get the Nexmo API key and Secret, see the appendix.

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image10.png" height=600>
6.  To receive SMS from the Nexmo, check **Enable SMS**. Click on **Save**.

## Steps to configure with webhook

1.  Click on [https://app.google.stackdriver.com/settings/notifications/static-webhook/](https://app.google.stackdriver.com/settings/notifications/static-webhook/)
2.  Login to Google Cloud Console.
3.  Click on **Add**

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image11.png" width=600>

4.  Set the **ENDPOINT URL** as your instance ID and **WEBHOOK NAME** that identifies the webhook.

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image12.png" width=600>
5.  Click on **Save.**

## Steps to configure with Google Monitoring

1.  Go to Google Developers Console.
2.  Click on menu and select **Monitoring.**
3.  Click on **Create Policy.**

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image13.png" width=600>
4.  Type the **Policy Name** and click on **Next.**

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image14.png" width=600>
5.  Select an instance from **RESOURCE TYPE**. Also select **APPLIES TO** from the drop down. Then click on **Next**.

	<img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image15.png" width=600>
6.  Set the threshold as per the requirements. For example - to check the CPU Usage, select CPU Usage (GCE Monitoring) under **IF METRIC**. 

	<img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image16.png" width=600>
7.  Click on **Save Condition.**
8.  Now configure the notification, select **Webhook** from the **METHOD** dropdown as shown in the below example.

	<img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image17.png" width=600>
9.  Click on **Add Notification**.
10.  Optionally set the description in **Documentation** section and click on **Save Policy**.

     <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image18.png" width=600>
11.  User will receive SMS when the condition satisfies.

Appendix
========

Nexmo API Keys
--------------
-   To access Nexmo keys, go to <https://www.nexmo.com/> and sign-in
-   On the top right corner, click on the **Api Settings**
-   Key and Secret will display in the top bar as shown in the below image:

    <img src="https://raw.githubusercontent.com/AdvaiyaLabs/Google-Cloud-with-Nexmo-SMS/master/docs/image19.png" width=600>

	
	