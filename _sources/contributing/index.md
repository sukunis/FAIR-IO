# How to contribute

In this repository, we collect materials on FAIR-IO. Materials come in various types, from academic journal articles to
blog posts, online videos, teaching resources, slide decks, source code, ... . New material can be contributed
as a markdown file or as a link to external resources. This procedure requires that you have forked this repository
to your own github account. All changes are first applied to your own fork. Later, you then create a pull request (PR)
in **this** repository. We will then review your proposed changes and integrate them into the website.

## What to contribute
- Documentation of creating, uploading, sharing, publishing FAIR-IOs
  - Markdown documents (including converted jupyter notebooks)
  - Academic journal articles and preprints
  - Technical reports and specifications
  - Blog posts
  - Events (workshops, conferences)
  - Educational material 
  - Source code, workflow definitions
  - ...

## Inclusion criteria

TODO

## Exclusion criteria

TODO

## Maintenance of contributions

We reserve the right to remove and modify entries of this collection at any point in time.

## Step-by-step tutorial
1. Clone this repository
1. **Markdown** document
    1. Edit or create new **Markdown** file under `docs/`. Create new section directory if required.
    1. Add path of new **Markdown** document in `docs/_toc.yml`.
1. **YML** document
    1. Edit or create new **YML** entry under `resources/` in one of the existing **YML** files or create a new **YML** file.
    1. Mandatory properties:
      - `name`
      - `url`
      - `type`
      - `license`
    1. Optional properties:
      - `description`
      - `publication_date`
      - `authors`
      - `tags`
    Note that the specific license applied to linked material might enforce the attribution of properties not mentioned here. E.g. the CC-BY
    license mandates the attribution of the original copyright owners, hence `authors` would then be a mandatory field, not just optional.
1. Save all files and commit to your repository
1. Push your changes to your github fork
1. Create a pull request at https://github.com/NFDI4BIOIMAGE/FAIR-IO/compare
   1. Select your fork/branch as **source** and `base:main` as target.
   1. Be as verbose as possible about the details of your proposed changes.
   1. Optional: Propose a reviewer

# At the minimum ...

If the above procedure seems too daunting or time consuming, create a [github issue](https://github.com/NFDI4BIOIMAGE/FAIR-IO/issues) with content or links to the materials you want to include. We can take care of all the details.


