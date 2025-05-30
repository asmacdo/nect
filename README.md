## Usage

Call the action in your workflow:

```yaml
uses: asmacdo/nect@main
with:
  name: dandi-cli
  marker: REQUIRES_CLI_PR
  default_install: "pip install dandi[test] @ git+https://github.com/dandi/dandi-cli"
  source_install: "pip install -e .[test]"
```

### Markers

In your PR description or comments, include:

`requires_cli_pr: https://github.com/dandi/dandi-cli/pull/123`
