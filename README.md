Role Name
=========

This role is to create a new EC2 Instance and add to the inventory.


Requirements
------------
 * Python
 * Boto must be installed on the node where the role will be invoked. 
 * The node where the role will be invoked should be an EC2 Instance which has a role assigned with enough previleges to create another EC2 Instance. 
 * Currently it mandates you to pass ami, subnet, region and security group for creating the server. 

To do 
--------------

 * Going forward optional variables will be added to provide AWS Access Key and AWS Secret Key. This will allow this role to be invoked when invoking EC2 servers don't have appropriate role or when invoking server is not in EC2.
 * Going forward the variable will made optional and a subnet and security group will be created on the fly.
 * Provide a variable to control whether in the end Ansible inventory and host variables should be updated or not.

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
This role does not need any other role.

Example Playbook
----------------
    hosts: localhost
    connection: local
    vars:
      ami: ami-1fbad07c
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
sameer.kasi200x@gmail.com
sameer.kumar@ashnik.com

Twitter: @sameerkasi200x
