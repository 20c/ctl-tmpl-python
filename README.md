# ctl-tmpl-python
ctl python package template


Use src dir with

```yaml
packages = [
    { include = "{{ project_name }}", from = "src" },
]
```

Use tox for doing proper matrix on libraries, poetry does not lend itself well to that

```yaml
    - name: python_template
      type: template
      config:
        # template root directory (path)
        source: "{{ ctx.cachedir }}/github.com/20c/ctl-tmpl-python"
        # template output directory (path)
        output: "{{ ctx.home }}/.."
        walk_dirs:
          - .
        vars:
          - Ctl/tmplvars.yaml
        ignore:
          - \.git/
```
