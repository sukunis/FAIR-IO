# Format of content
## Adding new markdown files
Add your **markdown files** to the section folders under `docs` and register the file in `docs/_toc.yml`.

## Adding links to external resources
The **YML** files under `resources/` contain
metadata about contributed material that is already published elsewhere.

Their structure is examplified here:
```
resources
- name: NFDI4BioImage Website
  type:
  - collection
  - website
  url: https://nfdi4bioimage.de 
```

Each entry is attributed by various properties such as
* `name` (mandatory): A descriptive title of the resource
* `url` (mandatory): Resources must be available on the internet using a URL or DOI-URL.
* `type` (mandatory): Content types such as `video`, `collection`, `blog post` etc. Resources can have multiple content types. Collections are lists of links, which could potentially contain more entries.
* `license` (mandatory)
* `description` (optional)
* `publication_date` (optional)
* `authors` (optional)
* `tags` (optional)

This list of meta-data entries is extensible, just let us know using a [github-issue](https://github.com/NFDI4BIOIMAGE/FAIR-IO/issues) which kind of meta data you would like to add here.

After pushing newly added material to your own fork, you can create a pull request to inform us about your suggested additions or modifications to existing material.
