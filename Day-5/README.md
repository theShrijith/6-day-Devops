- container will not support autoscaling
-vertical scaling -> it means, we have to increase system resources
-horizontal scaling -> we have to add additional server to existing infrastructure 

-scale down -> whenever the traffic goes slow towards the application we have to remove additional servers
-containers will not support load balancing
-if container is down we are going to get application downtime
-container will not support self healing

-to overcome these problems we are using orchid station tools

-what is Kubernetes -> it is a container management tool or it is going to manage all the containers 
-these perform the automatic deployment of the application
-Kubernetes features
1]orchid station 
2]auto scaling
3]load balancing
4]self healing
-Kubernetes is platform independent, we can run in any cloud
-to perform the automation Kubernetes we are going to write the manifester files

launch instance->ubuntu


steps
1]create a jump server
2]we have to install kubectl, eksctl, aws ali



COMMANDS ->
-go to msocia123 GitHub->EverNorth-DevOps-Training-Material->Install EKSCTL,Kubectl,AWS CLI.sh->copy the code
-go to server
-vi sh->right click
-chmod 777 cluster.sh
-sh cluster.sh
-ls
-sudo su
-sh cluster.sh
-now go to aws->iam->users->create users->shrijith-k8s->access policy->2nd one->create->click on the user created->cli->tick the box->create access key(rearrange this)
-aws configure(fill the details)
-eksctl
-eksctl create cluster --name shrijith-cluster --version 1.31 --region ca-central-1 --nodegroup-name test-linux --node-type t2.micro --nodes 3 --nodes-min 3 --nodes-max 5 --managed


-Kubernetes will manage a application in a cluster
-what is cluster - it is a group of node it contains master nodes and worker nodes
-what is master node- it is a hero of the cluster which is going to take care cluster head
		    - it is responsible for total health
-worker node - it is where we are going to deploy the application in a cluster atleast we should have one master node and one worker node
-2 types of cluster-> on-primises cluster - we have to manage this cluster by ourself, if something goes wrong in application downtime we are responsible
                   -> cloud manage cluster - this cluster manage by the cloud provider manage cluster, if something goes wrong they are responsible for our                                    application
-in aws if we want to create a cluster we have service called eks(elastic Kubernetes server)
-in a master node we have 4 components ->
1]api server - it is a hero of the cluster
2]etcd - where we are going to save information about the cluster, application 
3]controllers - it is responsible for monitoring the health of the application (it always checks the desired stage=the active status)
4]scheduler - it is a component it is going to schedule a pod in a node (pod - Kubernetes will run the application in a pod, it contains containers, is the smallest deployable in kubernetes)

-worker node components ->
1]kubelet - it is responsible for creating pods, it is going to act as a agent, if something goes wrong in worker node it will communicate with master node
2]container runtime - it is responsible for pulling the docker image creating containers, starting the container it is responsible for managing the life  cycle
3]kube-proxy - it is a networking component in a worker node, it is responsible for creating deployments, exposing application to the internet 



-snap install kubectl --classic
-aws eks update-kubeconfig --name shrijith-cluster --region  ca-central-1
-kubectl get nodes
-create a folder(shrijith-kubernetes-manifests)-> open in vs code -> create a file(pod.yaml)->code -> source conrol->initialise->public->terminal->
git add . ; git commit -m "my 1st" 
- git clone https://github.com/shrirakshakr/shrijith-kubernetes-manifests.git
- ls
-cd shrijith-kubernetes-manifests
-kubectl apply -f pod.yaml
-kubectl get pods
-kubectl get pods -o wide



http://afd54a3c9a3594fb7bf64fc96a9edbfa-607550035.ca-central-1.elb.amazonaws.com:3130/
