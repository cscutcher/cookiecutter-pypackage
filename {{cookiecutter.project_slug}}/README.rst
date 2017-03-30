{% set is_open_source = cookiecutter.open_source_license != 'Not open source' -%}
{% set use_github = cookiecutter.use_github == 'y' -%}
{% set use_pypi = cookiecutter.use_pypi_deployment_with_travis == 'y' -%}
{% set use_travis = cookiecutter.use_travis == 'y' -%}
{% set use_rtd = cookiecutter.use_rtd == 'y' -%}
===============================
{{ cookiecutter.project_name }}
===============================

{% if is_open_source -%}
{% if use_pypi -%}
.. image:: https://img.shields.io/pypi/v/{{ cookiecutter.project_slug }}.svg
        :target: https://pypi.python.org/pypi/{{ cookiecutter.project_slug }}
{% endif -%}
{% if use_github and use_travis -%}
.. image:: https://img.shields.io/travis/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}.svg
        :target: https://travis-ci.org/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}
{% endif -%}
{% if use_rtd -%}
.. image:: https://readthedocs.org/projects/{{ cookiecutter.project_slug | replace("_", "-") }}/badge/?version=latest
        :target: https://{{ cookiecutter.project_slug | replace("_", "-") }}.readthedocs.io/en/latest/?badge=latest
        :alt: Documentation Status
{% endif -%}
{% endif -%}
{% if use_github -%}
.. image:: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/shield.svg
     :target: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/
     :alt: Updates
{%- endif -%}

{{ cookiecutter.project_short_description }}

{% if is_open_source -%}
* Free software: {{ cookiecutter.open_source_license }}
{% if use_rtd -%}
* Documentation: https://{{ cookiecutter.project_slug | replace("_", "-") }}.readthedocs.io.
{% endif -%}
{% endif -%}

Features
--------

* TODO

Credits
---------

This package was created with Cookiecutter_ and the `cscutcher/cookiecutter-pypackage`_ template base on the `audreyr/cookiecutter-pypackage`_ project template.

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _`audreyr/cookiecutter-pypackage`: https://github.com/audreyr/cookiecutter-pypackage
.. _`cscutcher/cookiecutter-pypackage`: https://github.com/cscutcher/cookiecutter-pypackage

