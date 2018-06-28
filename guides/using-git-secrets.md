---
category: Tools
expires: 2019-01-31
---
# Using git-secrets

## Overview

We use [git][git] is a [distributed version-control system][dvcs]. Git primarily works by comparing a local working copy of repository content against another branch, highlighting and controlling any changes.

As Git utilises a local folder structure (a clone of a repository) on your device, it is possible to inadvertently upload unintended files to Github.com - for example, private keys and other secrets which should not be uploaded or shared with anyone else.

You must use [git-secrets](https://github.com/awslabs/git-secrets) on your device to limit the possibility of accidentally uploading secrets files or information.

## How-to

### Install git-secrets

Installation instructions can be found in the [git-secrets repository](https://github.com/awslabs/git-secrets).

### Use our base configuration

We need to put in something here about where our base configuration is, meaning we likely have to create one or 'bless' the base one provided.

### Scanning for the first time

We should write some instructions about installing and scanning for the first time.
