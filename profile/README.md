# VDA 231‑301 JSON Schema Repository
Consistent and transparent representation of material‑related test requirements in JSON

## Welcome

Welcome to the **VDA 231‑301 JSON Schema Repository**,  
the **official home of the JSON schema recommendation** for the digital exchange of material test results.

This repository provides **recommendations, guidance, and examples** for implementing standards and recommendations using the **JSON Schema** format.  
Its purpose is to ensure a **consistent, transparent, and maintainable structure** for representing material‑related requirements and test results across different use cases.

This repository is maintained as part of a **VDA initiative** to enable an **open and collaborative recommendation** supporting various industry needs.

The work is developed jointly by:
- the **German Association of the Automotive Industry (VDA)** – https://www.vda.de  
- the **Institute for Engineering Design and Industrial Design (IKTD)** at the University of Stuttgart – https://www.iktd.uni-stuttgart.de  
- and numerous contributors from the automotive industry and its supply chain.

---

## Disclaimer

⚠️ **Important notice**

We are constantly working to improve the VDA 231‑301 recommendation.

The **current official version** of the VDA 231‑301 document is published exclusively by the VDA and is available via the **VDA Webshop**  (**German / English**).

The official document contains **additional information** that is **not part of this GitHub repository**.

---

## Language Requirement

English is the preferred language for all content.  
German content may be added where appropriate.

---

## Contents

- How to contribute  
- Disclaimer on standard copyright  
- Main repository  
- Sub‑schemas  
- Versioning  
- Branching  
- Using and generating IDs  

---

## 1. How to Contribute

See the **"How to contribute  section"** (https://github.com/VDA231-301/VDA231-301/tree/main#how-to-contribute) in the main `README.md` file of the repository.

---

## 2. Disclaimer on Standard Copyright

The content and references in this repository are based on standards whose copyrights belong to the respective standardization organizations  
(e.g. **DIN, ISO, VDA**).

⚠️ **Full standard texts must not be reproduced or published without permission.**  
Please ensure that you have the appropriate licenses when working with standard documents.

---

## 3. Main Repository

The main repository of the VDA 231‑301 JSON Schema is available here:

**VDA231‑301**  
https://github.com/VDA231-301/VDA231-301

---

## 4. Sub‑Schemas

### 4.1 General Information

This section describes the **subschema workflow repository** and the **lifecycle of subschemas** from conception to official publication.

#### Phase 1: Draft and Discussion (GitHub Repository)

Each subschema begins its lifecycle as an **independent GitHub repository**.

These repositories:
- serve as publicly accessible working drafts,
- invite discussion and collaborative development,
- collect feedback via GitHub Issues and Discussions.

Subschemas in this phase are **not yet officially versioned**.

#### Phase 2: Official Publication (Schema Repository)

Once a subschema has been reviewed and approved by the responsible **VDA Project Group (PG)**, it enters the official publication phase.

This includes:
- official versioning of the subschema,
- publication in the **central schema repository**,
- availability via a dedicated HTTPS endpoint.

✅ **Only subschemas published in the schema repository are considered officially released and versioned.**

---

### 4.1.1 Officially Released Sub‑Schemas

Currently, the following sub‑schemas are officially released:

- **EN 10204**  
  https://vda231-301.github.io/schemas/EN_10204/VDA_231-301_EN_10204_2004_Certificate_3.1_v0.2.0.schema.json
- **VDA 275**
  https://vda231-301.github.io/schemas/VDA_275/VDA_231-301_VDA_275_2021_Formaldehyde_v1.0.0.schema.json

---

### 4.1.2 Sub‑Schemas Under Review

The following sub‑schemas are currently under review:

- VDA 270  
- VDA 278  
- SEP 1240  

---

### 4.2 Creating New Sub‑Schemas

Guidelines for creating new sub‑schemas are available in:
- [English](https://github.com/VDA231-301/VDA231-301/blob/main/docs/guidelines_for_creating_subschemas_VDA231-301_en.md)
- [German](https://github.com/VDA231-301/VDA231-301/blob/main/docs/guidelines_for_creating_subschemas_VDA231-301_de.md)

---

### 4.3 Level of Detail for Standards

The level of detail in a subschema may vary:

- **Must**  
  Mandatory requirements according to the standard.
- **Can**  
  Optional requirements, often defined by internal factory standards.

The JSON Schema supports **both variants** and enables flexible implementation.

---

## 5. Versioning of Schemas

Each schema must have **clear versioning**.

- Semantic versioning is used (e.g. `v1.0.0`)
- Changes must be documented in a changelog
- Schema changes are made via **pull requests** only

This ensures **consistency, traceability, and transparency**.

---

## 6. Branching

All examples must:
- include the appropriate `if` condition to represent correct logic,
- ensure that `$ref` is present for references.

---

## 7. Using and Generating IDs

IDs must be **unique and stable**.They are generated according to the pattern `<prefix>-<sequential-number>`. 

### Requirements

- Every referable object **MUST** carry an internal data ID in `_id`
- Type: `string`
- Format: **UUID v4** (RFC 4122)
- Representation: lowercase, hyphenated UUID  
  (e.g. `123e4567-e89b-12d3-a456-426655440000`)

### Stability and Uniqueness

- `_id` **MUST** be unique within a test report
- `_id` **MUST NOT** be mutated after assignment

### References

- Reference fields (e.g. `refId`, `instrumentRef`, `sampleRef`)
  **MUST** use the same type and format as `_id`

### Validation

- JSON Schema validates structure and format
- Referential integrity must be ensured via **build / CI checks**

### Reuse

The base schema provides `$defs` for `UuidV4` and `UuidV4Ref`. Subschemas include them via `$ref`.

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



