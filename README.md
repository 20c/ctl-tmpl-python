copy `config.example.yaml` contents to `Ctl/config.yaml` of your target repository

copy `tmplvars.example.yaml` to `Ctl/tmplvars.yaml` in your target repository and edit as necessary.

Then in your target repostiroy

```
pip install ctl tmpl jinja2 pyyaml
ctl sync_python
```
