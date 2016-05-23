FROM {{ from }}
{{ 'MAINTAINER %s' % maintainer if maintainer else '' }}

{% for inst in instructions %}
{{ inst }}
{% endfor %}

{% if show_role_comment %}
# This file is rendered by ansible with user {{ template_uid }} to the host {{ template_host }} on {{ template_run_date }}.
# Check this role for detail: https://github.com/Yoctol/ansible-dockerfile
{% endif %}
