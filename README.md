# Ansible Role:

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-systemd-tiumesyncd.svg)](https://github.com/OnkelDom/ansible-role-systemd-tiumesyncd/tags)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-systemd-tiumesyncd)](https://github.com/OnkelDom/ansible-role-systemd-tiumesyncd/issues)
[![GitHub license](https://img.shields.io/github/license/OnkelDom/ansible-role-systemd-tiumesyncd)](https://github.com/OnkelDom/ansible-role-systemd-tiumesyncd/blob/master/LICENSE)

## Description

Configure Systemd Timesyncd using ansible.

## Requirements

- Ansible >= 2.5 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `systemd_timesyncd` | true | Enable or Disable service |
| `systemd_timesyncd_time_zone` | "Europe/Berlin" | Set timezone |
| `systemd_timesyncd_time_server` | "time.cloudflare.com" | Set primary timeserver |
| `systemd_timesyncd_time_server_fallback` | "0.de.pool.ntp.org 1.de.pool.ntp.org 2.de.pool.ntp.org" | Set fallback timeservers |

## Example

```yaml
- hosts: all
  roles:
    - onkeldom.ansible-role-systemd-timesyncd
  vars:
    systemd_timesyncd: false
    systemd_timesyncd_time_zone: "Europe/Berlin"
    systemd_timesyncd_time_server: "time.cloudflare.com"
    systemd_timesyncd_time_server_fallback: "0.de.pool.ntp.org 1.de.pool.ntp.org 2.de.pool.ntp.org 3.de.pool.ntp.org"
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
