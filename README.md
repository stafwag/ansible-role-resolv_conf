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
---
- name: setup /etc/resolv.conf
  hosts: all
  become: true
  roles:
    - role: stafwag.resolv_conf
```

### Empty /etc/resolv.conf

```
---
- name: setup /etc/resolv.conf
  hosts: all
  become: true
  roles:
    - role: stafwag.resolv_conf
      resolv_conf:
```

### Configure /etc/resolv.conf

```
---
- name: setup /etc/resolv.conf
  hosts: all
  become: true
  roles:
    - role: stafwag.resolv_conf
      resolv_conf:
        nameservers:
          - 10.10.10.10
        domain:
          intern.stafnet.local
        search:
          - intern.stafnet.local
          - dmz.stafnet.local
```

## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, website: http://www.wagemakers.be
