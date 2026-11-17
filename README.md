# setup-yosys

This action downloads a prebuilt [Yosys](https://github.com/YosysHQ/yosys) from [daxzio/yosys-package](https://github.com/daxzio/yosys-package) and adds it to `PATH`. The job that uses it does not compile Yosys.

Supported runner: `ubuntu-24.04` (not `ubuntu-latest` when that label points at a non-24.04 image).

```yaml
name: Check
on: [push, pull_request]
jobs:
  check:
    runs-on: ubuntu-24.04
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

## Tags

| Tag | Upstream |
|-----|----------|
| `0.71` | [Yosys v0.71](https://github.com/YosysHQ/yosys/releases/tag/v0.71) |