# ROLE dginhoux.docker_swarm



## DESCRIPTION

This ansible role init, configure and remove a swarm cluster.<br />


## REQUIREMENTS

Docker engine need to be installed and running before.<br />
Every nodes used (manager and worker) must be online.<br />
Nodes have to be fitted in two groups in ansible inventory.<br />


#### SUPPORTED PLATFORMS

| Platform | Versions |
|----------|----------|
| Debian | all |
| EL | all |
| Fedora | all |
| Ubuntu | all |

#### ANSIBLE VERSION

Ansible >= 2.13

#### DEPENDENCIES

None.



## INSTALLATION

#### ANSIBLE GALAXY

```shell
ansible-galaxy install dginhoux.docker_swarm
```
#### GIT

```shell
git clone https://github.com/dginhoux/ansible_role.docker_swarm dginhoux.docker_swarm
```


## USAGE

#### EXAMPLE PLAYBOOK

```yaml
- name: Playbook
  hosts: all
  tasks:
    - name: Start role dginhoux.docker_swarm
      ansible.builtin.include_role:
        name: dginhoux.docker_swarm
```


## VARIABLES

#### DEFAULT VARIABLES

Defaults variables defined in `defaults/main.yml`

#### EXAMPLES VARIABLES

```yaml
##
# Docker Swarm
##
# docker_swarm_inventory_manager_group_name: group_swarm_manager
# docker_swarm_inventory_worker_group_name: group_swarm_worker
docker_swarm_inventory_manager_group_name: group_pxe_manager
docker_swarm_inventory_worker_group_name: group_pxe_worker

##### GLOBAL optionnals settings
# docker_swarm_heartbeat_tick: 5
# docker_swarm_dispatcher_heartbeat_period: 10
# docker_swarm_task_history_retention_limit: 5
# docker_swarm_snapshot_interval: 10000
# docker_swarm_keep_old_snapshots: 0
docker_swarm_subnet_size: 24
docker_swarm_default_addr_pool: 10.0.0.0/8


##### PER NODES   or  GLOBAL settings
docker_swarm_node_docker_host: unix://var/run/docker.sock
docker_swarm_node_labels: []
# docker_swarm_node_labels:
#   pxe: "oui"
#   label1: "456"
#   val: "5"

##### PER NODES optionnals settings only
# docker_swarm_node_advertise_addr: 0.0.0.0:2377
# docker_swarm_node_listen_addr: 0.0.0.0:2377
# docker_swarm_node_availability: active OR pause OR drain
# docker_swarm_node_role: manager OR worker
```

#### DEFAULT OS SPECIFIC VARIABLES

Those variables files are located in `vars/*.yml` are used to handle OS differences.<br />
One of theses is loaded dynamically during role runtime using the `include_vars` module and set OS specifics variable's.

`NOT USED BY THIS ROLE`


## AUTHOR

Dany GINHOUX - https://github.com/dginhoux



## LICENSE

MIT


## INSPIRED FROM

This role is inspired and forked from this role https://github.com/atosatto/ansible-dockerswarm created by atosatto

