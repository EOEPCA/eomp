# EOEPCA Metadata Profile (EOMP) - workflow extension

Version: 1.0.0

Date: YYYY-MM-DD

## Overview

The EOEPCA Metadata Profile (EOMP) workflow extension is an extension of the EOEPCA Metadata Profile (EOMP).  A workflow defines an application and / or steps that can be executed by an experiment.

## EOMP baseline

An EOMP workflow record conforms to the [EOMP definition](https://github.com/EOEPCA/eomp/tree/master/standard).  All EOMP core rules are applied as a baseline for an EOMP workflow.

## Top level properties

|Property|Requirement|Type|Description|
|---|---|---|---|
|`conformsTo`|**Required**|[string]|The version of EOMP workflow extension (URI) to which the record conforms, fixed to `http://eoepca.org/spec/eomp/1/conf/workflow`|
|`stac_extensions`|Optional|[string]|A list of implemented STAC Extensions. This list must include the STAC application extension (https://stac-extensions.github.io/application/v0.1.0/schema.json)|

## Properties object

|Property|Requirement|Type|Description|
|---|---|---|---|
|`type`|**Required**|string|The resource type of the record.  Fixed to `workflow`

## Link relations

Links to an EOMP - workflow record can be advertised in link objects with a `rel=workflow` link relation.

## Schemas and examples

The authoritative EOMP workflow schema can be found in https://github.com/EOEPCA/eomp/blob/master/schemas/eomp-workflow-bundled.json

## Collaboration and development

The EOMP is developed in the open on [GitHub](https://github.com/EOEPCA/eomp) which contains the schemas, examples and document definition.  In addition, all issues (bugs, feature requests) and contributions can be provided via the GitHub repository.
