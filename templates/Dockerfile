FROM {{ from }}
{{ 'MAINTAINER %s' % maintainer if maintainer else '' }}

{% for inst in instructions %}
{{ inst }}
{% endfor %}

{% if show_role_comment %}
# This file is render by ansible.
# Check this role for detail:
# https://github.com/Yoctol/ansible-dockerfile
{% endif %}
