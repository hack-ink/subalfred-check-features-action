<div align="center">

# [Subalfred check features action](https://github.com/hack-ink/subalfred-check-features-action)
### Use [`subalfred check features`](https://github.com/hack-ink/subalfred) to check your runtime code.

<img width="400" src="https://raw.githubusercontent.com/w3f/Grants-Program/master/static/img/badge_black.svg"/>

</div>

### Usage
> **Take [Polkadot code/repository](https://github.com/paritytech/polkadot) as an example.**

**Check single runtime.**
```yml
name: Checks
on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
jobs:
  features-checks:
    name: Task check features
    runs-on: ubuntu-latest
    steps:
      - name: Check
        uses: actions/subalfred-check-features-action@v0.1.5
        with:
          path: runtime/polkadot
```

**Check multiple runtimes at once.**
```yml
name: Checks
on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
jobs:
  features-checks:
    name: Task check features
    strategy:
      matrix:
        runtime: [runtime/polkadot, runtime/kusama, runtime/rococo]
    runs-on: ubuntu-latest
    steps:
      - name: Check ${{ matrix.runtime }}
        uses: hack-ink/subalfred-check-features-action@v0.1.5
        with:
          path: ${{ matrix.runtime }}
```
