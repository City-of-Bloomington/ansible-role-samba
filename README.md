# Samba
This role allows for maintaining Samba configuration on Ubuntu servers

## Dependencies
- City-of-Bloomington.linux

## Samba Share Configuration
It makes no sense to install Samba without setting up shares.  Also, shares are very particular to the host they are on.  So, this role expects two smb.conf template files to exist in the inventory:

* group_vars/samba/templates/smb.conf
* host_vars/{{ host }}/templates/smb.conf

The group_vars smb.conf contains global samba configuration.  The host smb.conf contains the shares.  The global smb.conf should be written to look for shares.conf.

## Example Playbook
```yml
- hosts: samba
  become: yes
  roles:
    - City-of-Bloomington.samba
```

## Copying and License
This material is copyright 2021 City of Bloomington, Indiana
It is open and licensed under the GNU General Public License (GPL) v3.0 whose full text may be found at:
https://www.gnu.org/licenses/gpl.txt

