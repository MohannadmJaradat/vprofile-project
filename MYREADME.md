1. To start containerizing our project, first we need to gather the services used and their versions.
2. Then we can go to Dockerhub and match the required version with the suitable image tag.
3. To run the virtual machine, open a git bash terminal in the path where your Vagrantfile is located.
4. Make sure no other virtual machines are running using `vagrant global-status`, you can turn off and destroy other virtual machines using `vagrant destory`. Then you can run the vagrant file using `vagrant up`.
5. Once the virtual machine is up, you can ssh into it using `vagrant ssh`. Once you are in the virtual machine, use the offial docker docs to instal docker engine on your ubuntu virtual machine https://docs.docker.com/engine/install/ubuntu.
6. To give a use the ability to interact with docker without using `sudo`,you can use the following command `usermod -aG docker <your-user>`, which adds your user to the docker group.
7. Once you are done with your virtaul machine, you can use `vagrant halt` to turn it off.
8. You can use this as a reference to build a docker image https://docs.docker.com/reference/dockerfile/
9. We will created 3 new repositoires in docker hub, vprofileapp, vprofiledb, and  vprofileweb