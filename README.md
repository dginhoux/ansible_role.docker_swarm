Ansible Role : dginhoux.docker_swarm
=========

This ansible role init, configure and remove a swarm cluster.
Nodes have to be fitted in two groups in ansible inventory.



Requirements
------------

This role is built to only run on platforms defined in `meta/main.yml`.
Docker engine need to be installed and running before.
Every nodes used (manager and worker) must be online.


Role Variables
--------------

Necessary variables are defined on `defaults/main.yml`

```yaml
docker_swarm_inventory_manager_group_name: group_srv_swarm_manager
docker_swarm_inventory_worker_group_name: group_srv_swarm_worker

##### [group_vars] optionnals settings
# docker_swarm_heartbeat_tick: 5
# docker_swarm_dispatcher_heartbeat_period: 10
# docker_swarm_task_history_retention_limit: 5
# docker_swarm_snapshot_interval: 10000
# docker_swarm_keep_old_snapshots: 0
docker_swarm_subnet_size: 24
docker_swarm_default_addr_pool: 10.0.0.0/8

##### [host_vars] or [group_vars] settings
docker_swarm_node_docker_host: unix://var/run/docker.sock
docker_swarm_node_labels: []
# docker_swarm_node_labels:
#   pxe: "oui"
#   label1: "456"
#   val: "5"

##### [host_vars] optionnals settings
# docker_swarm_node_advertise_addr: 0.0.0.0:2377
# docker_swarm_node_listen_addr: 0.0.0.0:2377
# docker_swarm_node_availability: active OR pause OR drain
# docker_swarm_node_role: manager OR worker
```


Dependencies
------------

none


Example Playbook
----------------



License
-------

BSD


Author Information
------------------

https://github.com/dginhoux/
