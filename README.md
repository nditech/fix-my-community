This repository contains themeing and configuration files for FixMyCommunity, NDI's version of FixMyStreet. The instructions below explain how to install FixMyStreet and apply the customized themeing.

### Installation

The latest version of MySociety's code for FixMyStreet can be found at: https://github.com/mysociety/fixmystreet

The only dependency needed to run FixMyStreet is Docker and Docker-compose. Instructions for installing Docker can be found here (for ubuntu): https://docs.docker.com/install/linux/docker-ce/ubuntu/ . Instructions for installing docker-compose can be found here: https://docs.docker.com/compose/install/

FixMyStreet can be installed with the following commands:

```
git clone https://github.com/mysociety/fixmystreet.git
cd fixmystreet
sudo docker-compose up
```

These commands will start the application and launch four containers: nginx, memcached, postgres, and the FixMyStreet application itself.

By default, the site should then be available at localhost:8000 when installed locally, or at port 8000 if deployed on a server (*server ip*:8000) 
