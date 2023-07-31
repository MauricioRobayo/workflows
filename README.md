# My shared workflows

Reusable workflows are YAML-formatted files, very similar to any other workflow file. As with other workflow files, you locate reusable workflows in the .github/workflows directory of a repository. Subdirectories of the workflows directory are not supported.

For a workflow to be reusable, the values for on must include workflow_call:

```yml
on:
  workflow_call:
```

## Using inputs and secrets in a reusable workflow

You can define inputs and secrets, which can be passed from the caller workflow and then used within the called workflow. There are three stages to using an input or a secret in a reusable workflow.

In the reusable workflow, use the inputs and secrets keywords to define inputs or secrets that will be passed from a caller workflow.

```yml®
on:
  workflow_call:
    inputs:
      config-path:
        required: true
        type: string
    secrets:
      envPAT:
        required: true
```

https://docs.github.com/en/enterprise-cloud@latest/actions/using-workflows/reusing-workflows#creating-a-reusable-workflow
