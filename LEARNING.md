# Engineering notes: Repeatable configuration

## Objective

Express a small server baseline as desired state rather than a collection of manual commands.

## Design decisions

- Use built-in modules for packages, groups, directories, and managed files.
- Require a lab opt-in and the Debian OS family before applying changes.
- Provide an empty example inventory and a check-mode procedure for review.

## Verification performed

| Check | Observed result |
|---|---|
| `ansible-playbook -i inventory.example.ini playbook.yml --syntax-check` | Passed; exit 0 as expected |

## What the evidence establishes

Only syntax checking was performed. No remote VM was configured, and second-run idempotence is unverified. Package metadata refreshes depend on network access.

## Next exercise

Apply to a disposable VM, capture the first run, then verify a second run reports no configuration changes. Add a role when reuse justifies it.
