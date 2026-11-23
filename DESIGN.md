# Design decisions

Desired state lives in a reusable role. An explicit opt-in and OS-family check constrain targets. The independent verification playbook inspects packages and file metadata. Check mode previews changes; a second actual apply is used to verify idempotence.

See README.md for operation and VALIDATION.md for the checks actually performed.
