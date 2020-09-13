# Ansible Collection - ronmallory.win_docker

## Import Collection
```yaml
ansible-galaxy collection install ronmallory.win_docker
```

## Description

This role installs docker on windows server 2019.

[https://galaxy.ansible.com/ronmallory/win_docker](https://galaxy.ansible.com/ronmallory/win_docker)

## Use with vagrant

* Install virtualbox
* Install Vagrant
  * [https://www.vagrantup.com/docs/installation](https://www.vagrantup.com/docs/installation)
  * vagrant box from: [StefanScherer/windows_2019](https://app.vagrantup.com/StefanScherer/boxes/windows_2019_docker)

```yaml
# init vagrant box
vagrant init StefanScherer/windows_2019
vagrant up

# run test playbook
ansible-playbook ronmallory/win_docker/rolestests/vagrant_test.yml
```
