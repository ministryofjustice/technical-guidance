---
category: Operating services
---
# Naming domains

All services with real users and which look like GOV.UK should be on
`*.service.gov.uk` or `*.service.justice.gov.uk`.

### service.gov.uk

The [service standard](https://www.gov.uk/service-manual/technology/get-a-domain-name)
already sets out when and how to get a `*.service.gov.uk` subdomain:
public-facing services which have passed their beta assessment should
be able to get one.

### service.justice.gov.uk

All other services with real users and which look like GOV.UK should be
on here, including:

- public-facing services which haven’t yet passed their beta assessment
(but may be in private beta with a restricted set of real users)
- internal services which look like GOV.UK (although [they can’t use the
crown, New Transport font etc](https://www.gov.uk/service-manual/design/making-your-service-look-like-govuk#if-your-service-isnt-on-govuk))

## Staff-facing sites

Any staff-facing sites which exist as part of public-facing services
should also be on the `*.service(.justice).gov.uk` domain.

For example `staff.prisonvisits.service.gov.uk` is the staff-facing
side of `www.prisonvisits.service.gov.uk`.

## Pre-production environments

This standard includes pre-production environments. For those, use this
domain naming pattern:

`<application>.<environment>.<service-name>.service(.justice).gov.uk`

A real example would be `staff.staging.prisonvisits.service.gov.uk`.

This pattern makes the relationships between domains clear, grouping
environments by service and applications by shared environment.

Pre-production environments and [hosted prototypes](https://www.gov.uk/service-manual/design/making-prototypes#sharing-code-prototypes)
should also use authentication (such as HTTP basic auth) to prevent
public users who come across them thinking they’re real.

Pre-production environments can also use different styling as a way of
making it clear to users which environment they’re in - but that’s more
useful for people working on the service to not modify real data in
production than to keep real users out. GOV.UK publishing apps do this,
for example compare GOV.UK Signon in their [Staging](https://signon.staging.publishing.service.gov.uk)
and [Production](https://signon.publishing.service.gov.uk) environments.

## Pitfalls of non .gov.uk domains

You should follow the above advice for these sorts of reasons:

- Public government things should on principle be on government domains

- The ownership of a gov domain can be tracked to a government body by a member of the public

- By using .gov.uk we never have the problem that a domain's control is lost to a previous supplier or staff member who set it up and moved on. Domain renewals are easier to keep on top of when centralized. When the domain is not renewed, it can be snapped up by a squatter.

- The Service Manual says [not to use the crown, New Transport font etc](https://www.gov.uk/service-manual/design/making-your-service-look-like-govuk#if-your-service-isnt-on-govuk))

- Unfamiliar domains look untrustworthy, putting off users including internal staff from using
the service

- Normalizing the use of unfamiliar domains increases the risk of phishing

- Google's anti-phishing protection could at any time flag a site as 'deceptive' if it looks like a GOV.UK site but is served on a non .gov.uk domain. We've experienced several occasions when this happens, likely because of the use of the crown, New Transport font or "GOV.UK" text at the top left. Chrome users cannot use the site - instead they see this error:

  [
    <img class="img-medium" src="{{ "/images/deceptive-site-alert.png" | relative_url }}">
  ]({{ "/images/deceptive-site-alert.png" | relative_url }})

  Whilst we can get Google to remove the flag, it will keep happening.
