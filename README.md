# Docker role

## Features

Install docker-engine from official Docker Inc's repository

## Source

Based on [Krast76's role](https://github.com/Krast76/ansible-docker)

## Variables

Available variables are listed below, along with default values (see defaults/main.yml)

* Package type (Community or Enterprise)

    docker_package_type: docker-ce

* Repository's GPG signature key (required for installation on Debian)

    docker_gpg_url: "https://download.docker.com/linux/debian/gpg"

* Docker Machine related variables :

    docker_machine: False
    docker_machine_version: 0.10.0

* Docker Compose related variables :

    docker_compose: False
    docker_compose_version: 1.12.0

* Docker unsecure registry (only for registry without TLS/SSL) :

    docker_insecure_registry:
      - myregistry:5000
      - mybetterregistry:4000

## Example playbook

```
---
- hosts: localhost
  vars:
    - docker_package_type: docker-ce
    - docker_compose: True
  roles:
    - docker
```
