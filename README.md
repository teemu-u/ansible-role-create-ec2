Role Name
=========

This role is to create a new EC2 Instance. 

Requirements
------------
 * Python
 * Boto must be installed on the node where the role will be invoked. 
 * The node where the role will be invoked should be an EC2 Instance which has a role assigned with enough previleges to create another EC2 Instance

Role Variables
--------------
Below is a list of mandatory variables-
 * ami: Defines the AMI which has to be used for creating the instance
 * sec_group: Defines the security group to be used for new instance
 * region: Region in which the new instance will be created
 * subnet: Subnet in which the new instance will be created
 * server: Server name. An entry of this name will be added to host_vars and /etc/ansible/hosts

Dependencies
------------
None

Example Playbook
----------------
- name: Create a server using EC2 module
  hosts: localhost
  connection: local
  vars:
    ami: ami-1fbad07d
    sec_group: sg-77602f11
    region: ap-southeast-1
    subnet: subnet-9d05befe
    server: my_server
  roles:
    - create-ec2



License
-------

GNU

Author Information
------------------

