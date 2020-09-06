win_docker
=========

A role to install docker on windows server 2019.

Requirements
------------

Internet Access

Role Variables
--------------
|Var Name|Requirement|Value|Description|
|---|---|---|---|
|feat_name|Mandatory|Containers|Name of windows feature to install|
|feat_local_src|Optional|file path to local source|Local source location|
|feat_mgmt_tool|Optional| yes or no| install optional features|
|feat_sub_feat|Optional|yes or no| install sub featuers|
|feat_state|Mandatory|present|state of the feature|
|win_svc_name|Mandatory|docker|Name of docker service|
|win_svc_state|Mandatory|started|state of the service|
|win_svc_user|Optional||username for user to run the docker service|
|win_svc_pass|Optional||Password for username to run docker service do not store in clear text|
|win_svc_path|Optional|Path for the service exe|
|win_svc_start_mode|Optional|auto, delayed, disabled, manual|Service mode of running|


Dependencies
------------

This role depends on access to the internet

Example Playbook
----------------

The below example will install this role on a vagrant box.  Source of Vagrant box used in development:

[StefanScherer_windows_2019](https://app.vagrantup.com/StefanScherer/boxes/windows_2019)

```yaml
---
- hosts: 127.0.0.1
  gather_facts: no
  vars:
    ansible_user: vagrant
    ansible_password: vagrant
    ansible_connection: winrm
    ansible_winrm_transport: basic
    ansible_port: 55985
    ansible_winrm_server_cert_validation: ignore
    ansible_winrm_scheme: http

  tasks:

    # import role
    - name: import role
      import_role:
        name: win_docker
      vars:
        win_svc_name: 'docker'
        win_svc_state: 'started'

```

License
-------

GPL3.0

Author Information
------------------

Name: Ron Mallory
Email: ronnymallory@gmail.com

