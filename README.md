# run-re-target - Run a Re project in GitHub Actions

This action builds and runs your project using the [Re build system](https://github.com/osdeverr/rebs).

### Usage

```yaml
jobs:
  example:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout
      uses: actions/checkout@v3

    # You have to set up the Re environment once before running any Re actions.
    - name: Setup Re
      uses: osdeverr/actions-setup-re@v2

    # The action will fail if your executable fails
    # to build or returns a non-zero exit code.
    - name: Run unit tests
      uses: osdeverr/actions-run-re-target@v2

      # All of the following parameters are optional
      with:
        path: .
        target: .unit-tests

        arch: x64
        configuration: debug
```

**NOTE:** You have to set up Re using [osdeverr/actions-setup-re](https://github.com/osdeverr/actions-setup-re) before you can use this action!
