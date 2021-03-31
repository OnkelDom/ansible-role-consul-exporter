# Ansible Role: snmp exporter

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![centos-7](https://img.shields.io/badge/centos-7.x-orange?style=flat&logo=centos)](https://www.centos.org/)
[![centos-8](https://img.shields.io/badge/centos-8.x-orange?style=flat&logo=centos)](https://www.centos.org/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-consul-exporter?style=flat)](https://github.com/OnkelDom/ansible-role-consul-exporter/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-consul-exporter.svg?style=flat)](https://github.com/OnkelDom/ansible-role-consul-exporter/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-consul-exporter/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-consul-exporter)

## Description

Deploy and manage consul-exporter [Consul Exporter](https://github.com/prometheus/consul_exporter) using ansible.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)
- Community Packages: `ansible-galaxy collection install community.general`

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` | {} | Proxy environment variables |
| `consul_exporter_version` | 0.7.1 | Set exporter version |
| `consul_exporter_web_listen_address` | 0.0.0.0 | Set exporter ip-adress |
| `consul_exporter_web_listen_port` | 9107 | Set exporter listen-port |
| `consul_exporter_log_level` | warn | Loglevel for the exporter |
| `consul_exporter_log_format` | "logger:stdout?json=true" | Logformat for the exporter |
| `consul_exporter_allow_firewall` | false | Enabled/Disabled Firewalld and open the port |
| `consul_exporter_binary_local_dir` | /usr/local/bin | Binary Path |
| `consul_exporter_system_user` | prometheus | Set exporters system user |
| `consul_exporter_system_group` | prometheus | Set exporters system group |
| `consul_exporter_consul_token` | exmaple | consul token |
| `consul_exporter_params` | [defaults/main.yml](defaults/main.yml) | define startup params |

## Example

### Playbook

```yaml
- hosts: all
  become: yes
  roles:
    - onkeldom.consul_exporter
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
