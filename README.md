# effx-lint-action ✅

GitHub action for linting [effx](https://www.effx.com) configuration files

### Usage

```
name: effx lint
on: push

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: lint effx configuration files
        uses: effxhq/effx-lint-action@master
        with:
          directory: /github/workspace
        env:
          EFFX_API_KEY: ${{ secrets.EFFX_API_KEY }}
```

### Environment Variables

📁 **`directory`** _(required)_ - The relative path to the directory containing configuration files you'd like linted.\
🔑 **`EFFX_API_KEY`** _(required)_ - Your effx API key.

Setting `directory` to `/github/workspace` enables linting for **all** files with the suffix **`effx.yaml`** in your repo.

### Workflow

1. Add this action to your repo.
2. Head over to the **[effx website](https://app.effx.com/account_settings)**, navigate to **Account Settings** and find your API key.
3. Add your effx API key by
   - navigating to your repo's settings
   - selecting **Secrets** from the side bar
   - typing **`EFFX_API_KEY`** into the name field
   - pasting your effx API key into the value field
4. The **`yml`** file for **`effx-lint-action`** will live in **`.github/workflows`**.
5. Create a file named, **`effx.yaml`** and populate it with configurations.
6. On pushing any branch, **`effx-lint-action`** will check to make sure all of your configurations have the correct format. 🥳
