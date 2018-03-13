---
layout: post
title:      "WP with LAMP on Linux Server"
date:       2018-03-13 11:15:24 -0400
permalink:  wp_with_lamp_on_linux_server
---


This is going to be a run through of how to get a Word Press site up on Unbutu Server. I use this for getting WP websites up to either test them or simply practice on creating some of these sites. First thing you will need is a virtural machine, I use [Oracle](https://www.virtualbox.org/). Second your going to want to download an [Ubuntu server](https://www.ubuntu.com/download/server) as you will need this file while creating your VM. There are some steps you go through and if you are unsure about what options to choose during the installion refer to [Ubuntu Server Tutorial](https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-server#0).

Once you have your server installed, start up your server(if you havent already) and log in. Also make sure to write down your user name and password as I have forgotten before and had to create a new one. After you log in your going to want to run

```
sudo apt-get update
sudo apt-get install lamp-server^ 
```

This will create your LAMP server and installs Apache2, MySQL and PHP, next you want to go into MySQL and create your database. To get into MySQL type in

`sudo mysql -u root -p`

Once inside MySQL you can use these commands to create your database.

```
 CREATE DATABASE database-name; 
 CREATE USER your-user-name@localhost IDENTIFIED BY 'this-is-your-password';
 GRANT ALL PRIVILEGES ON database-name.* TO your-user-name; 
 FLUSH PRIVILEGES;
```


Then type 'exit' to leave MySQL, next you just need to install WP into the tmp file. Here is the a walkthrough of each command used in order to download and install wordpress. 

```
 sudo cd /tmp
 sudo wget http://wordpress.org/latest.zip
 sudo unzip -q latest.zip -d /var/www/html/
 sudo chown -R www-data:www-data /var/www/html/wordpress
 sudo chmod -R 755 /var/www/html/wordpress
 sudo mkdir -p /var/www/html/wordpress/wp-content/uploads
 sudo chown -R www-data:www-data /var/www/html/wordpress/wp-content/uploads
 ```

Once you have run these WP will be installed and ready to use, to access your site you just need to type this in your browser.

`server-ip-address/wordpress`

If you dont know your ip address you can run

`sudo apt-get install curl`
then:
 `curl http://icanhazip.com`
 
 This will display you ip address, I ran into the issue of having a private address and had to go through a process of port-forwarding. If this happens to you refer to this [page](https://www.digitalocean.com/community/tutorials/how-to-forward-ports-through-a-linux-gateway-with-iptables) as it will walk you through setting that up
 
 Once you are on your website, you will go through the basic setup of Word Press. Remember that when setting up the database name and user name to reference your information from MySQL as this will be the same. Hope this helps for anyone looking to setup a local site!

