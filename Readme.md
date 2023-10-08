# Using Helm to get values from a chart

>> helm show values weave-gitops --repo https://helm.gitops.weave.works > values.yaml

## Create repository for flux

> flux create source helm ww-gitops --url=https://helm.gitops.weave.works --export > source.yaml

# Create release

> gitops create dashboard ww-gitops --password=${PASSWORD} --export > release.yaml



# Use sops to encrypt and decrypt secrets for k8s

> create a gpg key pair
 see generate.sh script in ./gpg-key/generate-key.sh

> After generation, you will have a public and private key stored in gpg

Reference: https://www.youtube.com/watch?v=8pbdXAd-F44&t=1057

> get the value of your public key and store in git
> get the value of your private key and store that in your flux-system namespace secret
> configure flux to use the key to decrypt secrets


# encrypt secret inplace with sops

sops --encrypt \
    --encrypted-regex '^^(data|stringData)$' \
    --pgp <Value of your public key> \
    --in-place <Path to your secret.yaml>


# Using flux and age to stop secret in git for k8s

https://medium.com/picus-security-engineering/manage-your-secrets-with-mozilla-sops-and-gitops-toolkit-flux-cd-v2-7aa98f626001

