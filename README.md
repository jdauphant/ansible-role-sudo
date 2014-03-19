ansible-role-sudo
=================

Configure Sudo with Ansible

# Example
## Configuration

```
---
sudo_files:
  - name: usera
    vars:
      - "usera ALL=NOPASSWD: ALL"
  - name: group
    vars:
      - "%group ALL=NOPASSWD: ALL"
  - name: userb
    vars:
      - "userb ALL=(ALL:ALL) ALL"
  - name: userc
    vars:
      - "userc ALL = NOPASSWD: /usr/bin/lsof"
      - "userc ALL = NOPASSWD: /bin/mount"

```
## Integrated configuration :
```
---
 - hosts: all
   roles:
     - role: sudo
       sudo_files:
        - name: group
          vars:
           - "%group ALL=NOPASSWD: ALL"
```
