---
category: Operating services
---
# Documenting owners of infrastructure

All of your infrastructure resources should be tagged with details of their owners, what service they are part of, and what type of environment they are in.

Without this, teams responsible for supporting your services (security, finance, and web operations) may not be able to keep your infrastructure secure, paid for by the right people, and appropriately supported. Documenting this on the infrastructure itself ensures that it's as accurate and up-to-date as possible.

You should do this even if you're managing infrastructure in your own account: other teams may end up needing access to that account, or may receive access via another account.

## Tagging your infrastructure

All of our existing cloud hosting providers support tagging ([AWS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html), [Azure](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-using-tags), [vCloud](https://blogs.vmware.com/vsphere/2012/03/creating-custom-metadata-using-the-vcloud-api.html)). If your infrastructure is defined in code ([as it should be](https://www.gov.uk/service-manual/technology/manage-your-software-configuration#use-infrastructure-as-code)), you can probably specify your tags in that code.

## Tags you should use

To ensure we can consistently search for, and report on, the tags we use, you should use the following tags. In all values, only use acronyms if you're confident that someone from another part of government would understand them.

- `business-unit`: Should be one of `HQ`, `HMPPS`, `OPG`, `LAA`, `HMCTS`, or `CICA`. If none of these are appropriate, use an appropriate name for the area of the MOJ responsible for the service.
- `application`: Should be the full name of the application or service (and acronym version, if commonly used), e.g. `Prison Visits Booking`, `Claim for Crown Court Defence/CCCD`.
- `component` (optional): Which part of the system this infrastructure is for, e.g. `Staff booking interface`, `API gateway`. If there's a common name for the type of component, use that (e.g. `front-end`, `api`, `message-queue`)
- `is-production`: `true` or `false`, to indicate if the infrastructure is part of, or supports, live production services
- `environment-name`: The name the owners use to refer to the environment; typically something like `production`, `staging`, `test`, or `development`.
- `owner`: The team responsible for the overall service. Should be of the form `<team-name>: <team-email>`.
- `infrastructure-support`: The team responsible for managing the infrastructure. Should be of the form `<team-name>: <team-email>`.
- `runbook` (optional): The URL of the service's runbook.
- `source-code` (optional): The URL(s) for any source code repositories related to this infrastructure, comma separated.
