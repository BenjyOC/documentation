# Ansible

## Main

  - [ansible-ks](https://github.com/BenjyOC/ansible-ks) => branche v2

## Roles ansible

  - [ansible-base-setup](https://github.com/BenjyOC/ansible-base-setup)
  - [ansible-wireguard](https://github.com/BenjyOC/ansible-wireguard)
  - [ansible-prometheus-node-exporter](https://github.com/BenjyOC/ansible-prometheus-node-exporter)
  - [ansible-prometheus-blackbox-exporter](https://github.com/BenjyOC/ansible-prometheus-blackbox-exporter)
  - [ansible-postfix](https://github.com/BenjyOC/ansible-postfix)

## Run Ansible

```bash
ansible-galaxy install -r requirements.yml -f
ansible-playbook -i inventories/hosts playbook.yml -v
```
