# Helm Charts

## How to use Helm repository

You need to add this repository to your Helm repositories:

```
helm repo add maxlaverse https://maxlaverse.github.io/helm-charts/
helm repo update
```

## How to release
Bump version in `Chart.yaml`.

Then:
```bash
rm .cr-release-packages/*
cr package charts/soft-pod-memory-evicter
cr upload  --owner maxlaverse  --git-repo helm-charts --pages-branch=main --token <token>
cr index  --owner maxlaverse  --git-repo helm-charts --token <token> --pages-branch main -i ./
```
