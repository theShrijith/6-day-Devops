wsl --update


after creating instance and doing setups in putty
->sudo su
->yum install docker -y
->docker --version
->service docker status
->service docker start
->

environment is a server where we run the application
dev environment - where s/w developer tests the minimal 
testing environment - where s/w testing team perform the functional test cases non formal test cases and perform the performance, testing, load testing and all the test cases
UAT(user accepted test) environment - before release of product into the market we have to show prototype to the customers
production environment - where we can actually deploy the application so that customer can access the application

what is container -> it is a server where actually we run the application 

docker file is a text document it contains set of instructions how to run an application in a container
the instructions are -> build commands
1]FROM ->this will define base image or parent image of the application
	 every docker file must start from the FROM instruction
2]COPY ->to copy a file or directory from local mission into docker image
3]ADD  ->it is same as COPY instruction 
	 downloading packages from internet to docker image
4]RUN  ->it is going to help to download the dependency packages or install packages in a container
5].DOCKERIGNORE ->if we want to remove unnecessary packages or files while we are building a docker image we are going to use DOCKERIGNORE

run commands ->
1]CMD ->this defines which code or which artifact to run in container
2]ENTRYPOINT ->this defines entry of the application, CMD instruction will allow run time arguments, ENTRYPOINT will not allow the runtime arguments
3]EXPOSE ->it defines on which port number we want to access the application
4]ENV ->this defines environment variable of the application 
5]USER - if we want to create user account we are going to use the USER instruction

*note*->
work directory - defines keep the files inside the container


docker image is a template it contains what we need to run the application, it contains source code, dependency, configuration files, library files, on which platform we want to run our application (
docker hub is a registry where we can store all the docker image


to create container ->
->docker create ubuntu /bin/bash (creates docker image)
->docker ps -a (it shows all the containers irrespective of the state)
->docker start (container id i.e 4a2f8e97582c)
->docker ps (it will show the running containers)

->docker create -it --name webserver amazonlinux /bin/bash
->docker ps -a
->docker start webserver
->docker ps
->docker exec -it webserver /bin/bash(to go inside the container)
->ls
->exit(to come out of the container)
->docker run -it --name sample ubuntu /bin/bash
->ctrl+p+q (to come out of the container)
->docker ps
->docker run -td --name web-app -p(defines port number) 3002:3000 muralisocial123/cart-page-test:1.0
->docker ps
go to aws->instances->click on instance id->copy public ipv4 address->paste in browser :3002->go down in instances->security->inbound rules->edit inbound rules->add rule->all tcp->anywhere ipv4->save->now refresh the copied ipv4 address page


post port number is a user choice we can give any port b=number whichever the user likes it. This port number defines how to access application from server 



GitHub.com/Msocial123->dimple repository->fork->untick main branch->create fork->copy url->open powershell->git clone -b master link(this will clone)->open vs code->open folder->c drive->users->SHRIJITH->dimple repository->select


now go to server(putty that the set up is already done)->yum install git -y->git clone -b master link(this will clone)->ls->cd and give the folder name which we got from typing ls->
->docker build -t web-app-nodejs:1.0 .
->docker images
->docker inspect web-app-nodejs:1.0
->docker images
->docker run -td --name node-app -p 3015:3015 web-app-nodejs:1.0
->docker ps
->copy the public ipv4 address:3015 in browser 


hub.docker.com->
server->
->docker ps
->docker exec -it web-app /bin/bash
->ls
->exit
->docker images
->docker login(provide username and password)
->docker images
->docker tag web-app-nodejs:1.0 sj/web-app-nodejs
->docker images
->docker push sj/web-app-nodejs
->docker images
(->go to hub.docker.com->menu->docker hub)
->docker stats



6 steps
1]identify the base image of the application
2]create a work directory
3]copy the dependency into the docker image
4]install the dependency
5]copy whole source code from local mission into docker image
6]define the expose port number
7]mention which port we have to run in a container


assignment
1]develop a website using chatgpt and write a docker file deploy in ingenex server
2]identify the problems with a container
3]digitalbank
