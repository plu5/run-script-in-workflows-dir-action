# Run Script in Workflows Dir | Action

This is a convenience action to be able to run a script in .github/workflows easily without having to set permissions yourself or write the full path.

## Usage example

Assuming you have a script in ``.github/workflows/install.sh``, and you want to pass arguments `ubuntu` and `x64`

```yaml
name: CI - Testing Run Script in Workflows Dir | Action
on:
  workflow_dispatch:
jobs:
  testing_actions:
    name: Testing Action | Job
    runs-on: 'ubuntu-latest'
    steps:
      - uses: actions/checkout@v2
      
      - name: Run install.sh
        uses: plu5/run-script-in-workflows-dir-action@main
        with:
          script: 'install.sh'
          args: 'ubuntu x64'
```

## Settings

Option | Description | Required | Default | Example
---    | ---         | ---      | ---     | ---
script | Your script.<br> It needs to be the same directory as your action, or a relative path from `.github/workflows/`. | Yes | N/A | `install.sh`
args | Arguments you want to pass to the script, separated by space. | No | N/A | `ubuntu x64`
