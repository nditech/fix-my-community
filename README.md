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

By default, the site should then be available at localhost:8000 when installed locally, or at port 8000 if deployed on a server (*server-ip*:8000) 

### Adding themes and configuration

The site when first installed will run with the default configurations and themeing. The files contained in this repository are located in directories corresponding to where they belong in the FixMyStreet directory configuration.

To edit the configurations and themeing for the site, **files must be edited inside the docker container, not locally in the directory that was cloned from github**. In order to access the docker container with the application content, use the following command:

`sudo docker exec -it ` *name of the fixmystreet container* ` bash`
(`sudo docker exec -it fixmystreet_fixmystreet_1_499f08dcc4f9 bash` for example)

The name of the fixmystreet container will be something like `fixmystreet_fixmystreet_1_499f08dcc4f9` and can be found using `sudo docker ps` and checking for the name of the container with the image labeled `fixmystreet/fixmystreet:stable`.

Once inside the container, the directory in which the application files are located can be reached using
`cd /var/www/fixmystreet/fixmystreet/`

Once in this directory, the default configuration file can be removed and replaced with the conf/general.yml file from this repository. To remove the original configuration file, use `rm -rf conf/general.yml`. To replace it with the configuration file from this repository, exit the docker container and run the following command from the main folder of this repository:

`sudo docker cp conf/general.yml fixmystreet_fixmystreet_1_499f08dcc4f9:/var/www/fixmystreet/fixmystreet/conf/general.yml` , substituting in the name of your docker container.

To add the themeing files, similarly run the following commands:

`sudo docker cp templates/web/fixmycommunity  fixmystreet_fixmystreet_1_499f08dcc4f9:/var/www/fixmystreet/fixmystreet/templates/web/fixmycommunity`
`sudo docker cp web/cobrands/fixmycommunity fixmystreet_fixmystreet_1_499f08dcc4f9:/var/www/fixmystreet/fixmystreet/web/cobrands/fixmycommunity`

This copies the theme in as a cobrand called fixmycommunity. In the general.yml file in this repository, the fixmycommunity theme is specified as the default.

For more detailed information on installation and themeing of FixMyStreet, go to https://fixmystreet.org/overview/
