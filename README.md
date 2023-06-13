# ROLE dginhoux.prometheus_gluster_exporter



## DESCRIPTION

This ansible role install, configure and uninstall prometheus gluster exporter.<br />
It can be deploy as binary downloaded from github OR as docker (no public image, you have to build an image and push to a registry)



## REQUIREMENTS

#### SUPPORTED PLATFORMS

This role require a supported platform.<br />
It will skip node with unsupported platform to avoid any compatibility problem.<br />
This behaviour can be bypassed by settings the following variable `skip_check_platform_compatibility=true`.

| Platform | Versions |
|----------|----------|
| Debian | buster, bullseye |
| Fedora | 33, 34, 35, 36, 37, 38 |
| EL | 7, 8 |

#### ANSIBLE VERSION

Ansible >= 2.13

#### DEPENDENCIES

None.



## INSTALLATION

#### ANSIBLE GALAXY

```shell
ansible-galaxy install dginhoux.prometheus_gluster_exporter
```
#### GIT

```shell
git clone https://github.com/dginhoux/ansible_role.prometheus_gluster_exporter dginhoux.prometheus_gluster_exporter
```


## USAGE

#### EXAMPLE PLAYBOOK

```yaml
- hosts: all
  roles:
    - name: start role dginhoux.prometheus_gluster_exporter
      ansible.builtin.include_role:
        name: dginhoux.prometheus_gluster_exporter
```


## VARIABLES

#### DEFAULT VARIABLES

Defaults variables defined in `defaults/main.yml` : 

```yaml
deploy_gluster_exporter: install
deploy_gluster_exporter_mode: binary
prometheus_gluster_exporter_docker_image: "" ## prom/gluster-exporter
prometheus_gluster_exporter_name: gluster_exporter
prometheus_gluster_exporter_version: 0.2.7
prometheus_gluster_exporter_arch: amd64
prometheus_gluster_exporter_download_url: >-
  "https://github.com/ofesseler/gluster_exporter/releases/download/
  v{{ prometheus_gluster_exporter_version }}/
  gluster_exporter-{{ prometheus_gluster_exporter_version }}.
  linux-{{ prometheus_gluster_exporter_arch }}.tar.gz"
prometheus_gluster_exporter_bin_path: /usr/local/bin/{{prometheus_gluster_exporter_name}}
prometheus_gluster_exporter_options: >-
  -listen-address :9189
  -metrics-path /metrics
  -gluster_executable_path /usr/sbin/gluster
  -volumes _all
  -log.level error
prometheus_gluster_exporter_state: started
prometheus_gluster_exporter_enabled: true
prometheus_gluster_exporter_port: 9189
prometheus_gluster_exporter_run_user: gluster_exporter
prometheus_gluster_exporter_nice_level: 0
```

#### DEFAULT OS SPECIFIC VARIABLES

Those variables files are located in `vars/*.yml` are used to handle OS differences.<br />
One of theses is loaded dynamically during role runtime using the `include_vars` module and set OS specifics variable's.

`NOT USED BY THIS ROLE`



## AUTHOR

Dany GINHOUX - https://github.com/dginhoux



## LICENSE

MIT
