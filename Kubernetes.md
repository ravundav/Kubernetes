# What Is Kubernetes?

Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications"

We can think of Kubernetes as the pilot on a ship of containers.

Kubernetes is also referred to as k8s (pronounced Kate's), as there are 8 characters between k and s. It is an open source project written in the Go language.

# KubernetesSeveral features/objects of Kubernetes 
  - API servers
  - Pods
  - IP-per-Pod
  - Services
  - Labels.

# Kubernetes Features

Kubernetes offers a very rich set of features for container orchestration. Some of its fully supported features are:
  - Automatic bin packing
    Kubernetes automatically schedules containers based on resource needs and constraints, to maximize utilization without sacrificing availability.

  - Designed for extensibility
    A Kubernetes cluster can be extended with new custom features without modifying the upstream source code.
    
  - Self-healing
    Kubernetes automatically replaces and reschedules containers from failed nodes. It terminates and then restarts containers that become unresponsive to health checks, based on existing rules/policy. It also prevents traffic from being routed to unresponsive containers.
  
  - Horizontal scaling
    Kubernetes scales applications manually or automatically based on CPU or custom metrics utilization.
    
  - Service discovery and load balancing
    Containers receive IP addresses from Kubernetes, while it assigns a single Domain Name System (DNS) name to a set of containers to aid in load-balancing requests across the containers of the set.

Additional fully supported Kubernetes features are:

  - Automated rollouts and rollbacks
    Kubernetes seamlessly rolls out and rolls back application updates and configuration changes, constantly monitoring the application's health to prevent any downtime.

  - Secret and configuration management
    Kubernetes manages sensitive data and configuration details for an application separately from the container image, in order to avoid a rebuild of the respective image. Secrets consist of sensitive/confidential information passed to the application without revealing the sensitive content to the stack configuration, like on GitHub.
  
  - Storage orchestration
    Kubernetes automatically mounts software-defined storage (SDS) solutions to containers from local storage, external cloud providers, distributed storage, or network storage systems.
  
  - Batch execution
    Kubernetes supports batch execution, long-running jobs, and replaces failed containers.
  
  - IPv4/IPv6 dual-stack
    Kubernetes supports both IPv4 and IPv6 addresses.

Kubernetes supports common Platform as a Service specific features such as application deployment, scaling, and load balancing, but allows users to integrate their desired monitoring, logging and alerting solutions through optional plugins.

There are many additional features currently in alpha or beta phase. They will add great value to any Kubernetes deployment once they become stable features. For example, support for role-based access control (RBAC) is stable only as of the Kubernetes 1.8 release, while cronjob support is stable only as of release 1.21.
