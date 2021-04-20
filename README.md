# Ansible Role: loki

## Description

Deploy [Loki](https://github.com/grafana/loki) fully featured logging stack using ansible.

This role is heavy inspired by https://github.com/cloudalchemy/ansible-prometheus

## Requirements

- Ansible >= 2.7 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `loki_version` | 2.2.1 | Loki package version. Also accepts `latest` as parameter. |
| `loki_skip_install` | false | Loki installation tasks gets skipped when set to true. |
| `prometheus_binary_local_dir` | "" | Allows to use local packages instead of ones distributed on github. As parameter it takes a directory where `prometheus` AND `promtool` binaries are stored on host on which ansible is ran. This overrides `prometheus_version` parameter |
| `loki_config_dir` | /etc/loki | Path to directory with loki configuration |
| `loki_config_auth_enabled` | false | Loki authentication config. Compatible with [official configuration](https://grafana.com/docs/loki/latest/configuration/#supported-contents-and-default-values-of-lokiyaml) |
| `loki_config_server` | | Loki server config. Compatible with [official configuration](https://grafana.com/docs/loki/latest/configuration/#server_config) |
| `loki_config_ingester` | | Loki ingester config. Compatible with [official configuration](https://grafana.com/docs/loki/latest/configuration/#ingester_config) |
| `loki_config_schema_config` | | Loki schema config. Compatible with [official configuration](https://grafana.com/docs/loki/latest/configuration/#schema_config) |
| `loki_config_storage_config` | | Loki storage config. Compatible with [official configuration](https://grafana.com/docs/loki/latest/configuration/#storage_config) |
| `loki_config_compactor` | | Loki compactor config. Compatible with [official configuration](https://grafana.com/docs/loki/latest/configuration/#compactor_config) |
| `loki_config_limits_config` | | Loki limits config. Compatible with [official configuration](https://grafana.com/docs/loki/latest/configuration/#limits_config) |
| `loki_config_chunk_store_config` | | Loki chunk store config. Compatible with [official configuration](authentication) |
| `loki_config_table_manager` | | Loki table manager config. Compatible with [official configuration](https://grafana.com/docs/loki/latest/configuration/#table_manager_config) |
| `loki_config_ruler` | | Loki ruler config. Compatible with [official configuration](https://grafana.com/docs/loki/latest/configuration/#ruler_config) |

## Example

### Playbook

```yaml
---
- hosts: all
  roles:
  - ansible-loki
```
