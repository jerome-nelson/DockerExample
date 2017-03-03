# Docker Container

This is a Docker Build created for NetplayTV dev. environments.


## Steps to Setup Docker Access 
#### Make sure that any VirtualBox products are uninstalled/disabled.
  1. Install Docker for Windows (https://docs.docker.com/docker-for-windows/)
    * Once installed you will need to Share your C drive in Docker Settings.
  2. Next open Hyper-V Manager and create new internal Virtual Switch 
     * This is Windows Only (used to create internal access to Docker Instance)
  3. Visit Network Connections Folder and add static ip to new Virtual Switch (it may not be assigned).
    * https://docs.docker.com/machine/drivers/hyper-v/#example
  4. Run `docker-machine create --driver hyper-v DnetInterface` to create network Config to allow docker containers to connect to VSwitch
  5. Next run `docker-machine start Dnetinterface` to start the docker machine.


## Steps to Setup Dev Environment

#### Databases
   1. Databases can be copied into Docker Build by copying them into `mariadb/dumpfiles` 

#### If Existing Wordpress
   1. Place copy of DB into `mariadb/dumpfiles` and original site into `wpress/backups`
   2. Then run `docker-compose up` to start the containers.