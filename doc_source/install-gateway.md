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

**To install and configure the gateway on Amazon Linux, Red Hat, CentOS, or Ubuntu Server**

1. Install the Alexa for Business gateway:

   + For Amazon Linux, Red Hat, or CentOS, run the following command:

     sudo yum install \-y a4b\_gateway\_<architecture>\.rpm

   + For Ubuntu Server, run the following command:

     sudo dpkg \-i a4b\_gateway\_<architecture>\.deb 

1. Edit the **/etc/alexaforbusinessgateway/secrets\.cfg** text file to set the credentials of your Cisco TelePresence systems\. 

1. Open the **/etc/alexaforbusinessgateway/gateway\.cfg\.template** text file, verify that the system manager in **maintenance\.servicemanager** is set to the correct value \(valid values are **sysvinit**, **upstart**, or **systemd**\) and save the file\.:

   "serviceManager": "systemd"

1. Register the gateway to your Alexa for Business setup:

   sudo /usr/bin/alexaforbusinessgateway\-register 

1. When prompted, enter the IAM access keys and secret keys of the IAM users that you created previously\.

1. Start the Alexa for Business gateway service:

   + Sysvinit: sudo service alexaforbusinessgateway start

   + Upstart: sudo initctl start alexaforbusinessgateway

   + Systemd: sudo systemctl start alexaforbusinessgateway

1. \(Optional\) Check the **/var/log/alexaforbusinessgateway/gateway\.log** file for errors logged when starting the service\.

1. \(Optional\) Run the following command to start the alexaforbusinessgateway service at each system boot:

   + Sysvinit: sudo chkconfig alexaforbusinessgateway on

   + Upstart: Enabled by default

   + Systemd: sudo systemctl enable alexaforbusinessgateway\.service

**To install and configure the gateway on other Linux distributions**

1. Extract the Alexa for Business gateway tarball:

   tar zxvf a4b\-gateway\_<architecture>\.tar\.gz

1. Create the directory **/etc/alexaforbusinessgateway**\.

1. Copy the **config/secrets\.cfg** text file to **/etc/alexaforbusinessgateway/secrets\.cfg** and set the credentials of your Cisco TelePresence systems in the file\. 

1. Copy the **config/gateway\.cfg\.template** text file to **/etc/alexaforbusinessgateway/config\.cfg\.template**\. 

1. Open the **/etc/alexaforbusinessgateway/gateway\.cfg** text file and set the value of **credentials\.static** to the AWS credentials of the AlexaForBusinessGateway IAM user that you created previously\.

1. Verify that the system manager in **maintenance\.servicemanager** is set to the correct value \(valid values are **sysvinit**, **upstart**, or **systemd**\) and save the file\.

1. Register the gateway to your Alexa for Business setup:

   sudo \./alexaforbusinessgateway\-register 

1. When prompted, enter the IAM access keys and secret keys of the IAM users that you created previously\.

1. \(Optional\) To make the service manager available on your distribution, run the following command:

   sudo \./install\.sh

1. Start the Alexa for Business gateway service:

   + Sysvinit: sudo service alexaforbusinessgateway start

   + Upstart: sudo initctl start alexaforbusinessgateway

   + Systemd: sudo systemctl enable alexaforbusinessgateway\.service

1. \(Optional\) Check the **/var/log/alexaforbusinessgateway/gateway\.log** file for errors logged when starting the service\.