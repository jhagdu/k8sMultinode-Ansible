K8sWorker
=========

Ansible Role to configure Kubernetes Worker Node using Kubeadm

Requirements
------------

Recommended target systems are RHEL or Centos

Role Variables
--------------

    # Pass IP of Kubernetes Master Node here
    # Worker node will be joined with this master
    # Examples :- 
    #     k8s_master_ip: localhost
    #     k8s_master_ip: 192.143.66.7
    #     k8s_master_ip: "{{ groups.K8sMaster }}"
    k8s_master_ip: 127.0.0.1

Dependencies
------------

Recommended to use with jhagdu.K8sMaster Role which configure K8s Master Node

Example Playbook
----------------

    - hosts: servers
      vars:
        - k8s_master_ip: 127.0.0.1
      roles:
         - jhagdu.K8sWorker

License
-------

BSD

Author Information
------------------

Author Name: Aman Jhagrolia  
Contact: https://www.linkedin.com/in/amanjhagrolia143  
