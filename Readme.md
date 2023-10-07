# Using Helm to get values from a chart

>> helm show values weave-gitops --repo https://helm.gitops.weave.works > values.yaml

## Create repository for flux

> flux create source helm ww-gitops --url=https://helm.gitops.weave.works --export > source.yaml

# Create release

> gitops create dashboard ww-gitops --password=${PASSWORD} --export > release.yaml
