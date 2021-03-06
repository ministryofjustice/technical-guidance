# Technical guidance

How we build and operate products at the Ministry of Justice. This repo
is inspired by, and borrows from, [GDS's technical guidance][gds-way]
site.

It's built using the gov.uk [tech-docs-template], and hosted using [GitHub Pages].

[gds-way]: https://github.com/alphagov/gds-way
[GitHub Pages]: https://pages.github.com
[tech-docs-template]: https://github.com/alphagov/tech-docs-template

## Getting started

To preview the site locally, we need to use the terminal, and run:

```bash
make preview
```

This will create a local web server, at `http://localhost:4567` This is only
accessible on our own computer, and won't be accessible to anyone else.

## Making changes

To make changes, edit the appropriate Markdown files in/below the
`source/documentation` directory.

Make sure to make changes in a branch, and issue a pull request when
you want them to be reviewed and published.

## Publishing changes

Any changes merged into the `main` branch will be published automatically.

Every change should be reviewed in a pull request, no matter how minor, and
we've enabled [branch protection][] to enforce this.

[branch protection]: https://help.github.com/articles/about-protected-branches/
