# cpenv Publish Module
A Github Action for publishing your cpenv modules.

# Usage
See [action](action.yml) for more details.

```
name: Publish to ShotGrid

on:
  push:
    tags:
      - '*'

jobs:
  publish:
    name: Publish cpenv module to ShotGrid
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Publish cpenv module
        uses: cpenv/github-actions-publish@v1
        with:
          repo_name: bns_shotgun
          repo_type: shotgun
          repo_shotgrid_base_url: ${{ secrets.SHOTGRID_BASE_URL }}
          repo_shotgrid_script_name: ${{ secrets.SHOTGRID_SCRIPT_NAME }}
          repo_shotgrid_api_key: ${{ secrets.SHOTGRID_API_KEY }}
          repo_shotgrid_module_entity: CustomNonProjectEntity01
          repo_overwrite: true
```

# Resources
- [cpenv](https://github.com/cpenv/cpenv)
- [tk-cpenv](https://github.com/cpenv/tk-cpenv)
- [Github Actions Quickstart](https://docs.github.com/en/actions/quickstart)
- [Setting up Github Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)
