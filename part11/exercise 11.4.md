# 11.4 Date and Directory Contents

In this exercise, I extended my GitHub Actions workflow with additional steps.

New commands added:

```yaml
- name: Print date
  run: date

- name: List directory contents
  run: ls -l
```

Main concepts learned:

- GitHub Actions workflows can execute Linux terminal commands.
- The `date` command prints the current date and time from the GitHub virtual machine.
- The `ls -l` command lists files in long format.

One important thing I learned is that the GitHub Actions environment starts almost empty by default.

Even though the repository exists on GitHub, the workflow environment does not automatically contain the project files.

This means that additional steps are needed later to download the repository into the virtual machine.

Main takeaway:
GitHub Actions workflows run inside temporary Linux virtual machines where commands can be executed step by step.
