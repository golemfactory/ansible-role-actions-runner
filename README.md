# GitHub Actions runner deployment

This Ansible role allows for adding and removing new instances of self-hosted GitHub Actions runners.

## Requirements

The role requires a GitHub personal access token with appropriate scopes. The token should be added to the environment under `PERSONAL_ACCESS_TOKEN` variable. When creating a repo runner the `repo` scope is required. For organization runners, the token must have `admin:org` scope.

Install the following Ansible role:
```
ansible-galaxy install monolithprojects.github_actions_runner
```

# Running

Assuming you want to add a new self-hosted runner with the name `golem-runner` to an organization:
```
ansible-playbook install.yml --extra-vars "runner_name=golem-runner github_account=my_account runner_org=yes"
```

All available variables can be inspected in `defaults/main.yml`.
