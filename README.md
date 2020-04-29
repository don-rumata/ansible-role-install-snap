# Ansible Role: Install Snap

Install [Snap](https://snapcraft.io/) for Linux.

## Work on

```yaml
  platforms:
    - name: Fedora
      versions:
        - 31
        - 30
    - name: Ubuntu
      versions:
        - eoan
        - disco
        - cosmic
        - bionic
        - xenial
        - trusty
    - name: Debian
      version:
        - jessie
        - stretch
        - buster
        - stable
        - testing
    - name: EL (CentOS)
      versions:
        - 8
        - 7
    - name: opensuse
      vesrion:
        - tumbleweed
```

## Requirements

None.

## Role Variables

None.

## Dependencies

[min_ansible_version: 2.8](https://docs.ansible.com/ansible/latest/modules/snap_module.html)

## Example Playbook

`install-firefox-over-snap.yml`:

```yaml
- name: Install FireFox
  hosts: all
  strategy: free
  serial:
    - "100%"
  roles:
    - ansible-role-install-snap
  tasks:

    - name: Install FF over snap
      become: yes
      snap:
        name: firefox
        state: present
      tags:
        - firefox
        - snap
```

## License

Apache License, Version 2.0

## Author Information

[don Rumata](https://github.com/don-rumata)

## TODO

- Add tests.
