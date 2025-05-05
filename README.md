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
        uses: sunbeam-labs/sbx_test_action@v1
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
  install-options:
    description: 'Options to be passed to the sunbeam install script'
    required: false
    default: ''
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

### Dev

I do the versioning in a silly way for this because of its usage. For minor bug fixes, after making the necessary updates in the main branch, update the current tag to point at the latest commit via `git tag -f <tag-name>` and then `git push --force origin <tag-name>`. Find a list of tags [here](https://github.com/sunbeam-labs/sbx_test_action/tags). If you're making significant enough changes to be worthy of a new tag (i.e. changes to the interface that will break old implementations) then create a new tag for your latest commit and update any uses of it in the necessary extensions.
