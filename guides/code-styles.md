---
category: Code styles
expires: 2019-10-13 (6 months from now)
---

# Programming language styles

We have been having discussions in the LAA Developer team about which code style guides we should use. It has been suggested that it would perhaps be a useful discussion to have across teams, as it is would be better to adopt similar standards across the department rather than just for the LAA. This PR is an attempt to widen this discussion to colleagues across the department so that we can decide a way forward.

Currently there are a number of languages that we use at LAA/MoJ, the main languages are (note: this is not an exhaustive list but rather just those that I am most aware of, please amend as needed):

- Ruby
- Java
- Javascript
- Python
- PL/SQL

## Questions

- should we adopt other organization's style guides? [gds](https://github.com/alphagov/styleguides) / [google](http://google.github.io/styleguide/) etc.
- what tools should we use to assess style compliance (e.g. rubocop)?
- should guides be advisory or mandatory?
- should we work to apply styles retrospectively (i.e. for legacy code)?
- there are various ancillary technologies that we use (YAML / HAML / ERB) should these be linted as well?
- how should we publicise adopted styles?

## User needs

There are no officially designated standards available as guidance that are MoJ specific. This can lead to variance across projects which can impact code quality.

There are [GDS code styles](https://github.com/alphagov/styleguides) that we may want to adopt, but there may also be reasons that we want to diverge from these.

## Principles

These are up for discussion.


## Tools

There are many [code linters](https://github.com/collections/clean-code-linters) available which we could utilise to monitor code style matchers.





