### This is only a personal study note, written in my second language, and it might consist of wrong concepts/errors ###
Kubernetes service such as Load Balancer (LB) is required to expose application to internet. 
Depending on the requirement of the app or service, there are alternatives for online deployment.
LB is suitable for apps and services that need high availability, scalability, 
traffic management, security or redundancy 
(* redundancy - LB make sure requests are directed to healthy instance by
detecting and redirecting traffic away from instances with issues.)


To create the service that is available over internet:
1) Start a tunnel in a terminal by running "minikube tunnel" and keep it open

2) key in "kubectl apply -f (name of service file).yaml" in a separate tab/terminal
to apply service.yaml file and create a service

3) "kubectl get services -n (name of namespace)" -> this command displays informations of services.
There are 2 types of IP address being shown: 
   i) IP inside of the cluster, 
   ii) External IP

4) paste External IP onto browser and it will call out JSON Object from the pod

5) minikube tunnel can be stopped by pressing "Ctrl" and "C"
-> when tunnel is stopped, JSON Object won't be connecting online


More info:
 
In this exampple, 
External IP = 127.0.0.1 -> this IP is the local host of any local computer
-because that minikube works exclusively with local computer, 
IP addresses we get are not available across the internet 
-> so we need to activate tunnel to show it online 

- if a load balancer is created with cloud providers such as Google Cloud or AWS,
an IP address that is available online will be created instead -> doesn't need tunnel


Potential Error:

the local host address is not working online/Object from pod is not shown on browser: 
check the minikube tunnel and it may ask you to enter password
