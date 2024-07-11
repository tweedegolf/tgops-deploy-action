# TGOPS deploy action step

Deploy a tgops project.

## Usage

```
# ...

on:
  workflow_dispatch:
    inputs:
      env:
        description: Deploy environment
        required: true
        type: choice
        options:
          - staging
          - production

jobs:

  # ...

  docker:
    runs-on: ubuntu-latest
    steps:
      # ...

      - name: Deploy
        uses: tweedegolf/tgops-deploy-action@main
        with:
          env: ${{ inputs.env }}
          tgops-token: ${{ secrets.TGOPS_TOKEN }}
          deploy-token: ${{ secrets.DEPLOY_TOKEN }}

      # ...

  # ...
```
