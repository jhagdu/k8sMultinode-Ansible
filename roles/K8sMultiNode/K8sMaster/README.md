K8sMaster
=========

Ansible Role to configure Kubernetes Master Node using Kubeadm

Requirements
------------

Recommended target systems are RHEL or Centos

Role Variables
--------------

Variables which should be included in additional variable files -  

    # Kubernetes Version
    k8s_version: stable-1


    #### CIDRs ####
    ## Service CIDR
    # It is for kubeadm init option --service-cidr
    service_cidr: "10.96.0.0/12"
    #
    ## POD Network CIDR 
    # Specify range of IP addresses for the pod network
    # It is for kubeadm init option --pod-network-cidr
    pod_network_cidr: "10.240.0.0/16"


    #### KubeAPI Port ####
    # Port Number for kubernetes KubeAPI Server
    kubeapi_port: 6443


    #### Other Init Options ####
    # Any other additional options to add in init subcommand of kubeadm
    # See all Init options here - https://kubernetes.io/docs/reference/setup-tools/kubeadm/kubeadm-init/
    #
    # If your system/instance have <2 CPU and <1700MB RAM then pass --ignore-preflight-errors="NumCPU,Mem" to init_opts
    #
    ## Note - Don't pass options --kubernetes-version, --apiserver-bind-port, --service-cidr and --pod-network-cidr here 
    ## as they are already passed using above variables
    #
    ## For example :-
    #  kubeadm_opts: '--token ab34ef.0123456789abcdef --skip-token-print --ignore-preflight-errors="NumCPU,Mem"'
    init_opts: ''


    #### Other Kubeadm Options ####
    # Any other additional options to add in kubeadm command
    #
    ## For example :-
    #  kubeadm_opts: '--add-dir-header --log-file /file/path'
    kubeadm_opts: ''

Dependencies
------------

Recommended to use with jhagdu.K8sWorker Role which configure K8s Worker Node

Example Playbook
----------------

k8s_multinode.yml is a additional variable file that contains required variables -

    - hosts: servers
      vars_files:
         - k8s_multinode.yml
      roles:
         - jhagdu.k8smaster

License
-------

BSD

Author Information
------------------

Author Name: Aman Jhagrolia  
Contact: https://www.linkedin.com/in/amanjhagrolia143  
