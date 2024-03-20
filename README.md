# Reusable Workflows for Tidi

This repository contains reusable workflows for Tidi. It's a collection of
workflows that can be referenced in GitHub Action workflows.

## `tidiorg/workflows/build-container`

This workflow builds a container image and pushes it to a container registry.

```yaml
name: On Push

on:
  workflow_dispatch:
  push:
    branches:
      - main

jobs:
  build-container:
    name: Build Container
    permissions:
      packages: write
      id-token: write
      contents: read
    secrets: inherit
    
    uses: tidiorg/workflows/.github/workflows/build-container.yaml@v1

```

To customize the build, you can pass in the following inputs:

- `name`: The name of the image to build. Defaults to the repository name.
- `container-file`: The path to the Dockerfile. Defaults to `Dockerfile`.

See the rest of the [workflow file](./.github/workflows/build-container.yml) for
more details.
