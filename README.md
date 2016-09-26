Docker
======

Install and configure docker

Role Variables
--------------

```
# Docker install configuration
docker_apt_key_server: hkp://p80.pool.sks-keyservers.net:80
docker_apt_key_id: 58118E89F3A912897C070ADBF76221572C52609D
docker_apt_repo: deb https://apt.dockerproject.org/repo debian-jessie main
docker_dep_packages:
  - apt-transport-https
  - ca-certificates
docker_packages:
  - docker-engine
```

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - { role: jebovic.docker }
```

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic