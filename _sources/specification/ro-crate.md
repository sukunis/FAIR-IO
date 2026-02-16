# RO-Crate

### What a RO‑Crate actually is

* RO = Research Object – any collection of files that belong together in a research project (data tables, figures, code, PDFs, …).
* Crate = a container (think of a cardboard box).


A **RO-Crate** is a **standardised digital box** that holds all the files plus a small metadata file that tells you what each file is, who created it, when, under which licence, etc.
It can be compared to a ZIP folder + a “data sheet” that explains what each element is, who created it, and under what conditions it may be shared.

An **attached** RO-Crate bundles the actual data together with its metadata, giving you a self‑contained, portable snapshot. 

A **detached** RO-Crate carries only the metadata and points to data that remains stored elsewhere, which keeps the crate lightweight but relies on the external locations staying accessible.
Using RO-Crates makes your work **FAIR**, easier to cite, and ready for journal or archive submission.

### Quick visual example
**Attached crates** keep the data inside the box → fully portable but potentially large.
```
my-attached-crate/
│
├─ data/
│   └─ measurements.csv          # the file is right here
└─ ro-crate-metadata.json       # "@id": "data/measurements.csv"
```

**Detached crates** keep only the labels inside; the data stay outside (usually on a server) → small box, but you rely on the external links staying alive.
```
my-detached-crate/
│
└─ ro-crate-metadata.json       # "@id": "https://datahub.org/measurements.csv"
```
### Key points detached ro-crate

- exists without defined root directory,
- not processed in a file-system context
- referenced data entities are web-based
- naming convention: ${prefix}-ro-crate-metadata.json


