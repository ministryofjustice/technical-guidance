---
category: Building software
expires: 2019-01-01
---
# Storing secrets

All our secrets should be adequately protected and suitably stored.

Where possible, use infrastructure-based secrets management services such as [AWS Key Management Service](https://aws.amazon.com/kms/), [AWS Systems Manager Parameter Store](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-paramstore.html), [Microsoft Azure Key Vault](https://azure.microsoft.com/en-gb/services/key-vault/) or [Kubernetes Secrets](https://kubernetes.io/docs/concepts/configuration/secret/) on MOJ's Cloud Platforms.

## git-crypt

If you do need to store secrets within Github.com they should be adequately protected.

[git-crypt](https://github.com/AGWA/git-crypt) has previously been used by MOJDT teams to encrypt those secrets and control who has the ability to view (decrypt) those secrets.

You must never store unencrypted secrets in code repositories.
