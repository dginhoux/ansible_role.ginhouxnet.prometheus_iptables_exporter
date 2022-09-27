# ROLE dginhoux.prometheus_iptables_exporter



## DESCRIPTION

This ansible role install, configure and uninstall prometheus iptables exporter.<br />
It can be deploy as binary downloaded from github OR as docker (no public image, you have to build an image and push to a registry)



## REQUIREMENTS

#### SUPPORTED PLATFORMS

This role require a supported platform.<br />
It will skip node with unsupported platform to avoid any compatibility problem.<br />
This behaviour can be bypassed by settings the following variable `asserts_bypass=True`.

| Platform | Versions |
|----------|----------|
| Debian | buster, bullseye |
| Fedora | 33, 34, 35, 36 |
| EL | 7, 8 |

#### ANSIBLE VERSION

Ansible >= 2.12

#### DEPENDENCIES

None.



## INSTALLATION

#### ANSIBLE GALAXY

```shell
ansible-galaxy install dginhoux.prometheus_iptables_exporter
```
#### GIT

```shell
git clone https://github.com/dginhoux/ansible_role.prometheus_iptables_exporter dginhoux.prometheus_iptables_exporter
```


## USAGE

#### EXAMPLE PLAYBOOK

```yaml
- hosts: all
  roles:
    - name: start role dginhoux.prometheus_iptables_exporter
      ansible.builtin.include_role:
        name: dginhoux.prometheus_iptables_exporter
```


## VARIABLES

#### DEFAULT VARIABLES

Defaults variables defined in `defaults/main.yml` : 

```yaml
deploy_iptables_exporter: install
deploy_iptables_exporter_mode: binary
prometheus_iptables_exporter_docker_image: registry-build.infra.ginhoux.net:5001/ginhoux.net/iptables-exporter
prometheus_iptables_exporter_name: iptables_exporter
prometheus_iptables_exporter_version: 0.1.1
prometheus_iptables_exporter_arch: x86_64
prometheus_iptables_exporter_download_url: >-
  https://github.com/kbknapp/iptables_exporter/releases/download/
  v{{prometheus_iptables_exporter_version}}/
  {{ prometheus_iptables_exporter_name }}-v{{prometheus_iptables_exporter_version}}-
  {{prometheus_iptables_exporter_arch}}-linux-musl.tar.gz
prometheus_iptables_exporter_bin_path: /usr/local/bin/{{prometheus_iptables_exporter_name}}
prometheus_iptables_exporter_options: ""
prometheus_iptables_exporter_state: started
prometheus_iptables_exporter_enabled: true
prometheus_iptables_exporter_port: 9455
prometheus_iptables_exporter_run_user: iptables-exporter
prometheus_iptables_exporter_nice_level: 0
```

#### DEFAULT OS SPECIFIC VARIABLES

Those variables files are located in `vars/*.yml` are used to handle OS differences.<br />
One of theses is loaded dynamically during role runtime using the `include_vars` module and set OS specifics variable's.

`NOT USED BY THIS ROLE`



## AUTHOR

Dany GINHOUX - https://github.com/dginhoux



## LICENSE

MIT
