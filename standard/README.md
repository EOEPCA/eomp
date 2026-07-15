# EOEPCA Metadata Profile (EOMP)

Version: 1.0.0

Date: YYYY-MM-DD

## Overview

The EOEPCA Metadata Profile (EOMP) is an extension of the [OGC API - Records](https://ogcapi.org/records) standard.  An EOMP is a metadata **record** that can describe **any** resource in the EOEPCA ecosystem.  EOMP records facilitate discovery and search in the [Resource and Data Catalogue](https://eoepca.readthedocs.io/projects/resource-discovery/en/latest/design/resource-and-data-catalogue/design/) as part of the [Resource Discovery](https://eoepca.readthedocs.io/projects/resource-discovery/en/latest/) Building Block.  EOMP records are encoded as [GeoJSON](https://geojson.org).

The EOMP is defined using [JSON Schema](https://json-schema.org).

## OGC API - Records baseline

An EOMP record conforms to the Requirements Class "Record Core (Common Component)" of [OGC API - Records - Part 1: Core](https://docs.ogc.org/is/20-004r1/20-004r1.html#clause-record-core).  All Requirements, Recommendations and Permissions in Record Core are applied as a baseline in EOMP.

## Top level properties

|Property|Requirement|Type|Description|
|---|---|---|---|
|`id`|**Required**|string|A unique identifier for the record.  This value MAY be a UUID.|
|`conformsTo`|**Required**|[array]|The version of EOMP (URI) to which the record conforms, fixed to `http://eoepca.org/spec/eomp/1/conf/core`|
|`stac_extensions`|Optional|[array]|A list of implemented STAC Extensions. The list consists of URLs to JSON Schema files that can be used for validation|
|`geometry`|**Required**|GeoJSON geometry object or `null`|GeoJSON geometry of the record, or `null` if it cannot be derived/calculated, or chosen not to be provided|
|`properties`|**Required**|[Properties object](#properties-object)|Attributes of the record|
|`links`|**Required**|[Link object](#link-object)|Online linkages in support of data retrieval or additional informational resources|

## Properties object

|Property|Requirement|Type|Description|
|---|---|---|---|
|`title`|**Required**|string|A human-readable name of the resource
|`created`|**Required**|string|The date that the EOMP record was created

## Links object

## Schemas and examples

The authoritative EOMP schema can be found in https://github.com/EOEPCA/eomp/blob/master/schemas/eomp-bundled.json

## Collaboration and development

The EOMP is developed in the open on [GitHub](https://github.com/EOEPCA/eomp) which contains the schemas, examples and document definition.  In addition, all issues (bugs, feature requests) and contributions can be provided via the GitHub repository.
