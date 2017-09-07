---
category: Building software
expires: 2018-01-31
---
# Licensing software or code

Everything we produce or use, whether open or closed, should have an
appropriate licence applied (as [indicated by the service
manual][service manual licencing]). Without a licence, others (even
within the MOJ) have no way of knowing for sure if they can use it, or
how.

At the MOJ, we use the [MIT License](https://opensource.org/licenses/MIT).

[service manual licencing]: https://www.gov.uk/service-manual/technology/making-source-code-open-and-reusable#licensing-your-code

## Applying the MIT License to our work

### Each repository should include a licence file

This should be called `LICENCE` or `LICENCE.md`. "License" is the U.S.
English spelling.

GitHub will still show licence details for the British English spelling.

Make sure the licence content is included in full, including the title
"The MIT License", so that readers are quickly able to see what licence
is being used.

### Use the correct copyright notice

The Copyright is Crown Copyright; you can put "Ministry of Justice" in
brackets. For example:

```
Copyright (c) 2017 Crown Copyright (Ministry of Justice)
```

The year should be the year the code was first published. Where the
code is continually updated with significant changes, the year can be
shown as a period from first to most recent update (e.g. 2015-2017).

### Example

`repo-audit` has a good [example of our licence](https://github.com/ministryofjustice/repo-audit/blob/master/LICENSE).
