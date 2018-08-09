# Installing the Gateway<a name="install-gateway"></a>

The gateway is available on the Alexa for Business console\. 

**To prepare for installation**

1. Open the Alexa for Business console at [https://console\.aws\.amazon\.com/a4b/](https://console.aws.amazon.com/a4b/)\.

1. Choose **Conferencing**, **Conferencing equipment skills**, **Alexa for Cisco TelePresence**, and **Download gateway**\.

1. Select the package for your operating system and choose **Download**\.

**To install and configure the gateway on Windows**

1. Run the installer on your Windows server as an administrator: right\-click on the downloaded file and choose **Run as administrator**\.

1. When prompted, enter the IAM access keys and secret keys of the IAM users that you created previously\.

1. Enter a unique name for your gateway\.

1. \(Optional\) Enter a description to identify the gateway in the Alexa for Business console\.

1. When prompted, enter the user credentials to sign into your Cisco TelePresence appliances\.

1. Open the Alexa for Business console again, refresh **Alexa for Business Gateways**, and confirm that your gateway is listed\.

1. In the **Services** window, verify that the service \(Alexa for Business gateway\) is installed and running\.

**To install and configure the gateway on Amazon Linux**

1. Install the gateway:
   + On Amazon Linux, Red Hat, or CentOS, run the following command:

     sudo yum install \-y a4b\_gateway\_<architecture>\.rpm
   + For Ubuntu Server, run the following command:

     sudo dpkg \-i a4b\_gateway\_<architecture>\.deb 
   + On other Distros, run the following commands:

     sudo tar zxvf a4b\_gateway\_<architecture>\.tar\.gz

     sudo cp bin/\* /usr/bin/

     sudo mkdir /etc/alexaforbusinessgateway

     sudo cp config/\* /etc/alexaforbusinessgateway

     \(sysvinit\): sudo cp service/sysvinit/alexaforbusinessgateway /etc/init\.d/alexaforbusinessgateway

     \(Upstart\): sudo cp service/upstart/alexaforbusinessgateway\.conf /etc/init/alexaforbusinessgateway\.conf

     \(Systemd\): sudo cp service/systemd/alexaforbusinessgateway\.service /usr/lib/systemd/system/alexaforbusinessgateway\.service

1. Set the credentials of your Cisco TelePresence systems:

    sudo nano /etc/alexaforbusinessgateway/secrets\.cfg

1. Verify that the system manager is set to the correct value \(valid values are `sysvinit`, `upstart`, or `systemd`\):

   sudo cat /etc/alexaforbusinessgateway/gateway\.cfg\.template \| grep serviceManager

1. Register the gateway to your Alexa for Business setup:

   1. Run the following command:

      sudo /usr/bin/alexaforbusinessgateway\-register 

   1. When prompted, enter the IAM access keys and secret keys of the IAM users that you created previously\.

   1. For more advanced scenarios, run the following command to see additional help documentation:

      sudo /usr/bin/alexaforbusinessgateway\-register \-\-help

1. Start the Alexa for Business gateway service:
   + sysvinit: sudo service alexaforbusinessgateway start
   + Upstart: sudo initctl start alexaforbusinessgateway
   + Systemd: sudo systemctl start alexaforbusinessgateway

1. \(Optional\) Check the logs for errors logged when starting the service:

   sudo tail /var/log/alexaforbusinessgateway/gateway\.log