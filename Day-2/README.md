manage jenkin->tls
manage jenkin->plugin->available plugin
	deploy to container - plugin to install
	

Maven IntegrationVersion
3.25
Pipeline Maven IntegrationVersion
1508.v347c4b_692202
Pipeline Maven Plugin APIVersion
1508.v347c4b_692202
Maven Release Plug-inVersion
0.16.4
Maven InfoVersion
0.3.2
Maven InvokerVersion
2.5



program file->tomcat->conf-> tomecat-users -> open with vs code -> roles="manager-gui, manager-script, admin"




-quick
-quality
-lesser spending
-availability


DATA CENTER is a collection of physical servers

IAAS
PAAS
SAAS

AWS provides 
-autoscaling
-availability of services
-on demand

"ELASTIC KUBERNETES SERVICE"

requirements
-OS
-server configuration
-storage

Linux:
-red hat family
install httd
install apachetoserver
yum



AWS->compute->EC2->launch instance-> shrijith-webserver->Amazon Machine Image (AMI)->dropdown->Amazon Linux, kernal-> next dropdown->t2.micro->create a keypair->Shrijith-webserver->RSA->.ppk->create->network settings->edit->security group name->Shrijith-security->description->Shrijith-security->configure storage->30->summary->number of instances->2->launch

putty download->


aws->view all instances->select first one->connect->sshclient->copy example ec2 to end->open putty amd paste in host name->appearance->change font size to 14->ok->connection->seconds between->60->ssh->auth->credential->browse->shriraksha-webserver.ppk->apply->a server will open

--->commands
->visudo->permission denied->so become root user 
->sudo su
->visudo
->shift+:
->wq
->yum install httpd->y
->which httpd(to check if it is installed)
->service httpd status
->service httpd start
->service httpd status
->yum install git -y
->git clone -b master(url-> go to Mpublic123 git account->coursevita retail-> fork -> uncheck copy main-> fork-> copy the url)
(if network is lost restart go top and right click restart session-> sudo su-> ls-> then continue the work)
->ls
->cd (select the directory and) right click
->ls
->cp -r . /var/www/html


instance->instance id-> copy 
instance->security->security group->edit bound rule->second one http-> anywhere ipv4->save 




load balancing->load balancers-> create load balancer->classic load balancer -> create->load balancer name->shrijith-loadbalancer->availability 1st and 2nd->security groups-> select security->advanced health check->healthy threshold 2->add instance first 2->create
