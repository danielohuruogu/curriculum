# Gitbook Setup

Notes for cohort 3 will be published on a [GitBook](https://bnta.gitbook.io/cohort3-course-notes/v/main/) as we go through the course. The GitBook will sync with the `main` branch of this repository, meaning new content can be pushed here as normal. 

## Formatting

The GitBook will format markdown in the same way as GitHub, meaning things like code blocks can be included and will display correctly. The page title is defined when you update the summary document (see below). We can add an additional description of the content which will appear as a sub-heading at the top of the page by including this at the top of any markdown files:

```
---
description: short description of your content here
---

<!-- Content follows -->
```

This will enable us to provide a short summary of each lesson's content at the top of the page.

## Publishing

The structure of the GitBook is defined in [SUMMARY.md](/SUMMARY.md). Only links defined here will be published, so after delivering a lesson update the file to add the path to the markdown file.

The `H2`s define section headings with the bullets underneath linking to documents. We can add sub-sections if necessary. Update the file as shown below to add a new link:

```
# Table of contents

* [BNTA Course Notes](README.md)

## Welcome to BNTA

* [Virtual Machine Setup](virtual-machine-setup/README.md)

<!-- Add new content like this: -->
## New Section Heading

* [Title of New Page](path/to/page/filename.md)
* [Another Page](filepath/name.md)
```

There is no need for the repo's file structure to reflect `SUMMARY.md`, although it would make things much easier for us to keep track of the material.

**DO NOT REMOVE, RENAME OR MODIFY THE README!** [README.md](/README.md) is the document which is displayed as the front page of the GitBook. If we need to add more content to display to the students we can, but do not use it as a reference for the repo.

## TODO

Further details will follow on uploading slides and linking to code examples, still need to test.