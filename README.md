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
    - type: command
      name: printenv
      config:
        shell: true
        command:
          - "echo \"ctx.home: {{ ctx.home }}\""
          - "echo \"ctx.tmpdir: {{ ctx.tmpdir }}\""
          - "echo \"ctx.cachedir: {{ ctx.cachedir }}\""
          - "echo \"ctx.userhome: {{ ctx.userhome }}\""
          - "echo \"{{ input.plugin }}\""
          - "echo \"{{ plugin.git_template }}\""
          - "echo \"{{ plugin.copy }}\""
          - "echo \"{{ ctx.config }}\""

    # git repo for copying setup

    - name: repo_python_template
      type: git
      config:
        repo_url: git@github.com:20c/ctl-tmpl-python
        branch: origin/mvbase

    # template for copying template assets

    - name: python_template
      type: template
      config:
        # template root directory (path)
        source: "{{ ctx.cachedir }}/github.com/20c/ctl-tmpl-python/base"
        # template output directory (path)
        output: "{{ ctx.home }}/.."
        walk_dirs:
          - .
        vars:
          - Ctl/tmplvars.yaml
        ignore:
          - \.git/

    # chain plugin for entire template process

    - name: sync_tmpl
      type: chain
      config:
        chain:
          - stage: git_clone
            plugin: git_template
            action:
              name: clone

          - stage: git_pull
            plugin: git_template
            action:
              name: pull

          - stage: django_template
            plugin: django_template

```
