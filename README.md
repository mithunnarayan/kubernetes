# kubernetes demo app

Steps to deploy the app into GKE on Google Cloud.

1) Install and set up gcloud,kubectl commandline utility with a new google cloud project. 
2) Install Kops to create and manage Kubernetes cluster. 
3) Launch kuberntes cluster using below command.

kops create cluster   --name=<name>   --state=gs://<bucket to store metadata>   --dns-zone=<dns zone name>  --zones=asia-south1-a

4 ) Change kubectl context to GKE cluster. 

5) clone the repo.

6) create the kubernetes objects using kubectl apply -f k8s/<>.yaml files. 

This will create a Ingress with (tls pre created certs), nginx ingress controller, 2 services ( backend and frontend ) , 2 deployments for frontend and backend. 
The backend runs with tomcat server and fronted run with nginx for static contents. 

7) point the domain to the ingress IP to access the site. 

The app is configured to use persistant volume and its claims at the time of developement. We can enable pod autoscaling, and canary deployment at the time of production release. 


