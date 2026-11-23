# Validation

Ansible lint and both syntax checks passed. The role was applied to a disposable Debian Bookworm container: first run `changed=4`, second run `changed=0`, both with zero failures. Independent package and directory verification passed with `changed=0`.

## Coverage

Debian Bookworm container with the Docker connection as root. The test inventory disables become for that container.
