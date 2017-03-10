+++
tags =  ["php", "laravel"]
categories = ["dev"]
title = "Debug PHP with Eclipse PDT and Netbeans"
draft = true
+++

## PDT and Netbeans

> PDT and Netbeans are two most popluar free PHP IDEs. We choose such IDE for productivity, so code intelligence and debug are two key factors, which let us love IDE. Because both are not created for PHP development at the start, there is no built-in server to support the PHP web debug. When we want to use it to debug, we would come across some wierd problems. Here is how to prepare the IDE for PHP debug. 

## AMP package or without AMP

### Use AMP package as smart choice 

* If you haven't installed install any MySQL, Apache, PHP on your computer, I will recommend you to choose AMP ( Apache, MySQL, PHP ) package first, especially when project is small, the time is so tight, your client just want you to do some minor change. In that scenario, AMP package is a much better choice. Popular AMP packages include : EasyPHP, MAMP, WAMP, XAMPP. You can pick any of them on your favor.  

* Here is not going to discuss any specific AMP package. You can find more detailed instruction from their official website. If you still have problem, you can take a look how to do without the AMP package, but I won't guarantee you the solution below will work for your AMP.  

### Manage your shits without AMP package

* Here we just focus on how to work with shits ( Apache, PHP ) which you download and install them piece by piece. 10 years ago, it was easier to choose which one to download and install, because there was no much option, but now there are many options which make us confused.  

* The more worst and nastiest problem today is compatible issue between x86 and x64 applications in Windows. Even sometimes they are claimed compiled as x86, until you test it you will never they are really compatible. The reason is Windows has different versions of C++ redistributed compiler, if you use different compilers from Windows to compile your source code, you cannot ensure they are compatible to work together. 

* To avoid this problem, it is better to make sure the package or software are compatible at the beginning. That is why the AMP package is much better and easy to do that. They help you solve such nasty problem by bundling all you need together. 

* Download the compatible packages, especially Apache and PHP. When you download PHP, you need to know the PHP is compiled by VC9, VC11, or VC14, and x86 or x64. After that, you need to download proper Apache from [here](https://www.apachelounge.com/download)

## Assumption

### Apache path `c:\apache`. Version 2.4.x, VC11, x86
### PHP path `c:\php`, Version 5.6.x, VC11, x86
### Use `localhost:1234` as test website URL
### Website path `c:\phpsite`

## Prepare PHP for debugging

### Download XDebug and install it

* Go to xdebug [site](xdebug.org). Use the [wizard tool](https://xdebug.org/wizard.php) to find the xdebug tool. 

* Type `c:\php\php.exe -i | clip` to copy the php info to memory. And then paste the content to the input area, and click `Analyse my phpinfo() output`. It will show the correct file to download. 

* Download the dll file and put it into php folder `c:\php\ext`. Update the `php.ini` file by adding the following lines at the bottom of file. 

```ini
[XDebug]
zend_extension="c:/php/ext/php_xdebug-x.x.x-x.x-vcxx.dll"
xdebug.remote_enable=1
xdebug.remote_host=localhost
xdebug.remote_port=9000
xdebug.remote_autostart=1
xdebug.remote_connect_back=1
```

### Setup Apache to load PHP

* Add php module loading 

```apache

# Update apache root
# ServerRoot "c:/Apache24"
ServerRoot "c:/apache"

# Change origin 80 to 1234
# Listen 80
Listen 1234

# Add ServerName
ServerName localhost:1234

# Add PHP directory
PHPIniDir "C:/php"

# Add PHP module and handler
LoadModule php5_module "c:/php/php5apache2_4.dll"
AddHandler application/x-httpd-php .php

<FilesMatch \.php$>
      SetHandler application/x-httpd-php
</FilesMatch>

# Change origin doc root htdocs 
# 
DocumentRoot "c:/phpsite"

<Directory "c:/phpsite">
    Options Indexes FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>
```


## Debug PHP with PDT 





## Debug PHP with Netbeans 
