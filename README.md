# freeradius-k8s
cd freeradius-k8s
#Create freeradius Pod using deployment file 
kubectl create -f 01-deployment.yml
#Create freeradius Pod service using services file
kubectl create -f 02-services.yml
#Check Pod status
kubectl get pod -A
#Check service status
kubectl get svc
#Check service description details to get Internal and external NodePort information
kubectl describe svc lb-freeradius -n default
#Identify the worker node on which freeradius Pod is running using below command
kubectl get pods -o wide
#Testing freeradius authentication: Note: The worker node IP on which POD is running need to be used for authentication testing
#Run the below command from all nodes: X denotes IP Address and Port 
radtest testing password X.X.X.X:XXXX 0 SECRET
