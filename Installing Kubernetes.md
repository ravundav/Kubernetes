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


