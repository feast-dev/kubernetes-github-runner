# Kubernetes Github Runner

This repository contains a single Kubernetes deployment that registers a group of self-hosted Github Actions runners on Kubernetes. Based on the work from [this repository](https://github.com/tcardonne/docker-github-runner).

### Installation

1. Make a copy of `deployment.yaml`.
2. Edit the environmental variables based on the following variables:

| Variable              | Description                                                                |
|-----------------------|----------------------------------------------------------------------------|
| GITHUB_ACCESS_TOKEN   | Personal Access Token that is used to dynamically fetch a new runner token |
| RUNNER_REPOSITORY_URL | The runner will be linked to this repository URL                           |

`GITHUB_ACCESS_TOKEN` must have `repo` access for repository level runners. Please see the following [document](https://github.com/tcardonne/docker-github-runner#environment-variables) for more configuration options

3. Deploy to Kubernetes:

```
kubectl apply -f deployment.yaml
```

4. Confirm that the self-hosted runners appear in GitHub:

![](/runners.png)
