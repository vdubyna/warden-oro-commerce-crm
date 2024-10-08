# Warden setup for Oro Platform

This is a setup for Warden to work with Oro Platform.

## Installation

Copy `.warden` directory and `.env` file to your project root.

Execute the following commands:

```bash
# to load recent images from repository
warden env pull 

# to build the images for Oro platform
warden env build 

# to start the environment
warden env up

# to sign the certificate for the domain
warden sign-certificate app.orocrm.test 
```
At the moment installation includes the following services:
* PHP 8.3
* Nginx
* PostgreSQL 15.1
* Redis 6.2
* Node 20.10.0
* Composer 2.*

Website should be available at `https://app.orocrm.test`

More details are on warden [documentation](https://docs.warden.dev/index.html)

## ORO install

After environment install you can setup oro commerce

```shell
# login into container
warden env shell

# Create project in new directory
composer2 create-project oro/commerce-crm-application my_project_name 6.0.3 -n

# Move project file to document root 
mv my_project_name/* .
mv my_project_name/.* .
rm -rf mv my_project_name

# Set local config
mv .env-app.local.dist .env-app.local 

# Install oro migrations
php bin/console oro:install --env=prod --timeout=2000

```

During installation you will put required credentials. 
When it is done visit `https://app.orocrm.test/admin`

