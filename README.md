# Linux-server-configuration

Fully updated and secured webserver, hosting the backend of the item_catalog web application. 

## Description

This readme details the setup process for the webserver. The backend of the item_catalog web application is reachable at this url: 
http://ec2-52-34-70-105.us-west-2.compute.amazonaws.com/

The webserver is installed on a linux distribution, on a virtual machine. 

**Note** : the backend is hosted on a temporary amazon web service instance. If the url doesn't work, it may mean that the instance has expired.

## Project Access
#### IP address

**`52.34.70.105`**

#### SSH Port

**`2200`**

#### Web Application URL
http://52.34.70.105/  

* AWS-Server: 
http://ec2-52-34-70-105.us-west-2.compute.amazonaws.com/
 
## Installed Packages

Package Name | Description
-----------: | :----------
**apache2** | HTTP Server
**libapache2-mod-wsgi** | hosts Python applications on Apache2 server
**finger:** | Displays an easy to read information about a user
**postgresql** | Postgresql Database server
**git** | Version control system tools
**python-pip** | An easy-install package to facilitate installing Python packages
**python-psycopg2** | PostgreSQL adapter for Python
**unattended-upgrades** | Tool to automatically update to the stable versions of installed packages


## Configuration Summary

- Setup Virtual Machine and SSH into the server.
- A new system user `grader` was created with permission to sudo.
- All currently installed packages were updated and upgraded.
- CRON tasks added to `update` and `upgrade` installed packages.
- Changed SSH Port from `22` to `2200` and configure SSH access.
- Configured `UFW`to only allow incoming connections for `SSH(Port:2200)`, `HTTP(Port:80)` and `NTP(Port:123)`.
- Configured local Time Zone to `UTC`.
- Installed and configure `Apache` and `mod_wsgi`
- Installed Git, cloned the item catalog application 
- Configured `Apache` and `mod_wsgi` to serve the item catalog application
- Installed and configured `PostgreSQL` with default settings to *not* allow remote connection.
- Created a new user `catalog`, added user to PostgreSQL databse with limited permissions to catalog application database.

## Third party ressources used to complete the project

- A big thanks to code reviewer Ellis Enobun, who made available a [detailed walkthrough](https://github.com/elnobun/Linux-Server-Configuration/blob/master/README.md) of steps he took to finish this project, which helped me a lot.
- [django documentation on how to deploy an app using wsgi](https://docs.djangoproject.com/en/1.10/howto/deployment/wsgi/) 
- [django documentation on how to use postgresql](https://docs.djangoproject.com/en/1.10/topics/install/#database-installation)
- [digital ocean guide on how to use django](https://www.digitalocean.com/community/tutorials/how-to-run-django-with-mod_wsgi-and-apache-with-a-virtualenv-python-environment-on-a-debian-vps)
- [digital ocean guide on how to install postgresql](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-14-04)





