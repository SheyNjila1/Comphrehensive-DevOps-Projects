# FIRST PROJECT WEB STACK IMPLEMENTATION

## WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS
A technology stack is a set of frameworks and tools used to develop a software product. This set of frameworks and tools are very specifically chosen to work together in creating a well-functioning software. They are acronymns for individual technologies used together for a specific technology product. some examples are…

If you are the account owner, I recommends that you create an IAM user for yourself for daily use of your resources.

Once you login into AWS successfully, you will see the main console with all the service listed as follows


<img width="912" alt="aws manageent console" src="https://user-images.githubusercontent.com/85270361/123521930-b63df000-d6b1-11eb-910d-dac9a376c097.PNG">

Before proceeding with the creation of an EC2 instance, Select the desired and closest region to you.

Let me list certain parameters when choosing an AWS region which factors should you consider:

* Latency and proximity

* Security and regulatory compliance

* Service Level Agreements (SLA)

And finally, the most important is the **Cost**

<img width="365" alt="aws region" src="https://user-images.githubusercontent.com/85270361/123522699-e045e100-d6b6-11eb-8d15-690462f391d7.PNG">


**Click on "Services" at the upper left corner and you will see the all the Services available on AWS. Click on "EC2"**


<img width="891" alt="aws services" src="https://user-images.githubusercontent.com/85270361/123523149-cf4a9f00-d6b9-11eb-9611-e1669ecf5f9c.PNG">


**select ec2 stroll down, and Click on "Launch Instance."**

<img width="934" alt="awe select ec2 instance" src="https://user-images.githubusercontent.com/85270361/123523381-14230580-d6bb-11eb-8263-717e39e960d9.PNG">



**Launch a new "EC2" instance of t2.micro family with Ubuntu Server 20.04 LTS(HVM) 64 bit**


<img width="765" alt="aws ubuntu server" src="https://user-images.githubusercontent.com/85270361/123523536-0de15900-d6bc-11eb-9848-c5c47941b7b2.PNG">



**Click on Next: to choose an instance type**


<img width="939" alt="aws t2 micro" src="https://user-images.githubusercontent.com/85270361/123523745-96acc480-d6bd-11eb-83c1-f3d9e7bd3ed5.PNG">



**Next: Configure Instance Details**


<img width="951" alt="aws confi" src="https://user-images.githubusercontent.com/85270361/123524110-015eff80-d6c0-11eb-91d3-6101f7305d9f.PNG">



**Next:** Add Storage; to add or configure the Storage size and type.
Every time you launch an instance from an AMI, a root storage device is created for that instance. The root storage device contains all the information necessary to boot the instance. You can specify storage volumes in addition to the root device volume when you create an AMI or launch an instance using block device.

<img width="951" alt="aws stora" src="https://user-images.githubusercontent.com/85270361/123524647-a7f8cf80-d6c3-11eb-9715-a7f761f7196a.PNG">



**Next**: Add Tags. A tag is a label that you assign to an AWS resource. ... Tags enable you to categorize your AWS resources in different ways, for example, by purpose, owner, or environment. For example, you could define a set of tags for your account's Amazon EC2 instances that helps you track each instance's owner and stack level.



<img width="954" alt="aws add tags" src="https://user-images.githubusercontent.com/85270361/123524992-c8c22480-d6c5-11eb-872a-34324a6a75b9.PNG">



Click Next: Configure Security Group; A security group acts as a virtual firewall for your EC2 instances to control incoming and outgoing traffic. Inbound rules control the incoming traffic to your instance, and outbound rules control the outgoing traffic from your instance. When you launch an instance, you can specify one or more security groups.


<img width="960" alt="ASW SG" src="https://user-images.githubusercontent.com/85270361/123525303-7aae2080-d6c7-11eb-9d52-36629367bd6d.PNG">



**Next:Review Instance Launch**


<img width="960" alt="AWS REVIEW AND LAU" src="https://user-images.githubusercontent.com/85270361/123525425-759da100-d6c8-11eb-83f1-e486807ade7b.PNG">



Before you launch an instance, you need to select a key pair which is then required for SSH access to the Server.

To create a new key-pair, Select "Create a new key-pair" from the drop down menu, give a name to the key-pair, and download it.

**IMPORTANT - save your private key (.pem file) securely and do not share it with anyone! If you lose it, you will not be able to connect to your server ever again!**

As for me, I already created a key-pair, so I selected "Choose an existing key-pair" and i checked the acknowledgment box


<img width="544" alt="aws keypair" src="https://user-images.githubusercontent.com/85270361/123525635-1b054480-d6ca-11eb-8490-f38421871846.PNG">



**Click on "View Instance" to check the Instance State and other details.**


<img width="960" alt="aws view instance" src="https://user-images.githubusercontent.com/85270361/123525784-33c22a00-d6cb-11eb-92a3-c4d0dc76d1f3.PNG">



The next phase is to view your instance state, click on your instance to view it. 
At this stage, you will see if your instance is running or still pending. mine is running, now i can view my instance details



<img width="960" alt="aws instance runnin" src="https://user-images.githubusercontent.com/85270361/123526012-f5c60580-d6cc-11eb-9605-f179070c74c3.PNG">




**Next** is to connect my instance to an SSH Client. 
In my own case, am using MOBAXTERM, you can decide to use PUTTY or any other existing ones.
And to connect to MOBAXTERM, you need to copy the public ip address of the instance you want to ssh to



<img width="957" alt="aws public ip address" src="https://user-images.githubusercontent.com/85270361/123527017-d41c4c80-d6d3-11eb-8d58-3ba2e6d517a4.PNG">


**Next** i opened my MOBAXTERM, i clicked on SESSION, SSH, on the REMOTE HOST i pasted my public-ip address i copied from my instance.
i checked the box and i specify username as (ubuntu)


<img width="715" alt="aws mobaxterm" src="https://user-images.githubusercontent.com/85270361/123539880-d0b8ad80-d733-11eb-9e56-5c7987027c81.PNG">



**Next** i clicked on ADVANCE SSH settings, i checked the box for private key, and i browse my downloaded key.pem 
next i clicked on OK

<img width="766" alt="Capture" src="https://user-images.githubusercontent.com/85270361/123540371-85ec6500-d736-11eb-8182-7cdf1c4b715f.PNG">



For a web application to work smoothly, it has to include an operating system, a web server, a database, and a programming language. The name LAMP is an acronym of the following programs:

```
* Linux Operating System
* Apache HTTP Server
* MySQL database management system
* PHP programming language
```

### In this project, I will implement a web solution based on LAMP stack on a Linux server by implementing the steps below:


# Step 1 — Installing Apache and Updating the Firewall
* We need to Install Apache using Ubuntu’s package manager, apt:


```
$ sudo apt update

$ sudo apt install apache2
```

**To verify that apache2 is running as a Service in our OS, use following command**

```
 sudo systemctl status apache2
 ```


<img width="689" alt="APACHE IS RUNNING" src="https://user-images.githubusercontent.com/85270361/123540764-900f6300-d738-11eb-9dcd-b84937be10ef.PNG">



Before we can receive any traffic by our Web Server, we need to open TCP port 80 which is the default port that web browsers use to access web pages on the Internet

To open our port 80, i went back to the instance, clicked on security, clicked on edit inbound rules and i add rules.
i added port 80 for http and port 443 https and i cliked on save rules

**see my output:**


<img width="954" alt="SG" src="https://user-images.githubusercontent.com/85270361/123543505-c0f69480-d746-11eb-97de-f08427ec7bb5.PNG">

## Our server is running and we can access it locally and from the Internet (Source 0.0.0.0/0 means ‘from any IP address’).
 
* To verify and check that we can access it locally in our ubuntu shell and from the internet, run:

```
$ curl http://localhost:80
or
$ curl http://127.0.0.1:80
```


**As an output you can see some strangely formatted test, do not worry, we just made sure that our Apache web service responds to ‘curl’ command with some payload.**

Open a web browser of your choice and try to access following url


```
http://<Public-ip-address>:80
```

*  **Another way to retrieve your Public IP address, other than to check it in AWS Web Console, is to use the following command.**

```
$ curl -s http://169.254.169.254/latest/meta-data/public-ipv4
```

* If you see the following page, then your web server is now correctly installed and accessible through your firewall. 


**see my output:**

<img width="935" alt="apache test page" src="https://user-images.githubusercontent.com/85270361/123543890-9d344e00-d748-11eb-9f8c-b362bcfbd349.PNG">



# STEP 2 - Installing MySQL

### We need to install the database system to be able to store and manage data for our website. MySQL is a popular database management system used within PHP environments.

* To install mysql-server, run:

```
sudo apt -y install mysql-server
```

* After the installation it is recommended that we run a security script that comes pre-installed with MySQL. This script will remove some insecure default settings and lockdown access to our database system.
* Start the interactive Script by running:


```
sudo mysql_secure_installation
```


* This will ask if you want to configure the VALIDATE PASSWORD PLUGIN.


## Note: Enabling this feature is something of a judgment call. If enabled, passwords which don’t match the specified criteria will be rejected by MySQL with an error. It is safe to leave validation disabled, but you should always use strong, unique passwords for database credentials.



Answer Y for yes, or anything else to continue without enabling.


```
VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No:
```

* If you answer “yes”, you’ll be asked to select a level of password validation. Keep in mind that if you enter 2 for the strongest level, you will receive errors when attempting to set any password which does not contain numbers, upper and lowercase letters, and special characters, or which is based on common dictionary words.



### <p> If we enabled password validation, we’ll be shown the password strength for the root password we just entered and our server will ask if we want to continue with that password. If we are happy with our current password, enter Y for “yes” at the prompt:</p>



### For the rest of the questions, We press Y and hit the ENTER key at each prompt. This will remove some anonymous users and the test database, disable remote root logins, and load these new rules so that MySQL immediately respects the changes we have made.



when you are done, you will get this **output:** 


<img width="714" alt="sql pluin" src="https://user-images.githubusercontent.com/85270361/123550451-66b8fc00-d765-11eb-814c-81fc9d924aea.PNG">


* When you're finished, test if you're able to login to the MySQL Console by typing:

```
sudo mysql
```



<img width="728" alt="sql data" src="https://user-images.githubusercontent.com/85270361/123550542-ec3cac00-d765-11eb-951c-362255c783fe.PNG">


* To exit the MySQL Console, type: exit

```
mysql> exit
```

### Setting a password for the root MySQL account works as a safeguard, in case the default authentication method is changed from unix_socket to password. For increased security, it’s best to have dedicated user accounts with less expansive privileges set up for every database, especially if we plan on having multiple databases hosted on our server.


### *Note*: At the time of this writing, the native MySQL PHP library mysqlnd doesn’t support caching_sha2_authentication, the default authentication method for MySQL 8. For that reason, when creating database users for PHP applications on MySQL 8, we’ll need to make sure they’re configured to use mysql_native_password instead. We’ll demonstrate how to do that later.


### Our MySQL server is now installed and secured.


* Next, we will install PHP, the final component in the LAMP Stack.



## Step 3 — Installing PHP


### We have Apache installed to serve our content and MySQL installed to store and manage our data. PHP is the component of our setup that will process code to display dynamic content to the final user. In addition to the php package, we’ll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases. We’ll also need libapache2-mod-php to enable Apache to handle PHP files. Core PHP packages will automatically be installed as dependencies.


* To install these 3 packages at once, run:


```
$ sudo apt -y install php libapache2-mod-php php-mysql
```

* Once the installation is finished, you can run the following command to confirm your PHP version:

```
php -v
```

<img width="502" alt="php" src="https://user-images.githubusercontent.com/85270361/123551074-1e4f0d80-d768-11eb-8216-5cc6c6656197.PNG">


* At this point, your LAMP stack is completely installed and fully operational.
* To test our setup with a PHP Script, it's best to setup a proper Apache Virtual Host to host our website's file and folders.
Virtual Host allows you to have multiple websites located on a single machine and users of the websites will not even notice it.

![image](https://user-images.githubusercontent.com/85270361/127688747-88a3d098-3df5-4ea0-a8fe-fb55b5bec192.png)


* We will configure our first Virtual Host in the next step.



## Step 4 — Creating a Virtual Host for your Website using Apache

In this project, you will set up a domain called projectlamp, but you can replace this with any domain of your choice.


Apache on Ubuntu 20.04 has one server block enabled by default that is configured to serve documents from the /var/www/html directory. We will leave this configuration as is and will add our own directory next next to the default one.


Create the directory for projectlamp using ‘mkdir’ command as follows:

```
sudo mkdir /var/www/projectlamp
```

Next, assign ownership of the directory with the $USER environment variable, which will reference your current user.

```
$ sudo chown -R $USER:$USER /var/www/projectlamp
```

* We can now open a new configuration file in Apache’s sites-available directory using our preferred command-line editor. Here, we’ll be using vi

```
$ sudo vi /etc/apache2/sites-available/projectlamp.conf
```

This will create a new blank file. Paste in the following bare-bones configuration by hitting on i on the keyboard to enter the insert mode, and paste the text:


<img width="719" alt="vi file" src="https://user-images.githubusercontent.com/85270361/123552786-a71d7780-d76f-11eb-9be1-01aeca3c9b70.PNG">


To save and close the file, simply follow the steps below:

* Hit the esc button on the keyboard
* Type :
* Type wq. w for write and q for quit
* Hit ENTER to save the file


#### You can use the *ls* command to show the new file in the sites-available directory

```
$ sudo ls /etc/apache2/sites-available
```


* see my output

<img width="596" alt="conf" src="https://user-images.githubusercontent.com/85270361/123552945-9a4d5380-d770-11eb-80b5-cf6061818d71.PNG">


### With this VirtualHost configuration, we’re telling Apache to serve propitixhomes.local using */var/www/projectlamp* as the web root directory. If we like to test Apache without a domain name, we can remove or comment out the options ServerName and ServerAlias by adding a # character in the beginning of each option’s lines. Adding the # character there will tell the program to skip processing the instructions on those lines.



You can now use a2ensite command to enable the new virtual host:

```
$ sudo a2ensite projectlamp
```


<img width="683" alt="reload" src="https://user-images.githubusercontent.com/85270361/123553211-c0272800-d771-11eb-9687-2cf134a811a0.PNG">


* We might want to disable the default website that comes installed with Apache. This is required if we are not using a custom domain name, because in this case Apache’s default configuration would overwrite our virtual host. To disable Apache’sdefault website use a2dissite command, type:


```
$ sudo a2dissite 000-default
```


<img width="572" alt="disable" src="https://user-images.githubusercontent.com/85270361/123553386-cc5fb500-d772-11eb-9574-b6d1053de01f.PNG">


* To make sure your configuration file doesn't contain syntax errors, run :

```
$ sudo apache2ctl configtest
```


<img width="536" alt="ok" src="https://user-images.githubusercontent.com/85270361/123553507-645d9e80-d773-11eb-9c25-b23f9acf7d78.PNG">


* Finally, reload Apache so these changes take effect:

```
$ sudo systemctl reload apache2
```


Your new website is now active, but the web root /var/www/projectlamp is still empty. Create an index.html file in that location so that we can test that the virtual host works as expected:


* Type and run :

```
$ sudo vi /var/www/projectlamp/index.html
```

see my input :


<img width="662" alt="ann" src="https://user-images.githubusercontent.com/85270361/123554661-e9978200-d778-11eb-9d1c-8d62b4dfab8e.PNG">


Now go to your browser and try to open your website URL using IP address:

```
http://<public-ip-address>:80
```
or you can also browse using your public dns. the result is the same

```
http://<Public-DNS-Name>:80
```

see my output :

<img width="631" alt="it works" src="https://user-images.githubusercontent.com/85270361/123555103-81966b00-d77b-11eb-8ac2-1d964b4cad30.PNG">



You can leave this file in place as a temporary landing page for your application until you set up an index.php file to replace it. Once you do that, remember to remove or rename the index.html file from your document root, as it would take precedence over an index.php file by default.


* To check your Public IP from the Ubuntu shell, run :

```
$(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 
$(curl -s http://169.254.169.254/latest/meta-data/public-ipv4)
```


## Step 5 — Enable PHP on the website


With the default DirectoryIndex settings on Apache, a file named index.html will always take precedence over an index.php file. This is useful for setting up maintenance pages in PHP applications, by creating a temporary index.html file containing an informative message to visitors. Because this page will take precedence over the index.php page, it will then become the landing page for the application. Once maintenance is over, the index.html is renamed or removed from the document root, bringing back the regular application page.

In case you want to change this behavior, you’ll need to edit the /etc/apache2/mods-enabled/dir.conf file and change the order in which the index.php file is listed within the DirectoryIndex directive:

```
sudo vim /etc/apache2/mods-enabled/dir.conf
```

<IfModule mod_dir.c>
        #Change this:
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm
        #To this:
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index.htm
</IfModule>


After saving and closing the file, you will need to reload Apache so the changes take effect:

```
$ sudo systemctl reload apache2
```


* Finally, we will create a PHP Script to test the PHP is correctly installed and configured on our Server.
* Now that we have a custom location to host our website's files and folders, we'll create a PHP test script to confirm that Apache is able to handle and process requests for PHP files.
* Create a new file named index.php inside our custom web root folder:

```
$ vim /var/www/projectlamp/index.php
```

This will open a blank file. Add the following text, which is valid PHP code, inside the file:

```
<?php
phpinfo();
```

<img width="744" alt="p" src="https://user-images.githubusercontent.com/85270361/123558938-0d66c200-d791-11eb-8ee2-b87069d183c1.PNG">


## When you are finished, save and close the file, refresh the page and you will see a page similar to this :



<img width="943" alt="Capture p" src="https://user-images.githubusercontent.com/85270361/123559012-78b09400-d791-11eb-9fae-2baad31d34b0.PNG">


* This page provides information about your server from the perspective of PHP. It is useful for debugging and to ensure that your settings are being applied correctly.

* If you can see this page in your browser, then your PHP installation is working as expected.

* After checking the relevant information about your PHP server through that page, it’s best to remove the file you created as it contains sensitive information about your PHP environment -and your Ubuntu server. You can use rm to do so:


```
$ sudo rm /var/www/projectlamp/index.php
```
