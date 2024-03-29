
# {{ project_name }}

[![PyPI](https://img.shields.io/pypi/v/{{ project_name }}.svg?maxAge=60)](https://pypi.python.org/pypi/{{ project_name }})
[![PyPI](https://img.shields.io/pypi/pyversions/{{ project_name }}.svg?maxAge=600)](https://pypi.python.org/pypi/{{ project_name }})
[![Tests](https://github.com/20c/{{ project_name }}/workflows/tests/badge.svg)](https://github.com/20c/{{ project_name }})
[![LGTM Grade](https://img.shields.io/lgtm/grade/python/github/20c/{{ project_name }})](https://lgtm.com/projects/g/20c/{{ project_name }}/alerts/)
[![Codecov](https://img.shields.io/codecov/c/github/20c/{{ project_name }}/master.svg)](https://codecov.io/github/20c/{{ project_name }})

{{ package.description }}

{% if package.installable %}
## Introduction

```sh
pip install {{ project_name }}
```
{% endif %}
{% if package.documentation %}

## Documentation

Documentation is created with mkdocs and available here:

**stable**: <http://{{ project_name }}.readthedocs.io/en/stable/>

**latest**: <http://{{ project_name }}.readthedocs.io/en/latest/>
{% endif %}

## Changes

The current change log is available at <https://github.com/20c/{{ project_name }}/blob/master/CHANGELOG.md>

{% if package.license == "Apache-2" %}
## License

Copyright {{ package.copyright }} 20C, LLC

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this software except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
{% endif %}
