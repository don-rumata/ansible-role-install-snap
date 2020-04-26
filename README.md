Ansible Role: Install Snap
===================================================

Install [Snap](https://snapcraft.io/) for Linux.

Requirements
------------

None.

Role Variables
--------------

None.

Dependencies
------------

[Ansible v2.8.](https://docs.ansible.com/ansible/latest/modules/snap_module.html)

Example Playbook
----------------

install-firefox-over-snap.yml
```yml
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


License
-------

Apache License, Version 2.0

Author Information
------------------

[don Rumata](https://github.com/don-rumata)

TODO
----
  - Add tests.
