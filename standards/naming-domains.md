---
category: Operating services
---
# Naming domains

All MOJ services should be served from `*.service.gov.uk` or
`*.service.justice.gov.uk` domains. MOJ infrastructure or justice-wide services
may be eligible for a `*.justice.gov.uk` domain.

## Requesting domain changes

If you need to request a new domain or changes to an existing domain,
email the [MOJ Domains team](mailto:domains@digital.justice.gov.uk),
who will help ensure that your domain meets this standard and our
[wider standards for naming]({% link standards/naming-things.md
%}#naming-things). The Domains team can also help identify which of the
domains below that your service is eligible to be hosted in.


## Domain your service can have a subdomain of

### `service.gov.uk`

The [service standard](https://www.gov.uk/service-manual/technology/get-a-domain-name)
already sets out when and how to get a `*.service.gov.uk` subdomain:
public-facing services which have passed their beta assessment should
be able to get one.

### `service.justice.gov.uk`

All other MOJ services should be served from a
`*.service.justice.gov.uk` subdomain, including:

- public-facing services which haven’t yet passed a beta assessment
  (but may be in private beta with a restricted set of users)
- internal-facing services

Cloud-hosted software-as-a-service used by MOJ staff (like Gmail or
Office365), or on which MOJ has a corporate presence
(like [GitHub](https://github.com/ministryofjustice/) or
[Trello](https://trello.com/mojds/home)) are not required to be served
from a `*.service.justice.gov.uk` subdomain

### `justice.gov.uk`

Only services which are core, MOJ-wide infrastructure, like email or
videoconferencing, or otherwise applicable to users across the entire
justice system (like the intranet) may use a `*.justice.gov.uk`
subdomain. Contact the [MOJ Domains team](mailto:domains@digital.justice.gov.uk)
to find out if your service is eligible.

## Staff-facing sites

Any staff-facing sites which exist as part of public-facing services
should also be on a `*.service(.justice).gov.uk` domain.

For example `staff.prisonvisits.service.gov.uk` is the staff-facing
side of `www.prisonvisits.service.gov.uk`.

## Pre-production environments

This standard includes pre-production environments. For those, use this
domain naming pattern:

`<application>.<environment>.<service-name>.service(.justice).gov.uk`

For example: `staff.staging.prisonvisits.service.gov.uk`.

This pattern makes the relationships between domains clear, grouping
environments by service and applications by shared environment.

Pre-production environments and [hosted prototypes](https://www.gov.uk/service-manual/design/making-prototypes#sharing-code-prototypes)
should also use authentication (such as HTTP basic auth) to prevent
public users who come across them thinking they’re real.

Pre-production environments can also use different styling as a way of
making it clear to users which environment they’re in - but that’s more
useful for people working on the service to not modify data in
production than to keep users out. GOV.UK publishing apps do this,
for example compare GOV.UK Signon in their [Staging](https://signon.staging.publishing.service.gov.uk)
and [Production](https://signon.publishing.service.gov.uk) environments.

## Pitfalls of non `.gov.uk` domains

You should follow the above advice for these sorts of reasons:

- Public government things should on principle be on government domains
- The ownership of a gov domain can be tracked to a government body by a member of the public
- By using .gov.uk we never have the problem that a domain's control is lost to a previous supplier or staff member who set it up and moved on. Domain renewals are easier to keep on top of when centralized. When the domain is not renewed, it can be snapped up by a squatter.
- The Service Manual says [not to use the crown, New Transport font etc](https://www.gov.uk/service-manual/design/making-your-service-look-like-govuk#if-your-service-isnt-on-govuk))
- Unfamiliar domains look untrustworthy, putting off users including internal staff from using the service
- Normalizing the use of unfamiliar domains increases the risk of phishing
- Google's anti-phishing protection could at any time flag a site as 'deceptive' if it looks like a GOV.UK site but is served on a non .gov.uk domain. We've experienced several occasions when this happens, likely because of the use of the crown, New Transport font or "GOV.UK" text at the top left. Chrome users cannot use the site - instead they see this error:

  [
    <img class="img-medium" src="{{ "/images/deceptive-site-alert.png" | relative_url }}">
  ]({{ "/images/deceptive-site-alert.png" | relative_url }})

  Whilst we can get Google to remove the flag, it will keep happening.
