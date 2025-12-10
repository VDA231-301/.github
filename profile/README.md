# VDA 231-301 JSON Schema Repository
----
# **Consistent and transparent representation of specific material requirements of standards in JSON schema**
----
Welcome to the **VDA 231-301 JSON Schema Repository** the official home for the JSON schema standard for the digital exchange of material test results. This repository provides specifications and examples for implementing standards using the JSON Schema format. Its purpose is to ensure a consistent, transparent, and maintainable structure for representing standard requirements across different use cases.

This repository is maintained as part of the VDA initiative to enable an open, collaborative standard that supports various industry needs.
Developed jointly by the German Association of the Automotive Industry (www.vda.de), as well as the Institute for Engineering Design and Industrial Design (IKTD) at the University of Stuttgart (www.iktd.uni-stuttgart.de) and many contributors from the automotive industry.


**DISCLAIMER**: We are constantly working to improve the VDA 231-301. The current version of the official VDA 231-301 document can be found in the VDA Webshop. ([German](https://webshop.vda.de/VDA/de/vda-231-301-022025) / [English](https://webshop.vda.de/VDA/en/vda-231-301-022025)). It contains additional information about the standard that is not part of this repository.



**Language Requirement**

English is the preferred language for all content, but it is not mandatory. German can be added.

---
# Contents


## Table of Contents
1. How to contribute
2. Disclaimer
3. Main Repository
4. Sub-Schemas
5. Branching 
6. Using and generating IDs

## 1. How to contribute

See the ["How to contribute" section](https://github.com/VDA231-301/VDA231-301/tree/main#how-to-contribute) in the main README.md file.

  
## 2. DISCLAIMER on Standard Copyright: 
The content and references in this repository are based on standards whose copyrights belong to the respective standardization organizations (e.g., DIN, ISO, VDA). Full standard texts must not be reproduced or published without permission. Please ensure you have the appropriate licenses.


## 3. Main Repository
**VDA231-301:** https://github.com/VDA231-301/VDA231-301



## 4. Sub-Schemas

### 4.1 General information
Below you find general information to Subschema Workflow Repository. Additionally it describes the lifecycle of our subschemas from conception to official publication.


**Phase 1: Draft and Discussion (GitHub Repository)**
Each subschema begins its lifecycle as an independent repository on GitHub. These repositories serve as publicly accessible working drafts, inviting discussion and further development. In this phase, the focus is on collaboration and community feedback. Subschemas at this stage are not yet officially versioned. GitHub Issues and Discussions can be used for communication and gathering feedback. 


**Phase 2: Official Publication (Schema Repository)**
Once a subschema is deemed reviewed and ready for publication by the VDA-Product Group (PG), it transitions to the official publication phase. This includes official versioning of the subschema. Subsequently, the subschema is published in our central schema repository, which is accessible via a dedicated HTTPS page. Only subschemas in this repository are considered officially released and versioned.

**Currently, the following sub-schemas are officially released:**

EN 10204
"https://vda231-301.github.io/schemas/EN_10204/VDA_231-301_EN_10204_2004_Certificate_3.1_v0.2.0.schema.json"


**Currently, the following sub-schemas are under review:**

- VDA 270

- VDA 278

- SEP 1240

- VDA 275

### 4.2 Creating new sub-schemas
See the **guidelines  for creating sub-schemas**:
- [English](https://github.com/VDA231-301/VDA231-301/blob/main/docs/guidelines_for_creating_subschemas_VDA231-301_en.md)
- [German](https://github.com/VDA231-301/VDA231-301/blob/main/docs/guidelines_for_creating_subschemas_VDA231-301_de.md)

### 4.3 Level of Detail for Standards
- **Must**: Requirements that are mandatory according to the standard.  
- **Can**: Optional requirements that are possible at any time, often defined by internal factory standards.  
The JSON schema supports both variants and enables flexible implementation.

### 4.4 Versioning of Schemas
Each schema must have clear versioning. Use semantic versioning (e.g., `v1.0.0`) and document changes in the changelog. Changes to schemas should only be made via pull requests to ensure consistency and traceability.


## 5. Branching 
All examples must include the `if` condition to represent correct logic. Also ensure that `$ref` is present for references


## 6. Using and generating IDs

IDs must be unique and stable. They are generated according to the pattern `<prefix>-<sequential-number>`. 
- **Requirement:** Every referable object **MUST** carry an internal data ID in `_id`. Type is `string`, format **UUID v4** (RFC 4122).
- **Representation:** Lowercase, hyphenated UUID (e.g., `123e4567-e89b-12d3-a456-426655440000`).
- **Stability & Uniqueness:** `_id` **MUST** be unique within a test report and **MUST NOT** be mutated after assignment.
- **References:** Reference fields (e.g., `refId`, `instrumentRef`, `sampleRef`) **MUST** use the same type/format as `_id` (UUID v4).
- **Validation:** JSON Schema validates structure/format, not referential integrity. Existence and uniqueness of `_id` **MUST** be enforced via build/CI checks.
- **Reuse:** The base schema provides `$defs` for `UuidV4` and `UuidV4Ref`. Subschemas include them via `$ref`.
  
**Example Base Schema Definition:**
```json
"$defs": {
  "UuidV4": {
    "type": "string",
    "format": "uuid",
    "pattern": "^[0-9a-f]{8}-[0-9a-f]{4}-4[0-9a-f]{3}-[89ab][0-9a-f]{3}-[0-9a-f]{12}$"
  }
}


{
  "_id": "123e4567-e89b-12d3-a456-426655440000",
  "instrumentRef": "987e6543-e21b-43d3-a456-426655440999"
}




