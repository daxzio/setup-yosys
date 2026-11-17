# setup-yosys

This action downloads a prebuilt [Yosys](https://github.com/YosysHQ/yosys) from [daxzio/yosys-package](https://github.com/daxzio/yosys-package) and adds it to `PATH`. The job that uses it does not compile Yosys.

Supported runners: **Ubuntu 24.04** and **Ubuntu 26.04** (including **`ubuntu-latest`** while that label points at 26.04). By default the action downloads the tarball built for the runner’s `VERSION_ID` (`yosys-ubuntu-26.04.tar.gz` or `yosys-ubuntu-24.04.tar.gz`).

```yaml
name: Check
on: [push, pull_request]
jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: daxzio/setup-yosys@v1
      - run: yosys -V
```

Pin a release with `version`. The default is the latest package release.

```yaml
- uses: daxzio/setup-yosys@v1
  with:
    version: "0.71"
```

Stay on the 24.04 binary on a 26.04 runner (not recommended unless you know you need it):

```yaml
- uses: daxzio/setup-yosys@v1
  with:
    version: "0.71"
    ubuntu-version: "24.04"
```

## Tags

| Tag | Upstream |
|-----|----------|
| `0.71` | [Yosys v0.71](https://github.com/YosysHQ/yosys/releases/tag/v0.71) — assets for 24.04 and 26.04 |