## Balanced [![Build Status](https://travis-ci.org/balanced-ops/ansible-balanced.svg)](https://travis-ci.org/balanced-ops/ansible-balanced)

## Installing roles

```bash
ansible-galaxy install -r requirements.yml -p `pwd`/roles
```

### Re-installing roles

```bash
ansible-galaxy install -r requirements.yml -p `pwd`/roles --ignore-errors
```

## Debugging while running vagrant

### Collect facts

```bash
ansible -i ./vagrant_ansible_inventory_default all -m ec2_facts -u vagrant -vvv -c ssh --private-key ~/.vagrant.d/insecure_private_key
```

### Execute a playbook

```bash
ansible-playbook -i ./vagrant_ansible_inventory_default -u vagrant -vvv -c ssh --private-key ~/.vagrant.d/insecure_private_key site.yml
```


## Gotachas

- setup ansbile inside virtualenv and run it from there
- make sure you synced over your folders (TODO: make this part of the play)
- if you use vagrant, destroy the VM, and re-provision it, you have to delete the host file key otherwise ansible can't start
