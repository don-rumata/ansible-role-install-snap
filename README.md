# Ansible Role: Install Snap

[![License][license-image]][license-url] [![Ansible Galaxy][ansible-galaxy-image]][ansible-galaxy-url] [![CircleCI][circleci-image]][circleci-url]

Install [Snap](https://snapcraft.io/) for Linux.

## Work on

```yaml
  platforms:
    - name: Fedora
      versions:
        - 31
        - 32
    - name: Ubuntu
      versions:
        - xenial
        - bionic
        - focal
    - name: Debian
      version:
        - oldstable
        - stable
    - name: EL (CenOS)
      versions:
        - 7
        - 8
    - name: opensuse
      vesrion:
        - tumbleweed
        - 15.2
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

- ~~Add tests.~~
- Add more tests.

[license-image]: https://img.shields.io/github/license/don-rumata/ansible-role-install-snap.svg
[license-url]: https://opensource.org/licenses/Apache-2.0

[ansible-galaxy-image]: https://img.shields.io/badge/ansible_galaxy-don__rumata.ansible__role__install__snap-blue.svg
[ansible-galaxy-url]: https://galaxy.ansible.com/don_rumata/ansible_role_install_snap

[circleci-image]: https://circleci.com/gh/don-rumata/ansible-role-install-snap.svg?style=shield
[circleci-url]: https://circleci.com/gh/don-rumata/ansible-role-install-snap
