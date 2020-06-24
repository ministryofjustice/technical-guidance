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

Repositories should be [clearly named]({{ '/standards/naming-things' | relative_url }}),
and have an [appropriate licence]({{ '/standards/licencing-software-or-code' | relative_url }})
and enough documentation that someone new can get started with the
project.

Creating a new project from this [template repository] will add the
correct licence file, as well as adding our organisation default
`.gitignore` file and [github actions].

If your repository contains secrets rather than code, make it private
and restrict the people who have access to it. Discuss with the
security engineering team whether you should encrypt the contents of
the repository.

### Private repositories

By default, any [ministryofjustice organisation](https://github.com/ministryofjustice) member has no additional privileges. This means they can clone and pull public and internal repos only. Internal repos are essentially org-public, and anyone in the organisation can interact with them. Unless explicitly and strictly defined on a per-repository basis to override default permissions: private repositories should be considered "private" to your team/project.


[template repository]: https://github.com/ministryofjustice/template-repository
[github actions]: https://github.com/ministryofjustice/github-actions

### GitHub user accounts

If you already have a GitHub account from before you joined MOJ, you can choose whether to continue using it at MOJ or create a new one. Some people prefer to have continuity with previous work; others value the separation.

You must [add your MOJ email address to your
account](https://help.github.com/articles/adding-an-email-address-to-your-github-account/)
It doesn't matter if it's the 'primary email' or not and it's ok to make it private.
Maybe [use that email for notifications](https://help.github.com/articles/managing-notification-emails-for-organizations/)).

Bear in mind that you may wish to also have a home email address added to the
account as the 'backup email', so that you can keep control of the account after
you leave MOJ. Because whilst you won't retain MOJ repo permissions, it might be
prudent to retain the ability to change your account's public profile or delete
public comments. Home email addresses are not exposed to GitHub organisation
admins, aside from what is already public.

You don't have to use your real name or photo - just let your colleagues know
your username.

Ask the Digital Service Desk or a member of the webops team to add you
to the MOJ organisation. Our GitHub organisation requires that you use two-factor authorisation.
