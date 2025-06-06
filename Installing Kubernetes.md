# Kubernetes Configuration
Kubernetes can be installed using different cluster configurations. The major installation types are described below:

### All-in-One Single-Node Installation

In this setup, all the control plane and worker components are installed and running on a single-node. While it is useful for learning, development, and testing, it is not recommended for production purposes.

### Single-Control Plane and Multi-Worker Installation

In this setup, we have a single-control plane node running a stacked etcd instance. Multiple worker nodes can be managed by the control plane node.

### Single-Control Plane with Single-Node etcd, and Multi-Worker Installation

In this setup, we have a single-control plane node with an external etcd instance. Multiple worker nodes can be managed by the control plane node.

### Multi-Control Plane and Multi-Worker Installation

In this setup, we have multiple control plane nodes configured for High-Availability (HA), with each control plane node running a stacked etcd instance. The etcd instances are also configured in an HA etcd cluster and multiple worker nodes can be managed by the HA control plane.

### Multi-Control Plane with Multi-Node etcd, and Multi-Worker Installation

In this setup, we have multiple control plane nodes configured in HA mode, with each control plane node paired with an external etcd instance. The external etcd instances are also configured in an HA etcd cluster, and multiple worker nodes can be managed by the HA control plane. This is the most advanced cluster configuration recommended for production environments.

As the Kubernetes cluster's complexity grows, so does its hardware and resources requirements. While we can deploy Kubernetes on a single host for learning, development, and possibly testing purposes, the community recommends multi-host environments that support High-Availability control plane setups and multiple worker nodes for client workload for production purposes.

# Infrastructure for Kubernetes Installation

Once we decide on the installation type, we need to decide on the infrastructure. Infrastructure related decisions are typically guided by the desired environment type, either learning or production environment. For infrastructure, we need to decide on the following:

    - Should we set up Kubernetes on bare metal, public cloud, private, or hybrid cloud?
    - Which underlying OS should we use? Should we choose a Linux distribution - Red Hat-based or Debian-based, or Windows?
    - Which networking solution (CNI) should we use?

# Installing Local Learning Clusters

Installing Local Learning Clusters
There are a variety of installation tools allowing us to deploy single- or multi-node Kubernetes clusters on our workstations, for learning and development purposes. While not an exhaustive list, below we enumerate a few popular ones:

[Minikube](https://minikube.sigs.k8s.io/docs/)
Single- and multi-node local Kubernetes cluster, recommended for a learning environment deployed on a single host.

[Kind](https://kind.sigs.k8s.io/)
Multi-node Kubernetes cluster deployed in Docker containers acting as Kubernetes nodes, recommended for a learning environment.

[Docker Desktop](https://www.docker.com/products/docker-desktop/)
Including a local Kubernetes cluster for Docker users.

[Podman Desktop](https://podman-desktop.io/)
Including Kubernetes integration for Podman users.

[MicroK8s](https://microk8s.io/)
Local and cloud Kubernetes cluster for developers and production, from Canonical.

[K3S](https://k3s.io/)
Lightweight Kubernetes cluster for local, cloud, edge, IoT deployments, originally from Rancher, currently a CNCF project.

Minikube is an easy and flexible method to create a local Kubernetes setup. We will be using it extensively in this course to manage certain aspects of a Kubernetes cluster, while taking advantage of several automated features designed to simplify the user interaction with the Kubernetes environment and the containerized applications deployed to the cluster.

# Installing Production Clusters with Deployment Tools

When it comes to production ready solutions, there are several recommended tools for Kubernetes cluster bootstrapping and a few that are also capable of provisioning the necessary hosts on the underlying infrastructure.

### kubeadm

kubeadm is a first-class citizen of the Kubernetes ecosystem. It is a secure and recommended method to bootstrap a multi-node production ready Highly Available Kubernetes cluster, on-premises or in the cloud. kubeadm can also bootstrap a single-node cluster for learning. It has a set of building blocks to set up the cluster, but it is easily extendable to add more features. Please note that kubeadm does not support the provisioning of hosts - they should be provisioned separately with a tool of our choice.

### kubespray

kubespray (formerly known as kargo) allows us to install Highly Available production ready Kubernetes clusters on AWS, GCP, Azure, OpenStack, vSphere, or bare metal. kubespray is based on Ansible, and is available on most Linux distributions. Explore the kubespray project for more details.

### kops

kops enables us to create, upgrade, and maintain production-grade, Highly Available Kubernetes clusters from the command line. It can provision the required infrastructure as well. Currently, AWS and GCE are officially supported. Support for DigitalOcean and OpenStack is in beta, while Azure is in alpha support, and other platforms are planned for the future. Explore the kops project for more details.

# Production Clusters from Certified Solutions Providers

The growing popularity of Kubernetes accelerated its adoption by many cloud services providers together with hosted platforms of certified Kubernetes distributions. There are well over 200 managed certified Kubernetes services providers today, as many more organizations became Kubernetes partners, joining the list of initial providers of hosted Kubernetes solutions:

### Hosted Solutions

Hosted Solutions providers fully manage the provided software stack, while the user pays hosting and management charges. Popular vendors providing hosted solutions for Kubernetes are (listed in alphabetical order):

    - Alibaba Cloud Container Service for Kubernetes (ACK)
    - Amazon Elastic Kubernetes Service (EKS)
    - Azure Kubernetes Service (AKS)
    - DigitalOcean Kubernetes (DOKS)
    - Google Kubernetes Engine (GKE)
    - IBM Cloud Kubernetes Service
    - Oracle Container Engine for Kubernetes (OKE)
    - Red Hat OpenShift
    - VMware Tanzu Kubernetes Grid

### Partners

Additional Partners providing managed Kubernetes services and platforms (listed in alphabetical order):

    - Aqua Security
    - Canonical
    - D2IQ
    - Dell Technologies Consulting
    - Deloitte
    - Fujitsu
    - GitLab
    - HPE
    - Kubermatic
    - Kublr
    - Mirantis
    - Platform9
    - SAP
    - SUSE
    - Sysdig
    - Weaveworks

### Turnkey Cloud Solutions

Turnkey Cloud Solutions install production ready Kubernetes clusters on cloud infrastructure:

    - Linode Kubernetes Engine
    - Nirmata Managed Kubernetes
    - Nutanix Karbon
    - Vultr Kubernetes Engine

### Kubernetes on Windows

The Windows operating system plays a key role in running and managing enterprise applications and services. With that in mind, the Kubernetes community worked very hard to bring Windows support to Kubernetes.

With the release of Kubernetes v1.14, Windows was successfully introduced as a supported production ready operating system only for worker nodes of a Kubernetes cluster. This enabled Kubernetes to support the deployment of Windows containers in the cluster, either as a dedicated Windows cluster, or a hybrid cluster with Windows nodes running alongside Linux nodes. Keep in mind, however, that the control plane nodes are limited to running on Linux only, with no plans to extend the support to Windows control plane nodes.

With Windows Server 2019 and Windows Server 2022 being the only Windows OS supported by Kubernetes, the same container workload orchestration tool can schedule and deploy both Linux and Windows containers in the same cluster. The user is responsible to configure the workload scheduling according to the expected OS, that is to schedule Linux and Windows containers on nodes with their respective operating systems when nodes of each OS coexist in the same Kubernetes cluster.
