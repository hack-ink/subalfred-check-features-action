<div align="center">

# [Subalfred check features action](https://github.com/hack-ink/subalfred-check-features-action)
### Use [`subalfred check features`](https://github.com/hack-ink/subalfred) to check your runtime code.

<img width="400" src="https://raw.githubusercontent.com/w3f/Grants-Program/master/static/img/badge_black.svg"/>

</div>

### Usage
**Take [Polkadot code/repository](https://github.com/paritytech/polkadot) as an example.**
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
        uses: actions/subalfred-check-features-action@v0.1.0
        with:
          path: runtime/polkadot
```
