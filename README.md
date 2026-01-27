![Main Workflow](https://github.com/kobiton/action-setup-ninja/workflows/Main%20Workflow/badge.svg)

# setup-ninja

Github Action for configuring ninja build tool into PATH

Official ninja-build binaries are downloaded from [ninja-build](https://github.com/ninja-build/ninja/releases) github releases and added to the PATH of runner.

## Quickstart
A simple matrix workflow which build CMake project with Ninja
```yaml
jobs:
  build:
    runs-on: ${{ matrix.config.os }}
    strategy:
      matrix:
        config:
          - { name: "Windows MSVC", os: windows-latest, cc: "cl", cxx: "cl" }
          - { name: "Ubuntu gcc", os: ubuntu-latest, cc: "gcc", cxx: "g++" }
        
    steps:
      - name: Setup Ninja
        uses: kobiton/action-setup-ninja@master
        with:
          # ninja version to download. Default: 1.11.1
          version: 1.11.1
        
```

### Action Reference: All Input/Output & Defaults
[action.yml](https://github.com/kobiton/action-setup-ninja/blob/master/action.yml) 

## License
All the content in this repository is licensed under the MIT License.

Copyright (c) 2024 Kobiton Inc.
Copyright (c) 2019-2020 Ashutosh Varma
Copyright (c) 2026 qr243vbi
