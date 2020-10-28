Role Name
=========

An Ansible role that installs Docker on Linux.

Requirements
------------

None.

Role Variables
--------------
Available variables are listed below along with their default values. (see [defaults/main.yml](defaults/main.yml))
```
---
docker_apt_gpg_key: https://download.docker.com/linux/{{ ansible_distribution | lower }}/gpg
docker_apt_repository: "deb [arch=amd64] https://download.docker.com/linux/{{ ansible_distribution | lower }} {{ ansible_distribution_release }} stable"
docker_yum_repo_url: https://download.docker.com/linux/{{ (ansible_distribution == "Fedora") | ternary("fedora","centos") }}/docker-ce.repo
docker_yum_gpg_key: https://download.docker.com/linux/centos/gpg


docker_compose_version: "1.26.0"
docker_compose_url: https://github.com/docker/compose/releases/download/{{ docker_compose_version }}/docker-compose-Linux-x86_64
docker_compose_path: /usr/local/bin/docker-compose
```

Dependencies
------------

None.

Example Playbook
----------------

How to use the role:

    - hosts: all
      roles:
         - docker

License
-------

MIT

Author Information
------------------

This role was created in 2020 by Andrew Gonzalez.
