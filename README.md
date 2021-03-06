Role Name
=========

Role to render dockerfile with ease.

Requirements
------------

Ansible >= 1.2

Role Variables
--------------

```yaml
# Required, the path where dockerfile to be rendered on the host.
dest: ~/Dockerfile

# Opitonal, whether to show the details of role in comments. Default true.
show_role_comment: true

# Required, the image to be used in FROM instruciton as the base image.
from: scratch

# Optional, the maintainer to be used in MAINTAINER instruction.
maintainer: ''

# Optional, other instructions to be written in dockerfile.
# It would fail if invalid instruction type is used.
instructions: []

# Optional template arguments, which are the args of template module except `src`.
# If not set, default template settings are used.
# Check http://docs.ansible.com/ansible/template_module.html.
owner:
group:
mode:
backup:
force:
validate:
selevel:
serole:
setype:
seuser:
```


Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - role: dockerfile
       dest: ~/docker/Dockerfile
       template_options: owner=root mode=u=rw,g=r,o=r
       show_role_comment: true
       from: python:latest
       matainer: me
       instructions:
         - ADD /my/app /to/app/path
         - CMD /init.sh
```

License
-------

MIT

Author Information
------------------

Yoctol Info Inc.
