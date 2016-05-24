FROM {{ from }}
{{ 'MAINTAINER %s' % maintainer if maintainer else '' }}

{% for inst in instructions %}
{{ inst }}
{% endfor %}

{% if show_role_comment %}
# This file is rendered by ansible to the host {{ ansible_hostname }} with ssh user {{ ansible_user_id }} on {{ template_run_date }}.
# Check this role for detail: https://github.com/Yoctol/ansible-dockerfile
{% endif %}
