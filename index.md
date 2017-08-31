# MOJ technical guidance

This site documents some of the technical decisions that the
[Ministry of Justice](https://www.gov.uk/government/organisations/ministry-of-justice)
has made for the products we operate.

It complements the [Service Manual](https://www.gov.uk/service-manual),
which covers service design more broadly.

## Standards

{% assign standards = site.pages
  | where: "standard", true
  | group_by: "category" %}

{% for standard_group in standards %}
{% if standard_group.name != "" %}
### {{ standard_group.name }}
{% else %}
### General standards
{% endif %}

{% for standard in standard_group.items %}
- [{{ standard.title }}]({{ standard.url }})
{% endfor %}
{% endfor %}

## Adding new guidance

Create a new Markdown file that follows this pattern, add a link to it
from this page, and make a pull request:

```markdown
---
category: The broader area this fits into
expires: yyyy-mm-dd (6 months from now)
---
# Thing you're writing a standard about

Introduction of a couple of paragraphs to explain why the thing you're
writing a standard about is important. The [title should probably be a
verb, not a noun][good-services-are-verbs] (e.g. “Storing source code”,
not “Code repositories”).

[good-services-are-verbs]: https://designnotes.blog.gov.uk/2015/06/22/good-services-are-verbs-2/

## User needs

Why do we do this thing? Who is it helping?

## Principles

What broad approaches do we follow when we do this thing?

## Tools

What specific bits of software (commercial or open source) do
we use to help us do this thing?
```

The service manual has some useful information on
[learning about and writing user needs](https://www.gov.uk/service-manual/user-research/start-by-learning-user-needs).
