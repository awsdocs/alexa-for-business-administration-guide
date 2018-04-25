# Maintaining the Gateway<a name="maintain-gateway"></a>

By default, the gateway automatically updates itself every day during predefined maintenance windows\. These windows are defined in the configuration file \(gateway\.cfg\) that the gateway accesses at startup\. To change these maintenance windows, edit the gateway\.cfg file and restart the gateway service\. To manually update the gateway, execute the included updater binary installed with the gateway as the administrator \(for Windows\) or as root \(for Linux\)\.

If your Cisco TelePresence or AWS credentials change, you must update your Alexa for Business gateways to use the new credentials\. 

**To update Cisco TelePresence Credentials for Windows**

1. Stop the **AlexaForBusinessGateway** service\.

1. Choose **Start** and type **Command Prompt**\.

1. From the search results, right\-click **Command Prompt** and choose **Run as administrator**\.

1. Run the following command:

   `del <path_to_secrets.cfg_file>` \(for example: `del “C:\Program Files\Amazon\AlexaForBusinessGateway\secrets.cfg”`\)

1. Create a new secrets\.cfg file with the following structure:

   ```
   {
     "CISCO": {
       "USERNAME": "your cisco appliance username here",
       "PASSWORD": "your cisco appliance password here"
     }
   }
   ```

1. Start the **AlexaForBusinessGateway** service\.

**To update Cisco TelePresence Credentials for Linux**

1. Update the credentials in /etc/alexaforbusinessgateway/secrets\.cfg\.

1. Restart the **AlexaForBusinessGateway** service:
   + Sysvinit: `sudo service alexaforbusinessgateway restart`
   + Upstart: `sudo initctl restart alexaforbusinessgateway`
   + Systemd: `sudo systemctl restart alexaforbusinessgateway `

**To update AWS Credentials for Windows**

1. Stop the **AlexaForBusinessGateway** service\.

1. Choose **Start** and type **Command Prompt**\.

1. From the search results, right\-click **Command Prompt** and choose **Run as administrator**\.

1. Run the following command:

   `del <path_to_credentials_file>` \(for example: `del “C:\Program Files\Amazon\AlexaForBusinessGateway\credentials”`\)

1. Create a new credentials file with the following structure:

   ```
   [default]
   aws_access_key_id = YOUR ACCESS KEY ID HERE
   aws_secret_access_key = YOUR SECRET ACCESS KEY HERE
   ```

1. Start the **AlexaForBusinessGateway** service\.

**To update AWS Credentials for Linux**

1. Update the credentials in /etc/alexaforbusinessgateway/credentials\.cfg\.

1. Restart the **AlexaForBusinessGateway** service:
   + Sysvinit: `sudo service alexaforbusinessgateway restart`
   + Upstart: `sudo initctl restart alexaforbusinessgateway`
   + Systemd: `sudo systemctl restart alexaforbusinessgateway `