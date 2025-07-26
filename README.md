# 🚀 Docker Ansible Playbook – DEPI Assignment

This repository contains an Ansible playbook that automates the installation of Docker, runs an Nginx container, and displays the output of the `docker ps` command on a target RHEL-based system.

---

## 📋 Playbook Overview

**Filename:** `playbook.yaml`  
**Target Group:** `web` (defined in inventory.ini)  
**Privilege Escalation:** `become: yes`  

---

## 🔧 What This Playbook Does

1. Installs required DNF plugin tools (`dnf-plugins-core`)
2. Adds the official Docker CE repository
3. Installs Docker and related packages:
   - `docker-ce`
   - `docker-ce-cli`
   - `containerd.io`
   - `docker-buildx-plugin`
   - `docker-compose-plugin`
4. Starts and enables the Docker service
5. Runs an Nginx container named `nginx-from-ansible`
6. Executes `docker ps` to verify container status
7. Prints the output of `docker ps` to the terminal

---

## 📦 Prerequisites

- A reachable RHEL-based host group named `web` in your inventory
- Ansible installed on the control node
- The [`community.docker`](https://galaxy.ansible.com/community/docker) collection installed:

```bash
ansible-galaxy collection install community.docker
