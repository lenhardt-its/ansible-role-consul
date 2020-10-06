# Ansible Role: consul template

## Description

Deploy [Consul](https://github.com/hashicorp/consul) system using ansible.

This playbook ist only designed to generate Prometheus fileservice discovery files from Consul service dicovery.

## Dependencys

This role depens on ansible-role-prometheus

## Requirements

- Ansible >= 2.6 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` |  {} | Set proxy environment variables |
| `consul_version` | 0.25.1 | Consul Template download Version |
| `consul_config_dir` | /etc/consul | Config Path |
| `consul_template_dir` | "{{ consul_config_dir }}/templates" | Template store path |
| `consul_config_file` | config.hcl | Config file name |
| `consul_firewalld_state` | "disabled" | Allow access on firewalld port |
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
  - ansible-role-consul
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
