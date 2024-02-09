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
docker_swarm_action: enable


##### define inventory groups for identify manager and worker nodes
docker_swarm_inventory_manager_group_name: group_pxe_manager
docker_swarm_inventory_worker_group_name: group_pxe_worker


##### bridge configuration
docker_swarm_bridge_custom_subnet: 192.168.192.0/23
docker_swarm_bridge_custom_gw: 192.168.192.1


#### nodes labels)
docker_swarm_labels: []


##### node availability (active, drain, pause)
docker_swarm_availability: active


##### cluster and nodes variables
##
## read : https://docs.ansible.com/ansible/latest/collections/community/docker/docker_swarm_module.html
##
# docker_swarm_advertise_addr
# docker_swarm_api_version
# docker_swarm_autolock_managers
# docker_swarm_ca_force_rotate
# docker_swarm_ca_path
# docker_swarm_client_cert
# docker_swarm_client_key
# docker_swarm_data_path_addr
# docker_swarm_data_path_port
# docker_swarm_default_addr_pool
# docker_swarm_dispatcher_heartbeat_period
# docker_swarm_docker_host
docker_swarm_election_tick: 10
# docker_swarm_heartbeat_tick
# docker_swarm_keep_old_snapshots
# docker_swarm_listen_addr
# docker_swarm_log_entries_for_slow_followers
# docker_swarm_name
# docker_swarm_node_cert_expiry
# docker_swarm_rotate_manager_token
# docker_swarm_rotate_worker_token
# docker_swarm_signing_ca_cert
# docker_swarm_signing_ca_key
# docker_swarm_snapshot_interval
# docker_swarm_ssl_version
# docker_swarm_subnet_size
# docker_swarm_task_history_retention_limit
docker_swarm_timeout: 20
# docker_swarm_tls
# docker_swarm_tls_hostname
# docker_swarm_use_ssh_client
# docker_swarm_validate_certs
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

