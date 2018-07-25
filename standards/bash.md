---
category: Style Guides
expires: 2018-01-31T00:00:00.000Z
---

# Bash Style Guide

We follow the [shellcheck style guide](https://github.com/koalaman/shellcheck#style). In some circumstances shellcheck does not state preference.

This guide builds upon those standards.

## Variable Usage

It is useful to check variable existence and fail scripts if a variable does not exist.

Instead of doing this:

```sh
if [ -z "$VARIABLE" ];then
    echo "VARIABLE is blank";
  else
    echo "VARIABLE is set to '$VARIABLE'";
fi
```

or this

```sh
errMsg="is a required environment variable!"
VAR="${VARIABLE:?$errMsg}"
```

Check the variable when you use it:

```sh
echo "${VARIABLE:?}"
```

## Updating this manual

This manual, and by extension the MoJ Bash Style Guide, is not presumed to be infallible or beyond dispute. If you think something is missing or if you'd like to see something changed then:

- (optional) Start with the #development Slack channel. See what other developers think and you'll get an idea of how likely your proposal is of being accepted as a pull request even before you put in any work.
- Create a pull request against [MOJ technical-guidance repository](https://github.com/ministryofjustice/technical-guidance)
