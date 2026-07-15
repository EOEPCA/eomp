# EOEPCA Metadata Profile (EOMP) Key Performance Indicators (KPI)

Version: 1.0.0

Date: YYYY-MM-DD

## Overview

This document is intended to define Key Performance Indicators (KPIs) in support of the EOEPCA Metadata Profile (EOMP). KPIs provide measurable and valuable quality assessment rules beyond the rulesets put forth by EOMP.

## How to use

The KPIs in this document are designed to help metadata providers curate EOMP and for catalogues to measure the quality of metadata from data providers.

To improve quality:

- providers should use the KPIs to build into their metadata generation
- catalogues should use the KPIs to quality assess EOMP and provide subsequent feedback to providers

## Scoring

Each KPI assesses a number of criteria associated with metadata quality, resulting in a raw score, as well as a percentage. This approach supports weighted rubric scoring.

## Key Performance Indicators

### Good quality title

#### EOMP properties

* `properties.title`

#### Rationale for measurement

A title is the first element of metadata information displayed and helps with initial identification. Meaningful and relevant information makes it easier for users to understand the resource.

The resource title and description are the two most relevant elements in the EOMP record. These two elements are presented to the users in search results and on the dataset description page. They should highlight the resource's key characteristics to assist users in evaluating search results.

#### Measurement

The length is not too short or too long, contains fewer than three acronyms and is represented in sentence case. Spelling and grammar are correct.

#### Guidance

The title should be as specific as possible. For example, if the resource contains only one parameter, this can be stated in the title; however, if the resource contains numerous parameters, a more general term should be used in the title, and the parameters should be stated elsewhere in the metadata record (description, themes, keywords, etc.).

#### Rules

|Rule|Score|
|---|---|
|The title has 3 words or more|1|
|The title has less than 150 characters|1|
|The title has only printable characters (numbers and letters) and round brackets|1|
|The words in title are represented in "Sentence case"|1|
|The title contains fewer than 3 acronyms (words with all uppercase letters)|1|
|The title passes a basic spellcheck|1|
|===

*Total possible score: 6 (100%)*

### Good quality description

#### EOMP properties

* `properties.description`

#### Rationale for measurement

The description facilitates understanding and discovery and is a key element of metadata information displayed in search results. Extensive and meaningful descriptive information enables users to both understand and properly evaluate a metadata record and its respective resource in support of data access, visualization and exploitation.

A EOMP resource's title and description are the two most relevant elements in the record.

#### Measurement

The description should neither be too short nor too long and should not contain HTML markup. Spelling and grammar are correct. Bulletin templates should not be used to populate the description.

#### Guidance

The description should provide a clear and concise statement that enables the reader to understand the content of the resource.

##### Spell-checking recommendations

* Dictionary by Merriam-Webster: America's most-trusted online dictionaryfootnote:[https://www.merriam-webster.com]
* Cambridge Dictionary | English Dictionary, Translations & Thesaurusfootnote:[https://dictionary.cambridge.org]

#### Rules

|Rule|Score|
|---|---|
|The description has between 16 and 2048 characters|1|
|The description does not contain markup (HTML)|1|
|The description passes a basic spellcheck|1|

*Total possible score: 3 (100%)*

### Graphic overview

#### EOMP properties

* `$.links[?(@.rel=="preview")]`

#### Rationale for measurement

A graphic overview of a resource provides the user with a high-level preview, which can assist with the initial assessment or evaluation as part of search results presentation.

#### Measurement

The presence of a `preview` link is checked to ensure that it contains a URL to a common web image file type.footnote:[https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types#Common_image_file_types]

#### Guidance

In addition to the presence of the graphic overview image it is also valuable to provide consistent image dimensions (e.g. 800x800 pixels) so that all images are normalized and scaling and alignment of overview images can be applied consistently by web applications rendering search results.

#### Rules

|Rule|Score|
|A graphic overview element is present|1|
|A graphic overview URL resolves successfully|1|
|A graphic overview URL content is a common web image file type (check MIME type, content header/magic number)|1|

*Total possible score: (present link + resolves + image file type) / (total graphic overviews * 3) (100%)*

### Links health

#### WCMP properties

All properties with linked information (URLs).

* `links[*].href`
* `+properties.themes[*].concepts[*].url+`
* `properties.themes[*].scheme`
* `+properties.contacts[*].links[*].href+`

#### Rationale for measurement

Broken links damage the user experience and give users the impression that a website is not maintained (88% of online consumers are less likely to return to a site after a bad experience). In addition, numerous broken links can affect the reputation and rank of your website when indexed by mass-market search engines.

HTTPS is increasingly becoming a requirement for numerous agencies as the suggested protocol instead of HTTP. Non-HTTPS links in an EOMP document often lead to mixed content errors in web applications deployed via HTTPS and using AJAX/XHR design patterns. HTTPS supports secure, authoritative and trustworthy links.

#### Measurement

The number of broken links in each individual record.  Broken links include links that, when accessed, result in a 4xx or 5xx HTTP error (see [HTTP status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status)).

Also being measured is the use of HTTPS (with a valid SSL certificate) as the link protocol throughout EOMP metadata.

#### Guidance

Ensure that all links resolve and are accessible via HTTPS.

#### Rules

|Rule|Score|
|Link resolves successfully|1|
|Link has a valid media type|1|

*Total possible score: (link resolves) / (total links * 1) (100%)*
