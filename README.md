# Ansible Role: pushprox

An Ansible role that installs Prometheus PushProx on Ubuntu|Debian|Redhat-based machines with systemd|Upstart|sysvinit.

## Requirements

All needed packages will be installed with this role.

## Role Variables

| Variable                         | Type   | Comment                                            |
|----------------------------------|--------|----------------------------------------------------|
| pushprox_client_fqdn             | string | FQDN to register with                              |
| pushprox_client_proxy_url        | string | Push proxy to talk to                              |
| pushprox_proxy_listen_port       | string | Address to listen on for proxy and client requests |


## Dependencies

- None

## Example Playbook

```yaml
- hosts: exporter-inside
  roles:
    - role: s5unty.pushprox
      pushproxy_client_fqdn: {{ ansible_host }}
      pushproxy_client_proxy_url: "http://${Prometheus-outside}:8080"
```

## License

GPLv2
