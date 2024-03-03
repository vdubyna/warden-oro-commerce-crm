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
* PHP 8.2
* Nginx
* PostgreSQL 15.1
* Redis 6.2
* Node 18.14.0
* Composer 2.*

Website should be available at `https://app.orocrm.test`

More details are on warden [documentation](https://docs.warden.dev/index.html)

