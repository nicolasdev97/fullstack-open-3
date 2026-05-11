# 11.3 Hello World

In this exercise, I created my first GitHub Actions workflow.

I learned that GitHub Actions workflows must be placed inside:

```bash
.github/workflows/
```

I created a file called:

```bash
hello.yml
```

Workflow content:

```yaml
name: Hello World

on:
  push:

jobs:
  hello_world_job:
    runs-on: ubuntu-latest

    steps:
      - name: Print message
        run: echo "Hello World!"
```

Main concepts learned:

- `on: push`
  Runs the workflow every time changes are pushed to GitHub.

- `runs-on`
  Defines the operating system used by GitHub's virtual machine.

- `steps`
  List of commands executed during the workflow.

- `run`
  Executes terminal commands.

I also learned that GitHub Actions runs on GitHub servers, not on my local machine.

After pushing the workflow to GitHub, I was able to see the execution logs inside the Actions tab of the repository.

Main takeaway:
GitHub Actions automates tasks using YAML workflow files and virtual environments.
