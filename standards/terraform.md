---
category: Style Guides
expires: 2018-01-31T00:00:00.000Z
---

# Terraform Style Guide

# Local and Variable usage

Variables in the the following form, indicate they do not change and are default values.

However, by creating a set of variables you allow the user or CI environment to be able to change those values on the fly with a `tfvars` file.

```hcl
# variables.tf
variable "foo" {
  type = "map"
}

# terraform.tfvars
default_tags = {
  Terraform              = "true"
  business-unit          = "OPG"
  application            = "<app_name>"
  is-production          = "false"
  environment-name       = "development"
  owner                  = "<email address>"
  infrastructure-support = "<email address>"
  runbook                = "<runbook address>
  source-code            = "<source code address>"
}
```

Instead use a local block and declare it there. This map can be added and merged with later on in code.

```hcl
locals {
  default_tags = {
    Terraform              = "true"
    business-unit          = "OPG"
    application            = "<app_name>"
    is-production          = "false"
    environment-name       = "development"
    owner                  = "<email address>"
    infrastructure-support = "<email address>"
    runbook                = "<runbook address>
    source-code            = "<source code address>"
  }
}
```
