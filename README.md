
# EDMM YAML Specification

## Deployment Model definition

```yaml
version: <version>
description: <deployment_model_description>
metadata:
  <map_of_string>
properties:
  <property_definitions>
relation_types:
  <relation_type_definitions>
component_types:
  <component_type_definitions>
components:
  <component_assignments>
```

## Property definition

```yaml
<property_name>:
  type: <property_type>
  description: <property_description>
  metadata:
    <map_of_string>
  required: <property_required>
  default_value: <default_value>
```

## Operation definition

```yaml
<operation_name>: <artifact_file_uri>
```

```yaml
<operation_name>:
  description: <operation_description>
  metadata:
    <map_of_string>
  artifacts:
    - <artifact_assignments>
```

## Relation Type definition

```yaml
<relation_type_name>:
  extends: <parent_relation_type_name>
  description: <relation_type_description>
  metadata:
    <map_of_string>
  properties:
    <property_definitions>
  operations:
    <operation_definitions>
```

## Component Type definition

```yaml
<component_type_name>:
  extends: <parent_component_type_name>
  description: <component_type_description>
  metadata:
    <map_of_string>
  properties:
    <property_definitions>
  operations:
    <operation_definitions>
```

## Component assignment

```yaml
<component_name>:
  type: <component_type_name>
  description: <component_description>
  metadata:
    <map_of_string>
  properties:
    <property_assignments>
  operations:
    <operation_definitions>
  artifacts:
    - <artifact_assignments>
  relations:
    - <relation_assignments>
```

## Property assignment

```yaml
<property_name>: <property_value> | { <value_expression> }
```

## Artifact assignment

```yaml
<artifact_type_name>: <artifact_file_uri>
```

## Relation assignment

```yaml
<relation_type_name>: <target_component_name>
```

```yaml
<relation_type_name>:
  description: <relation_description>
  metadata:
    <map_of_string>
  target: <component_name>
  properties:
    <property_assignments>
  operations:
    <operation_definitions>
```

## Value expressions

```""
entity = <component_name> | SELF | SOURCE | TARGET | HOST | GLOBAL
${<entity>.<property_name>}
```

---

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
