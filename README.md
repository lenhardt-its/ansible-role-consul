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

## Description

Deploy [Consul](https://github.com/hashicorp/consul) system using ansible.

This is designed to handle services für prometheus service discoery or for consul template to generate prometheus file_sd files.

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)
- Community Packages: `ansible-galaxy collection install community.general`

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` |  {} | Set proxy environment variables |
| `consul_version` | 0.25.1 | Consul Template download Version |
| `consul_config_dir` | /etc/consul | Config Path |
| `consul_template_dir` | "{{ consul_config_dir }}/templates" | Template store path |
| `consul_config_file` | config.hcl | Config file name |
| `consul_allow_firewall` | false | Allow access on firewalld port |
| `consul_binary_install_dir` | "/usr/local/bin" | Base binary path |
| `consul_system_user` | "{{ consul_user | default('consul') }}" | User for Consul Template |
| `consul_system_group` | "{{ consul_group | default('consul') }}" | Group for Consul Template |
| `consul_web_listen_port` | 8888 | Prometheus metrics listen Port |
| `consul_config_consul` | {} | Configure consul entpoint |
| `consul_config_vault` | {} | Configure vault entpoint |
| `consul_config_default` | {} | Configure default options |
| `consul_config_wait` | {} | Configure wait options |
| `consul_config_deduplicate` | {} | Configure deduplication options |
| `consul_config_telemetry` | {} | Configure telemetry options |
| `consul_config_exec` | {} | Configure exec options |
| `consul_config_syslog` | {} | Configure syslog options |
| `consul_templates_config` | {} | Configure prometheus file_sd templates |

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
