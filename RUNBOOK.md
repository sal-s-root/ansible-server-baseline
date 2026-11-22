# Controlled configuration changes

1. Copy `inventory.example.ini` to a local inventory outside the repository.
2. Add only your disposable Debian or Ubuntu VM; confirm its SSH host key.
3. Run syntax checking, then `--check --diff` against that inventory.
4. Review proposed changes before applying. Use `--ask-become-pass` if required.
5. Apply once, apply again, and record whether the second run reports zero changes.

No SSH policy, firewall, user passwords, or sudo permissions are changed.
A real VM application and idempotence check have not been performed here.

## Post-apply verification

Run `ansible-playbook -i /path/to/inventory verify-baseline.yml` after applying to your lab VM. It inspects package presence and directory metadata without changing them. This verification playbook has been syntax checked; remote execution remains an exercise. SSH host key checking remains enabled.
