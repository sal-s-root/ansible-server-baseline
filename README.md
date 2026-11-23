# Ansible Linux baseline

A reusable role for disposable Debian and Ubuntu hosts, with explicit opt-in,
tagged tasks, templated configuration, and an independent verification playbook.

```sh
ansible-lint playbook.yml verify-baseline.yml roles/infra_baseline
ansible-playbook -i inventory.example.ini playbook.yml --syntax-check
# After configuring your own lab inventory:
ansible-playbook -i /path/to/inventory playbook.yml --check --diff
ansible-playbook -i /path/to/inventory playbook.yml
ansible-playbook -i /path/to/inventory verify-baseline.yml
```

Apply twice to check idempotence: the second completed run should report no
configuration changes. Package cache refreshes can change after their validity
window. The example inventory has no live targets.

## Role variables

| Variable | Default | Purpose |
|---|---|---|
| `infra_baseline_opt_in` | `false` | Explicit execution gate |
| `infra_baseline_packages` | Four diagnostic packages | Desired package presence |
| `infra_baseline_operator_group` | `laboperators` | Group owning the lab directory |
| `infra_baseline_directory` | `/opt/infra-lab` | Managed documentation directory |

The role does not change SSH, firewall rules, passwords, or sudo policy. See
[operations](RUNBOOK.md) and [verification evidence](VALIDATION.md). The Docker
inventory under `tests/` is for an isolated disposable test container only.
