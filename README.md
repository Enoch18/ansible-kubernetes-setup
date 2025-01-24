# Kubernetes Cluster Setup with Ansible

This repository provides an automated setup for deploying a Kubernetes cluster using Ansible. The setup includes configuring master and worker nodes, setting up Flannel CNI for networking, and deploying Kubernetes components.

## Prerequisites

- **Ansible**: Version 2.18 or higher
- **SSH Access**: Passwordless SSH access between the control machine (where Ansible is run) and the target nodes (master and worker nodes).
- **Python**: Installed on all nodes (both master and worker nodes).
- **Kubernetes Version**: Ensure you're using a compatible version of Kubernetes (the latest stable version is recommended).

## File Structure

```plaintext
├── inventory.yml               # Inventory file with master and worker nodes
├── playbooks/
│   ├── step1_sysctl_config_and_swap_disable.yml  # Configure sysctl and disable swap
│   ├── step2_install_prerequisites.yml           # Install prerequisites (Docker, dependencies)
│   ├── step3_install_cgroup_driver.yml          # Install cgroup driver
│   ├── step4_install_kubernetes.yml             # Install Kubernetes components
│   ├── step5_initialize_master.yml              # Initialize the Kubernetes master node
│   ├── step6_join_workers.yml                  # Join worker nodes to the cluster
└── README.md                     # This file
