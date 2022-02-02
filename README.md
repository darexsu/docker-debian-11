# Doсkerfile: Debian-11 for Molecule CI 

[![Build](https://github.com/darexsu/docker-debian-11/actions/workflows/build.yml/badge.svg)](https://github.com/darexsu/docker-debian-11/actions/workflows/build.yml)
[![Docker pulls](https://img.shields.io/docker/pulls/darexsu/molecule-debian-11.svg?maxAge=2592000)](https://hub.docker.com/r/darexsu/molecule-debian-11/)

Debian-11 for Ansible Playbooks testing

### Example molecule.yml
```yaml
---
dependency:
  name: galaxy
driver:
  name: docker
platforms:
  - name: instance
    image: "darexsu/molecule-debian-11:latest"
    command: ${MOLECULE_DOCKER_COMMAND:-""}
    volumes:
      - /sys/fs/cgroup:/sys/fs/cgroup:ro
    privileged: true    
provisioner:
  name: ansible
  playbooks:
    converge: converge.yml
```
