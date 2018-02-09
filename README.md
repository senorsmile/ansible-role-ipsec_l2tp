# ipsec_l2tp - An Ansible role to configure a vpn client

## largely based on the instructions from https://github.com/hwdsl2/setup-ipsec-vpn/blob/master/docs/clients.md#linux



# Usage

## add this repo under your ./roles/ dir

## define variables in inventory or ./hostvars/

  ```
  ## example values
  vpn_name:       'desired_vpn_name'
  vpn_server_ip:  '10.0.0.1'
  vpn_ipsec_psk:  'preshared key'
  vpn_user:       'username'
  vpn_password:   'password'
  vpn_def_route:  False
  vpn_routes:
    - 10.0.0.0/8
  ```

## add role to your playbook
---
- hosts:
    - vpn_clients
  become: True
  roles:
    - role: senorsmile.ipsec_l2tp

## run playbook
```
ansible-playbook -l localhost
```
