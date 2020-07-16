<p align="center" style="background-color:#23327c">
  <img src="https://biqmind.com/wp-content/uploads/2020/07/CAPE-4CLogo-Hor.png"/>
</p>
<p align="center">
  <a href="#features">Features</a> •
  <a href="#install">Install</a> •
  <a href="#Learn">Learn</a> •
  <a href="#license">License</a> •
  <a href="#support">Support</a> 

</p>

# Advanced Kubernetes Multi-cluster Application & Data Management

CAPE provides advanced Kubernetes features for Disaster Recovery, Data Migration & Mobility, Multi-cluster Application Deployment and CI/CD within a single, intuitive interface.

Deploy advanced K8s functionalities without the learning curve. This repo is for tracking community issues and feedback. Try CAPE today and let us know what you think!

<hr/>

<p align="center" style="background-color:#23327c">
  <img src="https://biqmind.com/wp-content/uploads/2020/07/CAPEReadmeDashboard.png" />
</p>

[![CAPE](https://github.com/cape-sh/cape/blob/master/assets/youtube-cape.png)](https://youtu.be/4KJt8NXTO8E "CAPE INTRO")


## Features

1. <b>Disaster Recovery</b>
- Single & scheduled backup & restore 
- Multi-cluster & multi-cloud backup & restore 
 
2. <b>Data Migration & Mobility</b>
- Secure, encrypted application & data at rest and in transit
- Support for on-prem, private cloud, major public clouds and edge

3. <b>Multi-cluster Application Deployment</b>
- End-to-end deployment, from application definition to application release
- Support for multiple types of application environments

4. <b>Drag & Drop CI/CD Workflow Manager (In development)</b>
- Build, Test & Deploy across multiple cloud providers or on-premises systems
- Standardize CI/CD tooling & processes across vendors & deployment environments

<hr /> 

### Install

> There are 2 options for accessing CAPE. Follow one of the options below as "root" user on the machine that you want to deploy to.

Option 1: 

Access CAPE UI with a local private IP env.

>   Eg: You and your VM are at home and you want to access using a private IP e.g., 192.168.1.7
 
```bash
curl https://raw.githubusercontent.com/cape-sh/cape-ansible/master/script/capesaaPvtIP.sh > capesaaPvtIP.sh
sh capesaaPvtIP.sh
```

Option 2:

Access CAPE UI with a public IP env.

>   Eg: Your VM is in the cloud and has a public IP e.g., 13.103.25.99

```bash
curl  https://raw.githubusercontent.com/cape-sh/cape-ansible/master/script/capesaasPubIP.sh > capesaasPubIP.sh
sh capesaasPubIP.sh
```
---

### Access CAPE UI 

The service may take 1-5 mins to come up based on the server config and the internet bandwidth.

> URL

```
http://<Your_server_ip>.nip.io/
```
** All CAPE documentation is available [here](https://docs.cape.sh/docs/) **

---

### What do the different Ansible roles do?

```
 1. Prereq: Prerequisite config at the os layer e.g., autoconfigure all repositories , SELinux , disable firewall etc.
 2. Download: Downloads all the relevant packages and scripts
 3. K3S: Installs k3s, crictl master on centos7/RHEL7 
 4. Cape: Installs the CAPE SAAS application & enables access to CAPE GUI via URL
 5. Reset: Uninstalls the Kubernetes packages from your machine 
``` 
---

### Troubleshooting 

Login as root to your machine

```bash
kubectl get pods -n cape
```
Make sure all pods are in a healthy state else kill any unhealthy pods and they will restart within a few seconds

---

### RESET everything using playbook

Login as root to your machine

> Run this playbook to uninstall Kubernetes and crictl

```bash
cd cape-ansible
ansible-playbook reset.yml
```
> "cape-ansible" directory is located where the capesaasPubIP.sh or capesaasPvtIP.sh script was downloaded earlier.

---

### Recommended System requirements

```
OS: Centos 7.3/7.4/7.5  
CPU: 2 core
RAM: 4GB RAM
Disk Space: 10 GB free 
Server Internet access: Yes
```

---

After accessing the CAPE UI, we recommend you to go through our videos for a walkthrough of the various use cases. 

## Learn

- [Recent Webinar](https://www.youtube.com/watch?v=JHP9zgv75ls)
- [CAPE Tutorials](https://www.youtube.com/watch?v=S551qxe9vCg&list=PLByzHLEsOQEB01EIybmgfcrBMO6WNFYZL)
- [Katacoda](https://katacoda.com/cape/courses/trycape/) 

## Use CAPE on Your Favorite Platforms
CAPE is also avaliable for the following deployment platforms:
- [Ansible](https://galaxy.ansible.com/biqmind_cloudnative/cape_ansible)
- [Docker Hub](https://hub.docker.com/u/capesh)
- [Github](https://github.com/cape-sh/cape-docker)
- [Helm Charts](https://github.com/biqmind/cape-saas-operator/tree/master/helm/cape)
- [OperaterHub]-> Coming soon

## Environments Supported

For CAPE Version V1.0.0
- AWS
- DigitalOcean
- GCE
- Azure
- Alibaba Cloud
- Huawei Cloud
- Tencent Cloud

## License
CAPE Community Edition will always be FREE for to 10 nodes. Get in touch with us at connect@biqmind.com if you are looking for a paid subscription. 


## Support

### Videos

#### CAPE UI Features Walkthrough
- [Key Menus](https://www.youtube.com/watch?v=S551qxe9vCg)

#### Clusters Walkthrough
- [Create Organization](https://www.youtube.com/watch?v=rjfZ_Av-Mxg)
- [Connect Biqmind CAPE to a K8s cluster using Kubectl](https://www.youtube.com/watch?v=CSW4IrjyGro)
- [Connect Biqmind CAPE to a K8s cluster using Kubeconfig](https://www.youtube.com/watch?v=pvfDTnu-HLI)
- [Install a disaster recovery component](https://www.youtube.com/watch?v=74t6jKB9G3E)

#### Backups Walkthrough
- [Backup K8s on-demand](https://www.youtube.com/watch?v=MOPtRTeG8sw)
- [Schedule a K8s Backup](https://www.youtube.com/watch?v=CkIVZdmWXiQ)
- [Share backup with other clusters](https://www.youtube.com/watch?v=tnyNPynPLJI)

#### Restores Walkthrough
- [Restoring a Kubernetes cluster](https://www.youtube.com/watch?v=Xf0TkzudUF0)
- [Restoring a Kubernetes cluster to another cluster](https://www.youtube.com/watch?v=dhBnUgfTsh4)

### Documentation
- Get started with CAPE [Docs](https://docs.cape.sh/docs/).

### Contribute
We welcome contributions from the community:
- Bug reports and feature requests through [Github issues](https://github.com/cape-sh/cape/issues/new)

### Contact
Connect with us over on our mailing list or Slack:
- [<img src="https://img.shields.io/badge/Slack-CAPE-brightgreen">](https://capesh.slack.com)

Our Youtube channel:
- [<img src="https://img.shields.io/badge/Youtube-Biqmind-blue">](https://www.youtube.com/channel/UCSXtrXokSgbZuSz7qgu3VHw)

If you like our project,
![Twitter Follow](https://img.shields.io/twitter/follow/CapeSuperhero?style=social) and 
![GitHub stars](https://img.shields.io/github/stars/cape-sh/cape?style=social)  





