# RO-Crate Bioimaging profile (detached)
- follow up on [ro-crate bioimaging minimal design](https://github.com/ome/ome2024-ngff-challenge/blob/42f710bc6b456a0b6e31f431c8283fdd670046b5/dev3/2024-07-02/ro-crate-metadata-proposal.md)
- Version v1.0.0-draft 
- **detached** RO-Crate 
- Authors: Susanne Kunis


## Specification 

![Detached Ro-Crate](ro-crate_detached_v1.0.0.png)

### RO-Crate Metadata Descriptor
```
{
    "@id": "ro-crate-metadata.json",
    "@type": "CreativeWork",
    "conformsTo": {"@id": "https://w3id.org/ro/crate/1.2-DRAFT"},
    "about": {"@id": <url_zarr>}
}
```
### Root Data Entity
- [`Dataset`](https://schema.org/Dataset)
  - `@id`: [`URL`](https://schema.org/URL) (MUST)
  - `@type`: [`Dataset`](https://schema.org/Dataset) (MUST)
  - [`name`](https://schema.org/name): [`Text`](https://schema.org/Text) (SHOULD) <br> [_identify the dataset to humans well enough to disam-
biguate it from other RO-Crates_]
  - [`description`](https://schema.org/description):[`Text`](https://schema.org/Text) (SHOULD) <br> [_further elaborate on the name to provide a sum-
mary of the context in which the dataset is important_]
  - [`license`](https://schema.org/license):[`CreativeWork`](https://schema.org/CreativeWork) or [`URL`](https://schema.org/URL) or [`Text`](https://schema.org/Text)(SHOULD) <br> [_link to a Contextual Entity in the RO-Crate Metadata
File with a name and description.MAY have a URI (eg for Creative Commons or Open Source licenses). MAY, if necessary be a textual description
of how the RO-Crate may be used_]
  - [`acquisition_method`](http://schema.org/measurementTechnique): [`DefinedTerm`](https://schema.org/DefinedTerm) or [`URL`](https://schema.org/URL) (COULD) <br>
[_link to Contextual Entity in the Ro-Crate Metadata File describing the method with name and linked specimen. MAY have a termCode and a inDefinedTermSet (eg if Contextual Entity is of type DefinedTerm)._]
  - [`specimen`](http://purl.obolibrary.org/obo/HSO_0000308):[`BioChemEntity`]() (MUST) <br> [_to specify this Ro-Crate is about this particular subject_]
  - [`hasPart`](http://schema.org/hasPart):[`CreativeWork`](https://schema.org/CreativeWork) or subtype of this (COULD)

### Contextual Entity
- [`acquisition_method`]()
  - `@id`: [`Text`](https://schema.org/Text) or [`URL`](https://schema.org/URL) (MUST) <br>[_MUST be either a URI Path relative to the RO Crate root, or an absolute URI._]
  - `@type`: [`DefinedTerm`](https://schema.org/DefinedTerm) or [`URL`](https://schema.org/URL) (MUST),
  - [`termCode`](https://schema.org/termCode): [`Text`](https://schema.org/Text), (COULD)
  - [`inDefinedTermSet`](https://schema.org/inDefinedTermSet): (http://purl.obolibrary.org/obo/) (COULD)
  - [`name`](https://schema.org/name): [`Text`](https://schema.org/Text) (SHOULD), <br> [_human readable name of linked method_]
 


- [`specimen`](http://purl.obolibrary.org/obo/HSO_0000308)
  - `@id`: [`Text`](https://schema.org/Text) or [`URL`](https://schema.org/URL) (MUST) <br>[_MUST be either a URI Path relative to the RO Crate root, or an absolute URI._]
  - `@type`: [`BioChemEntity`](https://schema.org/BioChemEntity) (MUST)
  - [`additionalType`](https://schema.org/additionalType): [`biosample`](http://purl.obolibrary.org/obo/OBI_0002648)
  - [`name`](https://schema.org/name): [`Text`](https://schema.org/Text) (COULD) <br> [_human readable name of linked term_]
  - [`organism_classification`](https://schema.org/taxonomicRange):[`DefinedTerm`](https://schema.org/DefinedTerm) or [`Taxon`](https://schema.org/Taxon) or [`Text`](https://schema.org/Text) or [`URL`](https://schema.org/URL) (MUST) <br>[_organismus classification via id or via link to Contextual Entity in the Ro-Crate Metadata File describing the organism. MAY have a name to present the human readable name of the term._]

 

## Custom Context and Extended Metadata:
allows to define custom fields within your RO-Crate metadata document and describe how they should be interpreted.

```
"@context": [
    "https://w3id.org/ro/crate/1.2-DRAFT/context",
    {
      "organism_classification": "https://schema.org/taxonomicRange",
      "obo": "http://purl.obolibrary.org/obo/",
      "acquisiton_method": {
        "@reverse": "https://schema.org/result",
        "@type": "@id"
      },
      "biosample": "http://purl.obolibrary.org/obo/OBI_0002648",
      "specimen": "http://purl.obolibrary.org/obo/HSO_0000308"
    }
  ],

```



## Minimal example
see [mic-ro-crate-metadata.json](mic-ro-crate-metadata.json) open in
* [RO-Crate Explorer](https://arunaengine.github.io/ro-crate-explorer/?crate=%7B%0A++%22%40context%22%3A+%5B%0A++++%22https%3A%2F%2Fw3id.org%2Fro%2Fcrate%2F1.1%2Fcontext%22%2C%0A++++%7B%0A++++++%22organism_classification%22%3A+%22https%3A%2F%2Fschema.org%2FtaxonomicRange%22%2C%0A++++++%22obo%22%3A+%22http%3A%2F%2Fpurl.obolibrary.org%2Fobo%2F%22%2C%0A++++++%22acquisiton_method%22%3A+%7B%0A++++++++%22%40reverse%22%3A+%22https%3A%2F%2Fschema.org%2Fresult%22%2C%0A++++++++%22%40type%22%3A+%22%40id%22%0A++++++%7D%2C%0A++++++%22biosample%22%3A+%22http%3A%2F%2Fpurl.obolibrary.org%2Fobo%2FOBI_0002648%22%2C%0A++++++%22specimen%22%3A+%22https%3A%2F%2Fschema.org%2Fabout%22%0A++++%7D%0A++%5D%2C%0A++%22%40graph%22%3A+%5B%0A++++%7B%0A++++++%22%40id%22%3A+%22https%3A%2F%2Fwww.ebi.ac.uk%2Fbiostudies%2Fbioimages%2Fstudies%2FS-BIAD464%22%2C%0A++++++%22%40type%22%3A+%22Dataset%22%2C%0A++++++%22name%22%3A+%22Calcium+wave+dynamics%22%2C%0A++++++%22description%22%3A+%22Time+lapse+image+of+whole+leaves+expressing+calcium+and+glutamate+responses%22%2C%0A++++++%22license%22%3A+%22https%3A%2F%2Fcreativecommons.org%2Flicenses%2Fby%2F4.0%2F%22%2C%0A++++++%22acquisition_method%22%3A+%7B%0A++++++++%22%40id%22%3A+%22%2325173e15-dd40-4287-a35c-c234ba1d366e%22%0A++++++%7D%2C%0A++++++%22specimen%22%3A+%7B%0A++++++++%22%40id%22%3A+%22%2353ce45ab-62a5-4c9d-afbd-bb8fe572e001%22%0A++++++%7D%2C%0A++++++%22hasPart%22%3A+%7B%0A++++++++%22%40id%22%3A+%22https%3A%2F%2Fuk1s3.embassy.ebi.ac.uk%2Febi-ngff-challenge-2024%2Fc0e5d621-62cc-43a6-9dad-2ddab8959d17.zarr%2Fzarr.json%22%0A++++++%7D%0A++++%7D%2C%0A++++%7B%0A++++++%22%40id%22%3A+%22ro-crate-metadata.json%22%2C%0A++++++%22%40type%22%3A+%22CreativeWork%22%2C%0A++++++%22conformsTo%22%3A+%7B%0A++++++++%22%40id%22%3A+%22https%3A%2F%2Fw3id.org%2Fro%2Fcrate%2F1.2-DRAFT%22%0A++++++%7D%2C%0A++++++%22about%22%3A+%7B%0A++++++++%22%40id%22%3A+%22https%3A%2F%2Fwww.ebi.ac.uk%2Fbiostudies%2Fbioimages%2Fstudies%2FS-BIAD464%22%0A++++++%7D%0A++++%7D%2C%0A++++%7B%0A++++++%22%40id%22%3A+%22%2353ce45ab-62a5-4c9d-afbd-bb8fe572e001%22%2C%0A++++++%22%40type%22%3A+%22BioChemEntity%22%2C%0A++++++%22additionalType%22%3A+%22biosample%22%2C%0A++++++%22organism_classification%22%3A+%7B%0A++++++++%22%40id%22%3A+%22NCBI%3Atxid3701%22%0A++++++%7D%0A++++%7D%2C%0A++++%7B%0A++++++%22%40id%22%3A+%22%2325173e15-dd40-4287-a35c-c234ba1d366e%22%2C%0A++++++%22%40type%22%3A+%22obo%3AFBbi_00000251%22%2C%0A++++++%22name%22%3A+%22confocal+microscopy%22%0A++++%7D%0A++%5D%0A%7D)
* [JSON-LD Playground](https://json-ld.org/playground/#startTab=tab-expanded&json-ld=%7B%22%40context%22%3A%5B%22https%3A%2F%2Fw3id.org%2Fro%2Fcrate%2F1.1%2Fcontext%22%2C%7B%22organism_classification%22%3A%22https%3A%2F%2Fschema.org%2FtaxonomicRange%22%2C%22obo%22%3A%22http%3A%2F%2Fpurl.obolibrary.org%2Fobo%2F%22%2C%22acquisiton_method%22%3A%7B%22%40reverse%22%3A%22https%3A%2F%2Fschema.org%2Fresult%22%2C%22%40type%22%3A%22%40id%22%7D%2C%22biosample%22%3A%22http%3A%2F%2Fpurl.obolibrary.org%2Fobo%2FOBI_0002648%22%2C%22specimen%22%3A%22https%3A%2F%2Fschema.org%2Fabout%22%7D%5D%2C%22%40graph%22%3A%5B%7B%22%40id%22%3A%22https%3A%2F%2Fwww.ebi.ac.uk%2Fbiostudies%2Fbioimages%2Fstudies%2FS-BIAD464%22%2C%22%40type%22%3A%22Dataset%22%2C%22name%22%3A%22Calcium%20wave%20dynamics%22%2C%22description%22%3A%22Time%20lapse%20image%20of%20whole%20leaves%20expressing%20calcium%20and%20glutamate%20responses%22%2C%22license%22%3A%22https%3A%2F%2Fcreativecommons.org%2Flicenses%2Fby%2F4.0%2F%22%2C%22acquisition_method%22%3A%7B%22%40id%22%3A%22%2325173e15-dd40-4287-a35c-c234ba1d366e%22%7D%2C%22specimen%22%3A%7B%22%40id%22%3A%22%2353ce45ab-62a5-4c9d-afbd-bb8fe572e001%22%7D%2C%22hasPart%22%3A%7B%22%40id%22%3A%22https%3A%2F%2Fuk1s3.embassy.ebi.ac.uk%2Febi-ngff-challenge-2024%2Fc0e5d621-62cc-43a6-9dad-2ddab8959d17.zarr%2Fzarr.json%22%7D%7D%2C%7B%22%40id%22%3A%22ro-crate-metadata.json%22%2C%22%40type%22%3A%22CreativeWork%22%2C%22conformsTo%22%3A%7B%22%40id%22%3A%22https%3A%2F%2Fw3id.org%2Fro%2Fcrate%2F1.2-DRAFT%22%7D%2C%22about%22%3A%7B%22%40id%22%3A%22https%3A%2F%2Fwww.ebi.ac.uk%2Fbiostudies%2Fbioimages%2Fstudies%2FS-BIAD464%22%7D%7D%2C%7B%22%40id%22%3A%22%2353ce45ab-62a5-4c9d-afbd-bb8fe572e001%22%2C%22%40type%22%3A%22BioChemEntity%22%2C%22additionalType%22%3A%22biosample%22%2C%22organism_classification%22%3A%7B%22%40id%22%3A%22NCBI%3Atxid3701%22%7D%7D%2C%7B%22%40id%22%3A%22%2325173e15-dd40-4287-a35c-c234ba1d366e%22%2C%22%40type%22%3A%22obo%3AFBbi_00000251%22%2C%22name%22%3A%22confocal%20microscopy%22%7D%5D%7D)


