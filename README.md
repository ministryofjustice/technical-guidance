# Technical guidance

How we build and operate products at the Ministry of Justice. This repo
is inspired by, and borrows from, [GDS's technical guidance][gds-way]
site.

It's built using [Jekyll][], and hosted using [GitHub Pages][]. It
incorporates HTML, SCSS, JavaScript, and images from [GDS's Tech Docs
Template][tech-docs-template], and reworks them to work with Jekyll
instead of [Middleman][].

[gds-way]: https://github.com/alphagov/gds-way
[Jekyll]: https://jekyllrb.com
[GitHub Pages]: https://pages.github.com
[tech-docs-template]: https://github.com/alphagov/tech-docs-template
[Middleman]: https://middlemanapp.com

## Getting started

To preview the site locally, we need to use the terminal.

Install Ruby and [Bundler][bundler], preferably with a [Ruby version
manager][rvm].

[rvm]: https://www.ruby-lang.org/en/documentation/installation/#managers
[bundler]: http://bundler.io/

Once you have Ruby and Bundler set up, you can install this project's
dependencies by running the following in this directory:

```bash
bundle install
```

## Making changes

To make changes, edit the appropriate Markdown files in this project.
Jekyll (and therefore this site) uses [kramdown][] for its Markdown
processing.

Make sure to make changes in a branch, and issue a pull request when
you want them to be reviewed and published.

[kramdown]: https://kramdown.gettalong.org/syntax.html

## Previewing

We can preview our changes locally by running this command:

```bash
bundle exec jekyll serve --watch
```

This will create a local web server, probably at http://127.0.0.1:4000
(look for the `Server address:` line). This is only accessible on our
own computer, and won't be accessible to anyone else. It's also set up
to automatically update (thanks to `--watch`) when we make changes to
the working Markdown files.

## Publishing changes

Because we're using GitHub Pages, any changes merged into the `master`
branch will be published automatically. Every change should be reviewed
in a pull request, no matter how minor, and we've enabled [branch
protection][] to enforce this.

[branch protection]: https://help.github.com/articles/about-protected-branches/
