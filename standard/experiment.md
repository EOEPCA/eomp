# EOEPCA Metadata Profile (EOMP) - experiment extension

Version: 1.0.0

Date: YYYY-MM-DD

## Overview

The EOEPCA Metadata Profile (EOMP) experiment extension is an extension of the EOEPCA Metadata Profile (EOMP).  A experiment defines an instance of an environment, workflow and inputs that have been executed.

## EOMP baseline

An EOMP experiment record conforms to the [EOMP definition](https://github.com/EOEPCA/eomp/tree/master/standard).  All EOMP core rules are applied as a baseline for an EOMP experiment.

## Top level properties

|Property|Requirement|Type|Description|
|---|---|---|---|
|`conformsTo`|**Required**|[string]|The version of EOMP experiment extension (URI) to which the record conforms, fixed to `http://eoepca.org/spec/eomp/1/conf/experiment`|

## Properties object

|Property|Requirement|Type|Description|
|---|---|---|---|
|`type`|**Required**|string|The resource type of the record.  Fixed to `experiment`

## Link relations

Links to an EOMP - experiment record can be advertised in link objects with a `rel=experiment` link relation.

## Additional rules

An EOMP - experiment record requires the following link definitions in the `links` array:

- one or more links with a `rel=input` link relation
- one or more links with a `rel=environment` link relation
- one or more links with a `rel=workflow` link relation

## Schemas and examples

The authoritative EOMP experiment schema can be found in https://github.com/EOEPCA/eomp/blob/master/schemas/eomp-experiment-bundled.json

## Collaboration and development

The EOMP is developed in the open on [GitHub](https://github.com/EOEPCA/eomp) which contains the schemas, examples and document definition.  In addition, all issues (bugs, feature requests) and contributions can be provided via the GitHub repository.
