# :computer: ROLE dginhoux.docker_swarm

## :scroll: DESCRIPTION

This ansible role init, configure and remove a swarm cluster.
Nodes have to be fitted in two groups in ansible inventory.
Docker engine need to be installed and running before.
Every nodes used (manager and worker) must be online.



## :nut_and_bolt: REQUIREMENTS

#### SUPPORTED PLATFORMS

This role require a supported platform. 
It will skip node with unsupported platform to avoid any compatibility problem.
This behaviour can be bypassed by settings this variable `asserts_bypass=True`.

| Platform | Versions |
|----------|----------|
| Debian | buster, bullseye |
| Fedora | 33, 34, 35, 36 |
| EL | 7, 8 |


#### ANSIBLE VERSION

Ansible >= 2.12


#### DEPENDENCIES

None.


## :inbox_tray: INSTALLATION

#### ANSIBLE GALAXY

```shell
ansible-galaxy install dginhoux.docker_swarm
```

#### GIT

```shell
git clone https://github.com/dginhoux/ansible_role.docker_swarm dginhoux.docker_swarm
```


## :rocket: USAGE

#### EXAMPLE PLAYBOOK

```yaml
- hosts: all
  roles:
    - name: start role dginhoux.docker_swarm
      ansible.builtin.include_role:
        name: dginhoux.docker_swarm
      vars:
        docker_swarm_default_addr_pool: 10.0.0.0/8
        docker_swarm_inventory_manager_group_name: group_srv_pxe_manager
        docker_swarm_inventory_worker_group_name: group_srv_pxe_worker
        docker_swarm_node_docker_host: unix://var/run/docker.sock
        docker_swarm_node_labels: []
        docker_swarm_subnet_size: 24
        
```


## :factory: VARIABLES
#### DEFAULT VARIABLES
Role default variables from `defaults/main.yml` : 

| Variable Name | Value |
|---------------|-------|
|docker_swarm_inventory_manager_group_name | <pre> group_srv_pxe_manager </pre> |
|docker_swarm_inventory_worker_group_name | <pre> group_srv_pxe_worker </pre> |
|docker_swarm_subnet_size | <pre> 24 </pre> |
|docker_swarm_default_addr_pool | <pre> 10.0.0.0/8 </pre> |
|docker_swarm_node_docker_host | <pre> unix://var/run/docker.sock </pre> |
|docker_swarm_node_labels | <pre> []<br> </pre> |


#### CONTEXT VARIABLES

Those variables are located in `vars/*.yml` are used to handle OS differences ; One of theses is loaded dynamically during role
runtime using the `include_vars` module and set OS specifics variable's.





## :man: AUTHOR

[![Author](https://img.shields.io/badge/maintained%20by-dginhoux-e00000?style=flat-square)](https://github.com/dginhoux)


## :bookmark_tabs: LICENSE

[![License](https://img.shields.io/github/license/dginhoux/ansible_role.docker_swarm?style=flat-square)](https://github.com/dginhoux/ansible_role.docker_swarm/blob/master/LICENSE)