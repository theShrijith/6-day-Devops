connect to the last day instance(shrijith-bastionshot)
-sudo su
-kubectl get nodes
-kubectl get namespace
-kubectl get all -n kube-system
-kubectl create ns shri-ns
-kubectl get ns
-kubectl get pods
-kubectl run test-pod --image ngnix --port 80 -n shri-ns
-kubectl get pods
-kubectl get pods -n shri-ns
-kubectl delete pod test-pod -n shri-ns
-kubectl get pods -n shri-ns

-open yesterdays created folder in vs-code (sj-kubernetes-manifests)
-create a file rs.yaml->code->terminal->git add . ; git commit -m "replicasetyamlfile"; git push origin main;
-go to GitHub repository->copy link->git clone https://github.com/theshrijith/sj-kubernetes-manifests.git->ls->cd sj-kubernetes-manifests->git pull->kubectl apply -f rs.yaml

-kubectl get pods -n shri-ns
-kubectl get rs -n shri-ns
-kubectl get pods -n shri-ns
-kubectl describe pod cart-page-rs-75svb -n shri-ns


-go to aws->containers->clusters->compute->test-linux2(name)->dropdown->(selectname)->launch template->dropdown(name)->next->desired size(3)->min(3)->max(5)->enable->next->next->create

-kubectl get rs -n shri-ns
-kubectl delete rs cart-page-rs -n shri-ns

-deployment.yaml->git push

-git pull
-kubectl apply -f deployment.yaml -n shri-ns
-kubectl get deployments -n shri-ns
-kubectl get rs -n shri-ns
-kubectl get pods -o wide -n shri-ns


-service.yaml->push

-git pull

-kubectl apply -f service.yaml -n shri-ns
-kubectl get svc -n shri-ns

a086c3151b9da42b396ade4158e8d53d-1559291561.ca-central-1.elb.amazonaws.com:3002
http://a086c3151b9da42b396ade4158e8d53d-1559291561.ca-central-1.elb.amazonaws.com:3002/



-snap install helm --classic
(the below commands are in monitoring setup.docx)
-helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
-helm repo add grafana https://grafana.github.io/helm-charts
-helm repo update
-helm install prometheus prometheus-community/kube-prometheus-stack \
  --namespace monitoring --create-namespace
-kubectl get pods -n monitoring
-kubectl patch svc prometheus-kube-prometheus-prometheus -n monitoring \
  -p '{"spec": {"type": "LoadBalancer"}}'
-rest steps
-http://a2841783fd5104b7ca4daef50ccada1e-354255227.ca-central-1.elb.amazonaws.com:9090/query
-http://af0c19bfd4f73401ba8193bd496f87ff-847301483.ca-central-1.elb.amazonaws.com/login
username - admin
password - SICjDy1ExOwfihHei68cmWL899eb4hgNoUypvFkt(got from the command)





namespace - dividing cluster into isolated environment
default namespace - it is created automatically Kubernetes to create a resource in a default namespace
kube-node-lease - to check the health of the node Kubernetes master node use lease objects
kube-public - anyone can able to access resources in  this namespace

the time of cluster creation by default all the resources like metric server, cni, core dns, all the resources will create in this namespace

note -> when we are deploying application production servers we will never deploy any application in default namespace

if the pod goes down there are 3 problems we have to face
1]we are going to get application downtime - to overcome this problem we have to attach controller to the pod
2]every pod has own ip address, if pod goes down the ip address will change - for this we have to create services in Kubernetes(it will create static url)
3]if pod goes down along with the pod we are going to lose the data - for this we have to implement volumes in Kubernetes

Replica set ->
it is Kubernetes object it is going to maintain minimum number of nodes 24*7(it is always maintains desired state=actual state)

Replicaset problems - in real time application
deployments - in Kubernetes we are deploying application using deployment objects or deployment controller, it will manage the replicaset, replicaset will manage pods 

if we want to expose application through the web browser Kubernetes will introduce objects called services. 3 types of services
1]cluster ip service
2]node port service
3]load balancer service

monitoring - to understand what's going inside an application we are implementing monitoring dashboards, with the help of this we can recognise id=f something goes wrong in the application, we can identify how much cpu, how much memory consumed by pods, nodes can be identified 
monitoring tools like promotheus, graphana
promotheus - it is a metric server where it is going to collect time series of data, it sends data to graphana dashboard
graphana - with the help of it we can set up monitoring dashboards where we can see our data in the form of pi charts or graphs
