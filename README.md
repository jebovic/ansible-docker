Docker
======

[![Build Status](https://travis-ci.org/jebovic/ansible-docker.svg?branch=master)](https://travis-ci.org/jebovic/ansible-docker) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.docker-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/docker)

Install and configure docker

This role is a part of my [OPS project](https://github.com/jebovic/ops), follow this link to see it in action. OPS provides a lot of stuff, like a vagrant file for development VMs, playbooks for roles orchestration, inventory files, examples for roles configuration, ansible configuration file, and many more.

Compatibility
-------------

Tested and approved on :

* Debian jessie (8+)
* Ubuntu Trusty (14.04 LTS)
* Ubuntu Xenial (16.04 LTS)

Role Variables
--------------

```yaml
# Docker install configuration
docker_apt_key_server: hkp://p80.pool.sks-keyservers.net:80
docker_apt_key_id: 58118E89F3A912897C070ADBF76221572C52609D
docker_apt_repo: deb https://apt.dockerproject.org/repo debian-jessie main
docker_dep_packages:
  - apt-transport-https
  - ca-certificates
docker_packages:
  - docker-engine

# Docker extras installations
docker_compose_enabled: yes
docker_compose_url: "https://github.com/docker/compose/releases/download/1.8.1/docker-compose-Linux-x86_64"
docker_compose_install_path: /usr/local/bin/docker-compose
docker_newrelic_support_enabled: yes
docker_test_mode: no
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: jebovic.docker }
```

Example : config
----------------

```yaml
# Install docker only, without newrelic support and docker-compose
docker_compose_enabled: no
docker_newrelic_support_enabled: no
```

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
