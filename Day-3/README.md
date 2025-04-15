-terraform is a
-whenever we want to create a cloud resources like ec2,subnets, loadbalancers, database servers, any resources by using automation or script we are using terraform
step1 - install terraform on your windows mission
step2 - we have to set terraform path
step3 - configure aws credentials from CLI, install aws CLI 




install terraform in windows->1st one->windows 386 download->go to program files->create a folder terraform->go to zipfile downloaded one->extract all->browse->select the terraform forlder->select->extract->now copy the path and paste in environment variables->check the version in cmd->terraform --version->


search aws cli install on windows->1st one->windows dropdown->1st link(msi)->open it-> next next->install->go to cmd -> aws --version->


aws login->security, identity->iam->users->create users->user name->next->attach policies->search ec2 and select amazonec2fullaaccess->vpc->amazonvpcfullaaccess->create->open user(shri)->security credentials->create access key->1st one->tick the box->next->download->then go to cmd->aws configure->open the downloaded sheet and copy the key and paste and the rest also->then got to global copy any region(ap-south-1) and paste->


-when writing terraform files we have to create bloacks
step1 - provider block it defines in which cloud you are doing automation
step2 - resource block, what kind of resource that you want to create in cloud
step3 - variable block, want to pass any parameters as variables
step4 - output.tf file, if we want to print o/p in console like public ip address or pvt ip address or instance name,id
when creating instance using terraform scripts 5 parameters have to be passed
1.amazon id 
2.instance type
3.key pair name
4.storage
5.instance name



create a folder anywhere->open it in vs code->create a new file(.tf)->go to extension->install harshicorp terraform->code in .tf->

aws account->menu->ec2->change it same region->ami change to kernel and copy the id there(ami-0ad8ebb39030577b4)->and paste in ami of the code->then key pair->dropdown ->copy any key pair and paste in script or code(if key pair is not there then create a key pair)

commands to run in termainal
1.terraform init - will initialise terraform backend configuration with a cloud api, it is going to generate one license key to authenticate cloud provider api as well as it is going to create .terraform folder which contains the license and necessary files
2.terraform validate - any syntax error
3.terraform plan - 
4.terraform apply - creates aws instances
5.terraform destroy - will delete all the resources automatically
(check terraform.tfstate)
6.terraform apply(check terraform.tfstate)
(check in instances in aws)
(create 3 instances now (hw))


when execute a command terraform plan command it will create terraform.tf state file which contains current state of the infrastructure

whenever creating vpc it should contain name and ip address range and tanacy

chatgpt
create terraform script to implement the aws architecture create a vpc name of the vpc should be shrijith-vpc cidr block of the vpc should be 10.0.0.0/16 tenacy should be default, create a subnet within the vpc cidr block should be 10.0.1.0/24, subnet name shrijith-subnet, available zone should be (zone) implement this script like main.tf, variable.tf,output.tf
- you will get the code and paste it in the respective files

main - provider
variable - regional
delete these from thise files
then execute the commands




-docker is a  containation tool which can help us to create portability application to use resources effectively to create platform independent application we are going with docker
-docker is going to perform os level virtualisation technique
-we are going to use docker to reduce the cost of the server, to run the application wherever we want we are going with something called as docker
-application will divide into the modules called as micro service, each and very micro service will have separate docker image,container, file 
-every micro service application will deploy in container
monolithic application is nothing but it is single tier application which means web, application, database server we are combine together and we are deploying in a single server

issues with a monolithic application
if any module goes wrong then --- it has tightly coupled nature
if one service goes down then entire application will go down that's a reason we are moving towards the micro services
what is micro services- we will breakdown application into the independent services that's called loosely coupled application. if any one service goes down only customer will not be abled access the service remaining services will go as it is
there are some issues with microservice
-each micro service will require single server therefore costing goes higher
-to reduce the cost to effectively use the resources, to create a platform independent application, to create portable of application
-build once run anywhere


install docker for windows->

