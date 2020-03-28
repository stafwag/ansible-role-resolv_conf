# Ansible Role: resolv_conf

An ansible role to configure /etc/resolv.conf

## Requirements

### Supported platforms

* Archlinux
* Debian
* FreeBSD
* NetBSD
* OpenBSD
* RedHat
* Suse

## Role Variables
### OS related variables

### Playbook related variables

* **resolv_conf**: "namespace"
  * **nameservers**: list of nameserver. Is set to quad9 by default.
      Defaults to:
```
        - 9.9.9.9
```
  * **domain**: string with the domain
  * **search**: list with search entries
  * **sortlist**: list with the sortlist entries
  * **options**: list with the options

## Dependencies

None

## Example Playbooks

### Set the nameserver to default

Set the nameserver to the default 9.9.9.9.

```
```

```
- name: configure ntp on the systems
  hosts: all
  become: true
  vars:
    ntp_servers:
      - 0.europe.pool.ntp.org
      - 1.europe.pool.ntp.org
      - 2.europe.pool.ntp.org
      - 3.europe.pool.ntp.org
  roles:
    - stafwag.ntpd
```

## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, website: http://www.wagemakers.be
