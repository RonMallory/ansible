# A collection of Ansible Roles

This repo is a collection of roles that can be used to automate various tasks.

## Getting Started

Set up development workstation

Install required Software
* ansible
* vagrant
* virtual box
* commit-lint

## Vagrant

variables used to run ansible commands on vagrant box.

```yaml
vars:
  ansible_user: vagrant
  ansible_password: vagrant
  ansible_connection: winrm
  ansible_winrm_transport: basic
  ansible_port: 55985
  ansible_winrm_server_cert_validation: ignore
  ansible_winrm_scheme: http
```

### start vagrant box

```bash
vagrant up
```

### run playbook from local machine to vagrant box

```bash
ansbile-playbook win_docker.yml
```

