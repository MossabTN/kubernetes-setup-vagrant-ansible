# kubernetes-setup

## Requirements

- Ansible
- Vagrant
- Docker

## Setup environment
* To create kubernetes cluster
```bash
vagrant up
```

* To start a Haproxy you can use Docker and just run the following command:
```bash
docker-compose -f haproxy/docker-compose.yaml up -d
```
