Payloads-Mangle
=========

This role is used to Mangle payloads for the RVA/RPT programs.

Requirements
------------

None

Role Variables
--------------

| Variable | Description | Default | Required |
|----------|-------------|---------|----------|
| output_path | The path to store the payloads | /share/Working/payloads-auto/ | no |
| mangle_target_globs | A dictionary of items to target for Mangle operations. See sample playbook below | None | yes |


Dependencies
------------

None

Example Requirements
--------------------

```yaml
---

- src: https://github.com//ansible-role-payloads-mangle.git
  scm: git
  name: payloads-mangle
```

Example Playbook
----------------

```yaml
- name: Linux Built Payloads
  hosts: localhost
  vars:
    mangle_target_globs:
      - target: /share/Working/payloads-auto/*uru*delay26s-*exe
        inflate: 250
  roles:
    - payloads-mangle
```

Running the Play
----------------

```bash
# Install requirements
ansible-galaxy install -r requirements.yml

# Run the playbook
ansible-playbook -i inventory.yml playbook.yml
```

License
-------

None
