# geneweb-dev
 
A docker image to develop on [geneweb](https://github.com/geneweb/geneweb) created from the code found [here](https://github.com/geneweb/geneweb/pull/1395) 

To use it :
1. Copy the two files in a directory on your docker host
2. Connect to guacamomle using your local admin account (not root !), go to this directory and run the following commands
   * docker build --tag geneweb-dev --file geneweb-dev.yml --force-rm .
   * docker run -it -p <a host port>:2316 -p <a host port>:2317 -v <a host directory>:/home/opam/geneweb --name geneweb-dev geneweb-dev<br>
     wait few minutes to the container to initialized itself

All the geneweb develpment files will be in the host directory you provided. You can modify them from your host.
To compile just start the container and compile:
* docker start -i geneweb-dev
* make clean distrib

** this image won't work for a SYNOLOGY NAS, use geneweb-syno-dev repository **
