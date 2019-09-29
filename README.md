# Ansible Role: redis_exporter

[![Build Status](https://travis-ci.org/cimon-io/ansible-redis-exporter.svg?branch=master)](https://travis-ci.org/cimon-io/ansible-redis-exporter)
[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)

## Description

Deploy prometheus [redis exporter](https://github.com/oliver006/redis_exporter) using ansible.

## Requirements

- Ansible >= 2.6 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `redis_exporter_version` | 1.0.0-RC6.1 | Redis exporter package version. Also accepts latest as parameter. |
| `redis_exporter_system_group` | "redis-exp" | System group used to run redis_exporter |
| `redis_exporter_system_user` | "redis-exp" | System user used to run redis_exporter |
| `redis_exporter_env` | `{ PG_EXPORTER_WEB_LISTEN_ADDRESS: ":9187", DATA_SOURCE_NAME: "redis://postgres@localhost:5432/postgres?sslmode=disable" }` | Redis_exporter environment variables for configuration

## Example

### Playbook

Use it in a playbook as follows:
```yaml
- hosts: all
  roles:
    - cimon-io.redis-exporter
```

## License

This project is licensed under MIT License.
