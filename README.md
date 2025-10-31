# sbx_test_action
GH Action for testing sunbeam extensions

Usage:

```
jobs:  
  test-e2e:
    name: Test Extension with Sunbeam
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Test with Sunbeam
        uses: sunbeam-labs/sbx_test_action@v1
```

See the `inputs` section at the top of `action.yml` for a list of options.

## Dev

After making updates to the code, make a new release. The release action will take care of the rest.
