# docker-swarm-traefik

This is a zero downtime deployment example with Docker swarm and Traefik. 

Traefik is the load balancer solution for the Docker containers running our application services. Docker swarm is in use to manage multiple application containers.


<img src="https://i.postimg.cc/Tw94GvxP/traefik.jpg">
--

# Requirements

You must have these applications installed on your system.

- Docker
- Ansible

```
$ docker --version
Docker version 18.06.3-ce, build d7080c1

$ ansible --version
ansible 2.7.8
```

- docker-py

```
$ (sudo) pip install docker-py
```


# Instructions

Initial deployment:

```
$ ansible-playbook provision.yml
```

Upgrading and Deploying airport service:

```
$ ansible-playbook deployment.yml --extra-vars "version=1.1.0"
```

# Notes

In order to test the v1.0.1, v1.1.0 (airport service) deployments, you can these commands:


| Version   | Command                                                                  |
|-----------|--------------------------------------------------------------------------|
| **1.0.1** | `curl -H Host:airports.lunatech.com http://127.0.0.1:8000/airports/NL`   |
| **1.1.0** | `curl -H Host:airports.lunatech.com http://127.0.0.1:8000/airports/EHAM` |
