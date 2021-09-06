# post-command-buildkite-plugin
A buildkite plugin for running commands in the `post-command` hook

## Usage

If the command step exits with 0 exit code, `on_success` command block will be executed, otherwise `on_failure` block will be executed.
The `always` command block will be exectued after `on_success` or `on_failure` block.

```yml
steps:
  plugin:
    - hasura/post-checkout#v1.0.0:
        on_success: |
          echo "success"
        on_failure: |
          echo "failure"
        always: |
          echo "command ran"
```

