# Helm Charts

## How to use Helm repository

You need to add this repository to your Helm repositories:

```
helm repo add maxlaverse https://maxlaverse.github.io/helm-charts/
helm repo update
```

## How to release
```bash
cr package charts/soft-pod-memory-evicter
cr upload  --owner maxlaverse  --git-repo helm-charts --token <token>
cr index  --owner maxlaverse  --git-repo helm-charts --token <token> -i ./
```
