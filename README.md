# K8s Multinode Cluster Using Ansible  

<img src="https://www.eweek.com/imagesvr_ez/b2bezp/2020/09/Kubernetes.logo.png?alias=social_image" height=100 width=170 alt="Kubernetes" /> <img src="https://gorillalogic.com/wp-content/uploads/2016/10/maxresdefault-1.jpg" height=100 width=170 alt="Ansible" /> <img src="https://www.metaltoad.com/sites/default/files/styles/large_personal_photo_870x500_/public/2020-05/aws-logo-blog-header.png?itok=t4o3meiH" height=100 width=170 alt="AWS" />

This repository contains the Ansible Playbook and Roles to deploy Kubernetes Multi-node cluster over AWS EC2 Instances. After successful deployment and configuration of K8s cluster a containerized webapp is deployed on that K8s Cluster.  
  
### Ansible Roles -   

**Role Name** | **Role Description**
------------- | --------------------
**awsInfra4K8s** | To create a AWS Infrastructure for Kubernetes MultiNode Cluster
**K8sMaster** | To configure Kubernetes Master Node using Kubeadm  
**K8sWorker** | To configure Kubernetes Worker Node using Kubeadm
**deploySiteOnK8s** | To deploy a containerized app over a kubernetes cluster

## Prerequisites   
- Ansible should be installed and Configured
- AWS CLI Should be Installed and Configured  
- Other requirements of Roles are included in Readme file of particular Role

## How to Start 
- Clone or Download the Repository  
- Change the value of variables according to requirement  
- Finally run setupK8sMultiNode.yml using 'ansible-playbook setupK8sMultiNode.yml' command  

## Note  
- Recommended to use RedHat AMI or OS for K8s Master and Workers  
- Ansible Config file should include previliage_escalation block to become root user in order to configure AWS Instances  

# Links

[Click here for Video and Post](https://www.linkedin.com/posts/amanjhagrolia143_rightmentor-righteducation-worldrecordholder-activity-6767009821616091138-ebAm)
  
***Feel free to Contact if any issue!!***

<a href="https://www.linkedin.com/in/amanjhagrolia143" target="_blank"> <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /> </a> 
<a href="https://galaxy.ansible.com/jhagdu" target="_blank"> <img src="https://galaxy.ansible.com/assets/galaxy-logo-02.svg" height=30 width=140 /> </a>