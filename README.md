# [ansible-update-authorized-keys](https://github.com/fnkr/ansible-update-authorized-keys)

Ansible playbook that replaces ssh keys in the `authorized_keys` file of all non-system users and the root user.

## Usage

**1)** Define which keys to replace (see `keys_to_replace.yaml` for example)

```yaml
keys_to_replace:
  # '<old key>': '<new key>'
  'ssh-rsa AAAAB3NzaC1yc2E... fnkr@example.com': 'ssh-ed25519 AAAAC3NzaC1lZDI1NTE5... fnkr@example.com'
```

**2)** Run playbook

```
ansible-playbook replace_keys.yaml -e @keys_to_replace.yaml -i ~/my-inventory.ini
```
