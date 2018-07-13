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

## Preventing secret leaks

We use [git][git] is a [distributed version-control system][dvcs]. Git primarily works by comparing a local working copy of repository content against another branch, highlighting and controlling any changes.

As Git utilises a local folder structure (a clone of a repository) on your device, it is possible to inadvertently upload unintended files to Github.com - for example, private keys and other secrets which should not be uploaded or shared with anyone else.

You should use a secret scanner on your device to help you detect and prevent accidental committal of secrets and other private information to github.com. MOJ has used `git-secrets` in the past and there is some [guidance here on using `git-secrets`](https://github.com/ministryofjustice/technical-guidance/guides/using-git-secrets.md). GDS has used [`talisman`](https://github.com/thoughtworks/talisman) as well.
