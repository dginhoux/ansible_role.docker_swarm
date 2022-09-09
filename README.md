ginhouxnet.docker_swarm
=========

This ansible role create a swarm cluster from docker node specified in two group in ansible inventory.
Docker need to be installed on the node where this roles is running.
Every nodes specified in both inventory groups (manager and worker) must be online, above the first declared manager.



Requirements
------------

This role is built to only run on platforms defined in `meta/main.yml`


Role Variables
--------------

Necessary variables are defined on `defaults/main.yml`
```
docker_swarm_inventory_manager_group_name: group_srv_swarm_manager
docker_swarm_inventory_worker_group_name: group_srv_swarm_worker


# You can set any interface, that is listened by docker engine.
# e.g. docker_swarm_interface: "eth1"
docker_swarm_interface: "{{ ansible_default_ipv4['interface'] }}"
docker_swarm_addr: "{{ hostvars[inventory_hostname]['ansible_' + docker_swarm_interface]['ipv4']['address'] }}"

docker_swarm_port: 2377

docker_swarm_labels: []
```


Dependencies
------------

Docker engine need to be installed before.


Example Playbook
----------------



License
-------

BSD


Author Information
------------------

https://github.com/dginhoux/
