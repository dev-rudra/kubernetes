# Introduction
Kubernetes, often abbreviated as K8s, is an open-source container orchestration platform used for automating the deployment, scaling, and management of containerized applications. It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation (CNCF), which is part of the Linux Foundation.

## What problem does kubernates solve?
Kubernetes solves several problems related to deploying, managing, and scaling containerized applications in a distributed and dynamic environment.

## What features do orchestration tools offer?
1. High Availability (Application has no downtime, user can access at anytime.)
2. Scalability (Applicaton has high performance.)
3. Disaster recovery (backup and restore) (If infrastrucutre has a problem, server explode or something problem, in that case it hase automatic backup and restore.)

# Kubernetes(K8s) Components 
Kubernetes comprises several components that works together to manage containerized applications in a cluster. These components are divided into two main categories:

## Control Plane (Master Components) 
1. **API Server:** The API server is the central management point for the entire Kubernetes cluster. It exposes the Kubernates API, which clients (including kubectl and other Kubernetes components) used to interact with the cluster. It validates and processes requests, communicates with the cluster. It validates and processes requests, communicates with the etcd store, and instructs the other components.
2. **etcd:** is a distributed key-value store that stores the configuration data for the cluster. It serves as Kubernete's backing store for all cluster data, including configuration, metadata, and the state of all objects in the system.
3. **Scheduler:** The scheduler is responsible for placing pods(group of container) onto worker nodes. It selects an appropriate node based on resource requirements, affinity/anti-affinity rules, and other facters, ensuring effficient resource utilization and high availability.
4. **Controll Manager:** The controller manager manages various controllers responsible for regulating the state of the system. Controllers include the Replication Controller, Deployment Controller, and others, which ensure that the desired state of objects is maintained.
5. **Kube-Proxy:** Kube-proxy is responsible for network routing and load balancing within the cluster. It maintains network rules on nodes to forward traffic to the appropriate pods or services. It also provides service discovery through virtual IPs and DNS.

## Node Componets (Worker Components)
1. **Kubelet:** The kubelet is the primary node agent that runs on each worker node. It communicates with the API server to ensure that containers are running as specified in a pod's manifest. It also performs health checks and reports node status.
2. **Container Runtime:** Kubernetes supports various container runtimes, with Docker being the most common. The container runtime is responsible for pulling and running container images, managing containers, and handling low-level container operations.
3. **Kube-Proxy:** While kube-proxy is part of the Control Plane, it also runs as a component on each node. Its role on nodes is to maintain network rules, perform network address translation (NAT), and manage the connectivity between pods and services.
4. **Pods:** Pods are the smallest deployable units in Kubernetes and are not components in the traditional sense. However, they run on worker nodes and consist of one or more containers that share the same network namespace and storage. Pods are where the application containers are deployed.

Additionally, some optional components and add-ons can be part of a Kubernetes cluster, depending on the specific requirements and use cases. These may include:

1. **Ingress Controller:** Manages external access to services within the cluster, typically for HTTP/HTTPS traffic.
2. **DNS Service:** Provides DNS-based service discovery for pods and services within the cluster.
3. **Monitoring and Logging Tools:** Tools like Prometheus for monitoring and Fluentd/ELK Stack for logging are often used to gain insights into cluster health and application performance.
4. **Dashboard:** A web-based UI for managing and monitoring the cluster.
5. **Authentication and Authorization:** Kubernetes can integrate with various authentication and authorization mechanisms, including Role-Based Access Control (RBAC).
6. **Custom Resource Definitions (CRDs):** Allows users to extend Kubernetes by defining custom resource types and controllers for specialized use cases.
