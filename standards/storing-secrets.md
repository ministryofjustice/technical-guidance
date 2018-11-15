---
category: Building software
expires: 2019-01-01
---
# Storing secrets

All our secrets should be adequately protected and suitably stored.

Use infrastructure-based secrets management services where possible:

- On the MOJ Cloud Platform, use [Kubernetes Secrets](https://ministryofjustice.github.io/cloud-platform-user-docs/02-deploying-an-app/003-add-secrets-to-deployment/)
- On Amazon Web Services (AWS), use the [Key Management Service (KMS)](https://aws.amazon.com/kms/)
- On Azure, use [Key Vault](https://azure.microsoft.com/en-gb/services/key-vault/)

## git-crypt

If you do need to store secrets within Git repositories they should be adequately protected.

[git-crypt](https://github.com/AGWA/git-crypt) has previously been used by MOJDT teams to encrypt those secrets and control who has the ability to view (decrypt) those secrets.

You must never store unencrypted secrets in code repositories.

## Preventing secret leaks

Git clones copies of repositories as local files/folders on your device as working copies to upload them again once you have made changes so it is possible to inadvertently upload unintended files - for example, private keys and other secrets which should not be uploaded or shared with anyone else.

You should use a secret scanner on your device to help you detect and prevent accidental committal of secrets and other private information to github.com. MOJ has used `git-secrets` in the past and there is some [guidance here on using `git-secrets`](https://github.com/ministryofjustice/technical-guidance/guides/using-git-secrets.md). GDS has used [`talisman`](https://github.com/thoughtworks/talisman) as well.
