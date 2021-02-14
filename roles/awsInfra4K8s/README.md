AWSInfra4K8s
============

Ansible Role to create a AWS Infrastructure for Kubernetes MultiNode Cluster

Requirements
------------

AWSCLIv2 should be installed and configured  
  
Required Python Packages -  
- boto  
- boto3  
- botocore  
- python >= 2.6  

Role Variables
--------------

Variables which should be included in additional variable files -  

    # Specify AWS CLI Profile to be Used
    aws_profile: default


    #### Ansible Paths ####
    # Path to ansible config directory
    ans_conf_dir: /etc/ansible/
    # Path to ansible inventory file
    ansible_inv_path: /etc/ansible/hosts/hosts.txt


    #### AWS Subnets ####
    ## These two subnets should have connectivity between then
    # For Master Node
    master_subnet_id: "subnet-id"
    # For Worker Nodes
    worker_subnet_id: "subnet-id"


    #### AMI IDs ####
    ## Recommended To use RedHat Linux
    # For Master Node
    master_ami_id: "ami-awsamiidhere"
    # For Worker Nodes
    worker_ami_id: "ami-awsamiidhere"


    #### Specify Instance Types ####
    ## Recommended to have more then 1 CPUs for K8s
    # For Master Node
    master_inst_type: "t2.medium"
    # For Worker Nodes
    worker_inst_type: "t2.medium"


    #### Your Public CIDR ####
    # This Public CIDR/IP is allowed through Security Group of Master Node
    # So that Master Node can be accessible
    #
    # If not specified, then by default 0.0.0.0/0 will be allowed
    # That is Master Node is vulnerable as it is publically open
    pub_cidr: "0.0.0.0/0"


    # Port Number for kubernetes KubeAPI Server
    kubeapi_port: 6443

    # Number of Worker Nodes for k8s cluster
    no_of_workers: 3

Variables in defaults/main.yml -  

    # Kubernetes Nodeport Service Port Range
    nodeport_svc_range_start: 30000
    nodeport_svc_range_end: 32767

Variables in vars/main.yml -  

    # Key-pair name for Kubernetes Nodes
    k8s_key_name: k8skey

    #### Security Groups Name ####
    # For Master Node
    master_sg_name: mastsg
    # For Worker Nodes
    worker_sg_name: worksg

Dependencies
------------

No Dependencies on other roles or collections

Example Playbook
----------------

aws_k8s_infra.yml is a additional variable file that contains required variables -

    - hosts: servers
      vars_files:
         - aws_k8s_infra.yml
      roles:
         - jhagdu.awsInfra4K8s

License
-------

BSD

Author Information
------------------

Author Name: Aman Jhagrolia  
Contact: https://www.linkedin.com/in/amanjhagrolia143  
