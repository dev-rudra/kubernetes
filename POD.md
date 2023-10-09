# POD
A Pod is a group of one or more containers (Usually Pod is meant to run one application continer, however you can run multiple containers usually it's only the case if you have one main application container and a helper container or some side service that has to run inside of that Pod), with shared storage and network resources, and specification for how to run the containers. Let's take a look in a points:

* Smallest unit of K8s
* Abstraction over container
* Usually 1 application per Pod
* Each Pod gets its own IP address

![Pod](https://github.com/dev-rudra/Kubernetes/assets/50256921/593ff9af-174f-49e9-b8a5-f56a6e6f72f8)

>**Note** Pod will die easily for example in the following figure the DB pod died, and new one will get created in its place and when that happens it will get assigned new IP address. Which is obviously is inconvenient if you are communicating with the Database using the IP address because now you will have to adjust it every time pod restarts and because of that another component of Kubernetes called service is used.

## Service
Service is basically a static IP address or permanent IP address that can be attached so to say each pod. For example in the following diagram `my-app` will have its own service and `DB` pod will have its own service. Best things is the life cycle of service and the Pod are not connected so even if the Pod dies the service and its IP address will stay so you don't have to change that endpoint anymore.

In Summary
* Permanent IP address
* lifecycle of Pod and Service NOT connected

![Service](https://github.com/dev-rudra/Kubernetes/assets/50256921/8c051757-ac9e-41e2-9f28-7554b32996c1)