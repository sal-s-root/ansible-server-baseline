# Ansible server baseline

## Purpose

Replace manual setup with repeatable desired-state configuration and a cautious rollout process.

## Run locally

```sh
ansible-playbook -i inventory.example.ini playbook.yml --syntax-check
# After configuring your disposable VM:
# ansible-playbook -i /path/to/inventory playbook.yml --check --diff
```

## Scope and limitations

Requires Ansible and a disposable Debian/Ubuntu VM for execution. The example inventory contains no active targets. Syntax validation does not demonstrate deployment or idempotence.

## Engineering notes

See [LEARNING.md](LEARNING.md) for the design decisions, verification evidence,
and next steps. Never commit credentials, private hostnames, or real incident data.
