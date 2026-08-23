# State of DMARC: data

The published data behind [State of DMARC](https://domaincanary.com/research/state-of-dmarc),
DomainCanary's monthly measurement of DMARC across the Tranco top million domains.

## Layout

One directory per edition, named by snapshot month:

```
2026-08/
  aggregates.json   every number the edition page prints, as published
  manifest.json     what was scanned: source lists, resolver setup, scan window, totals
```

`aggregates.json` is also served live at
`https://domaincanary.com/research/state-of-dmarc/<edition>/aggregates.json`. The copy here is
the pinned version for that edition and does not change after publication.

## What the numbers are

The scan reads public TXT records for DMARC and SPF across the Tranco top 1 million plus named
cohorts, then sorts each domain into a quality tier: no record, broken, dead (p=none with no
working report destination), monitoring, partial enforcement, or enforced. For external `rua=`
destinations it also checks the report-receiver authorization record, which is what separates a
domain that collects reports from one whose reports are silently dropped. The
[methodology section](https://domaincanary.com/research/state-of-dmarc) of each edition defines
every field.

Domains whose DMARC lookup failed after retries are counted as errors, never as "no DMARC".

## Citing this

Data is licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/): reuse it, including
commercially, with attribution. Suggested citation:

```
DomainCanary. State of DMARC, 2026-08. https://domaincanary.com/research/state-of-dmarc.
Data licensed CC BY 4.0.
```
