DeploySiteOnK8s
===============

Ansible Role to deploy a containerized app over a kubernetes cluster

Requirements
------------

Kubectl should be installed and configured

Required Python Packages -  
- PyYAML >= 3.11
- openshift >= 0.6
- python >= 2.7

Role Variables
--------------

Variables which should be included in additional variable files -  

    # Name of K8s Namespace to be created
    namespace: webspace

    # Specify Docker Image to deploy on K8s cluster
    image_to_deploy: "image_name_to_deploy:version"

    # Number of replicas to create
    pod_replicas: 3

    # Exposed Container Port
    exposed_container_port: 80

    # Service Type
    svc_type: NodePort

Dependencies
------------

Depends on Ansible Collections -
- community.kubernetes (To install it use 'ansible-galaxy collection install community.kubernetes')

Example Playbook
----------------

site_deploy.yml is a additional variable file that contains required variables -

    - hosts: servers
      vars_files:
         - site_deploy.yml
      roles:
         - jhagdu.deploysiteonk8s

License
-------

BSD

Author Information
------------------

Author Name: Aman Jhagrolia  
Contact: https://www.linkedin.com/in/amanjhagrolia143  
