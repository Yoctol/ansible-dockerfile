Role Name
=========

Role to render dockerfile with ease.

Requirements
------------

Ansible >= 1.2

Role Variables
--------------

```yaml
---
# Required, the path to render docker file on the host.
dest: ~/Dockerfile

# Optional, the args of template module except `src` and `dest`.
template_options: {}

# Opitonal, whether to show details in comments.
show_role_comment: true

# Required, the image name to be used in FROM instruciton as the base image.
from: scratch

# Optional, the maintainer to be used in MAINTAINER isntruction.
matainer: ''

# Optional, other instructions to be written in dockerfile.
# It would fail if invalid instruction is used.
instructions: []
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
