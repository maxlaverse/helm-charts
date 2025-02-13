# Helm Charts

## How to use Helm repository

You need to add this repository to your Helm repositories:

```
helm repo add maxlaverse https://maxlaverse.github.io/helm-charts/
helm repo update
```

## Available Charts

### [soft-pod-memory-evicter](https://github.com/maxlaverse/soft-pod-memory-evicter)

A Kubernetes controller that proactively evicts Pods approaching their memory limits to allow graceful shutdowns before OOM kills occur.

### [ndots-admission-controller](https://github.com/maxlaverse/ndots-admission-controller)

A Kubernetes admission controller that optimizes DNS resolution performance by setting ndots:1 on Pod creation, reducing unnecessary DNS lookups.

## How to release

Bump version in `Chart.yaml`.

Then:

```bash
rm .cr-release-packages/*
cr package charts/soft-pod-memory-evicter
cr upload  --owner maxlaverse  --git-repo helm-charts --pages-branch=main --token <token>
cr index  --owner maxlaverse  --git-repo helm-charts --token <token> --pages-branch main -i ./
```
