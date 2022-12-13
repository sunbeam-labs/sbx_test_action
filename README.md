# sbx_test_action
GH Action for testing sunbeam extensions

Usage:

```
jobs:  
  test-e2e:
    name: Test Extension with Sunbeam
    runs-on: ubuntu-latest

    steps:
      - name: Test with Sunbeam
        uses: sunbeam-labs/sbx_test_action@v0
        with:
          extension-name: 'Ulthran/sbx_demic'
          extension-branch-name: ${{ github.head_ref }}
```

Options:

```
  sunbeam-version:
    description: 'Branch or tag of sunbeam to install'
    required: false
    default: 'stable'
  extension-name:
    description: 'Name of this extension (e.g. sunbeam-labs/sbx_template or Ulthran/sbx_demic)'
    required: true
  extension-branch-name:
    description: 'Branch name of extension to be tested (use /$/{/{ github.head_ref /}/} to get current branch for PRs)'
    required: true
  other-extensions:
    description: 'Any other extensions needed to run this one (use comma-separated string like "sunbeam-labs/sbx_one,other-user/sbx_two")'
    required: false
    default: ''
  test-directory:
    description: 'Directory that contains e2e tests which need all of sunbeam to run'
    required: false
    default: '.tests/e2e/'
```
