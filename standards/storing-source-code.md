---
category: Building software
expires: 2018-01-31
---
# Storing source code

All our source code is open by default, and stored on well-known,
public code hosting services. At the MOJ, we use GitHub.

We follow the principles set out in the service manual for managing the
code that we write:

- [use version control](https://www.gov.uk/service-manual/technology/maintaining-version-control-in-coding)
- [make source code open](https://www.gov.uk/service-manual/technology/making-source-code-open-and-reusable)

You should keep secrets separate from source code, and keep them private.

## GitHub

New repositories for products and services live in the
[ministryofjustice organisation](https://github.com/ministryofjustice)
on GitHub.

You can use your personal GitHub account (but you should [add your MOJ
email address to your account](https://help.github.com/articles/adding-an-email-address-to-your-github-account/),
and maybe [use that for notifications](https://help.github.com/articles/managing-notification-emails-for-organizations/)).
Ask the Digital Service Desk or a member of the webops team to add you
to the organisation. Our GitHub organisation requires that you use
two-factor authorisation.

Repositories should be [clearly named]({{ '/standards/naming-things' | relative_url }}),
and have an [appropriate licence]({{ '/standards/licencing-software-or-code' | relative_url }})
and enough documentation that someone new can get started with the
project.

If the repository contains secrets rather than code, make it private
and restrict the people who have access to it. Discuss with the
security engineering team whether you should encrypt the contents of
the repository.
