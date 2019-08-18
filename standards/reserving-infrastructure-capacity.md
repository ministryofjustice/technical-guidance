---
category: Operating services
---
# Reserving infrastructure capacity

To get the best value for money from cloud infrastructure, we should
pay in advance for parts of it that are going to be in active use over
a long period.

This guidance should be followed wherever possible, but is particularly
applicable to
[AWS](https://aws.amazon.com/ec2/pricing/reserved-instances/) and
[Azure](https://azure.microsoft.com/en-us/pricing/reserved-vm-instances/).

## Principles

### Only reserve instances for long-lived infrastructure

Reserving infrastructure allows us to make a significant saving over
paying for it on demand, but only if that class of infrastructure is in
use over the period in which the savings are made.

The best indicator that we have of this is if that class of
infrastructure has been (and, therefore, is likely to continue to be)
in active use for the length of the reservation.

Given that most infrastructure reservation systems operate on a one- or
three-year basis, we should **only consider for reservation any
infrastructure that has existed for at least one year**.

### Allow for change without wasting reservations

Our infrastructure estate is undergoing a lot of changes at the moment,
with consolidation, re-hosting, and re-architecting taking place on
many fronts. This means it's difficult to predict what infrastructure
we'll need in future, so we should **only make reservations for one
year at a time**.

In addition, to avoid reserving infrastructure that we end up not
needing as a result of those changes, we should **only reserve up to
70% of the infrastructure we'd consider for reservation**.

**Teams provisioning infrastructure should ensure they can easily
change instance types within a given family**, to allow ease of
upgrading to more cost-efficient instance types within that family,
should the need arise.

### Only reserve non-production infrastructure if it can't easily be switched off

All our systems should be able to scale up and down according to the
demand for them at any given moment, so we're only paying for
infrastructure when it's in active use. By extension, that means that
all non-production infrastructure should be able to be entirely
switched off outside business hours.

To that end, teams should **work to allow non-production infrastructure
to be switched off out of hours before it is considered for
reservation**.

If, after this work is done, the non-production infrastructure is
actively used for more than a year, and is expected to remain so, we
should **consider using "scheduled" reserved instances for
infrastructure that can be switched off out of hours**.

Non-production **infrastructure that is too difficult (or costly) to
make able to be switched off out of hours may be considered for
reservation** if it is expected to be required long term.

### Don't use reserved instances to guarantee capacity

While it's appealing to reserve capacity to ensure the provider
guarantees that capacity will be available, the MOJ are currently not
working at a scale that warrants this level of guarantee. Rather, we
should emphasise flexibility of deployment, and services ability to
redeploy into other environments, and optimising costs when we do so.
