# Ansible Role: Consul

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![centos-7](https://img.shields.io/badge/centos-7.x-orange?style=flat&logo=centos)](https://www.centos.org/)
[![centos-8](https://img.shields.io/badge/centos-8.x-orange?style=flat&logo=centos)](https://www.centos.org/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-consul?style=flat)](https://github.com/OnkelDom/ansible-role-consul/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-consul.svg?style=flat)](https://github.com/OnkelDom/ansible-role-consul/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-consul/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-consul)

## Description

Deploy [Consul](https://github.com/hashicorp/consul) system using ansible.

This is designed to handle services für prometheus service discoery or for consul template to generate prometheus file_sd files.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` |  {} | Set proxy environment variables |
| `consul_version` | 1.10.0 | Consul download Version |
| `consul_config_dir` | /etc/consul | Config Path |
| `consul_data_dir` | /var/lib/consul | Data store path |
| `consul_config_file` | config.json | Config file name |
| `consul_log_dir` | /var/log/consul | logfile dir |
| `consul_tls_dir` | "{{ consul_config_dir }}/tls" | tls dir |
| `consul_limit_nofile` | 8192 | set systemd nofile limit |
| `consul_binary_install_dir` | "/usr/local/bin" | Base binary path |
| `consul_system_user` | consul | User for Consul Template |
| `consul_system_group` | consul | Group for Consul Template |
| `consul_web_listen_port` | 8500 | Prometheus metrics listen Port |
| `consul_config` | [defaults/main.yml#L32](defaults/main.yml#L32) | see config exmaple in defaults file |

## Example

### Playbook

```yaml
---
- hosts: all
  roles:
  - onkeldom.consul
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
