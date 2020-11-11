# effx-lint-action ✅

GitHub action for linting [effx](https://www.effx.com) configuration files

### Usage

```
name: effx lint
on: push

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: lint effx configuration files
        uses: effxhq/effx-lint-action@master
        with:
          directory: ${GITHUB_WORKSPACE}
```

### Environment Variables

📁 **`directory`** _(required)_ - The relative path to the directory containing configuration files you'd like linted.

Setting `directory` to `${GITHUB_WORKSPACE}` enables linting for **all** files with the suffix **`effx.yaml`** in your repo.

### Workflow

1. Add this action to your repo.
2. The **`yml`** file for **`effx-lint-action`** will live in **`.github/workflows`**.
3. Create a file named, **`effx.yaml`** or matching **`*.effx.yaml`** and populate it with configurations.
4. On pushing any branch, **`effx-lint-action`** will check to make sure all of your configurations have the correct format. 🥳
