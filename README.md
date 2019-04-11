<h1 align="center">
  <a href="https://www.ndi.org/"><img src="https://www.ndi.org/sites/all/themes/ndi/images/NDI_logo_svg.svg" alt="NDI Logo" width="200"></a>
</h1>

<h1 align="center">
  Fix My Community
</h1>

  ### Table of Contents
  1. [Installation](#installation)
  1. [Additional Configuration](#additional-configuration)

This repository contains themeing and configuration files for FixMyCommunity, NDI's version of FixMyStreet. The instructions below explain how to install FixMyStreet and apply the customized themeing.

### Installation

The latest version of MySociety's code for FixMyStreet can be found at: https://github.com/mysociety/fixmystreet

The only dependency needed to run FixMyStreet is Docker and Docker-compose. Instructions for installing Docker can be found here (for ubuntu): https://docs.docker.com/install/linux/docker-ce/ubuntu/ . Instructions for installing docker-compose can be found here: https://docs.docker.com/compose/install/


Begin by installing both this repository along with the latest version of fixmystreet with the commands below. 
```
git clone https://github.com/mysociety/fixmystreet.git
git clone https://github.com/nditech/fixmycommunity-demo-themes.git
```

Then, move the docker overide file into the fixmystreet folder with the command below. This file tells fixmystreet where to find the custom theme and config file.
```
mv fixmycommunity-demo-themes/docker-compose.override.yml fixmystreet/docker-compose.override.yml
```

Now, start up FixMyStreet 
```
cd fixmystreet
sudo docker-compose up
```

This commands will start the application and launch four containers: nginx, memcached, postgres, and the FixMyStreet application itself.

By default, the site should then be available at localhost:8000 when installed locally, or at port 8000 if deployed on a server (*server-ip*:8000). The site should be spun up using the custom theme.

### Additional Configuration

For more detailed information on installation and themeing of FixMyStreet, go to https://fixmystreet.org/overview/

