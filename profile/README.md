# VDA 231‑301 – Digital Material Data Exchange

**VDA 231‑301 provides a modular and standardized data model that enables reliable, machine‑readable exchange of material data between OEMs, suppliers, laboratories and IT systems, and is applicable beyond the automotive industry.**

### Quick Navigation

- [About VDA 231‑301](#about-vda-231-301)
- [Modular Architecture](#-modular-concept-of-vda231301)
- [Generic Schema](#-repository-overview)
- [Subschema Structure](#-repository-overview)
- [Governance & VDA Context](#-governance--contribution)
- [Contribution & Collaboration](#contribution--collaboration)

---

## 🌐 About VDA 231‑301

**VDA 231‑301** defines an **open, standardized, and vendor-neutral data model** for the digital management of material, substance, and test data. Originally developed to streamline **material sampling and approval processes in the automotive industry**, it has evolved into a **flexible schema for the digitalization of materials information** — easily adaptable to diverse use cases through sub-schemas.

It is developed and maintained within the **VDA Project Group  
“Digitales Werkstoff‑Datenmanagement im Bemusterungsprozess”**.
(https://www.vda.de)

The recommendation VDA 231‑301 benefits from scientific collaboration with  
the **Institute for Engineering Design and Industrial Design (IKTD)**  at the **University of Stuttgart**  
(https://www.iktd.uni-stuttgart.de).

## 🔄 Data Exchange & Interoperability

VDA 231‑301 enables **consistent, machine‑readable and traceable data exchange**  
across OEMs, suppliers, laboratories and IT systems - **regardless of organizational boundaries**.

Designed to support automation and seamless integration into heterogeneous IT landscapes, the data model is based on a **structured, JSON‑based format**.  

This approach ensures:

- ✅ **Standardized validation** of material data
- ✅ **Efficient processing** across systems
- ✅ **Reliable reuse** of data throughout **the automotive value chain and beyond**


---

## 🎯 Why VDA 231‑301?

VDA 231‑301 supports the digital transformation of material sampling and other material relevant data by:

- ✅ replacing heterogeneous documents with structured data
- ✅ enabling automation and system interoperability
- ✅ improving data quality, traceability and reuse
- ✅ aligning quality, regulatory and sustainability requirements
- ✅ providing an open, vendor‑neutral standard

---

## 👥 Who is this for?

This repository ecosystem is relevant for:

- OEMs and suppliers  
- Laboratories and testing service providers  
- Software vendors and IT platform providers  
- Standardization and regulatory stakeholders  
- Non‑automotive industries with comparable processes  

No prior knowledge of VDA standards is required to get started.

---

## 🚀 Getting Started

If you are new to VDA 231‑301, follow these steps:

1. Read this page to understand scope and structure  
2. Select the relevant subschema repository  
3. Explore data models and examples  
4. Integrate the recommendation or contribute to its development  

---

## 🧱 Modular Concept of VDA 231‑301

VDA 231‑301 follows a **modular architecture**:

- a **generic core schema** providing reusable structures  
- multiple **domain‑specific subschemas** for material, substance, test and requirement data  

This ensures:

- long‑term stability for IT integrations  
- clear separation of concerns  
- flexible extension for future requirements  

<p align="center">
  <img src="https://raw.githubusercontent.com/VDA231-301/VDA231-301/main/docs/images/vda231-301-modular-concept.svg"
       width="700"
       alt="Modular concept of VDA 231-301: generic core and domain-specific subschemas"/>
</p>

<p align="center"><em>
VDA 231‑301 follows a modular architecture with a stable generic core and domain‑specific subschemas.
</em></p>



---

## 🧩 Repository Overview

VDA 231‑301 is organized into **modular subschema repositories**.  
Each subschema covers a dedicated functional or regulatory domain.

| Subschema Repository | Focus (EN) | Fokus (DE) |
|---------------------|-----------|-----------|
| **VDA 231‑300 – Generic**  
https://github.com/VDA231-301/VDA231-300 | material and surface definition in 3D-models in jt | Material- und Oberflächendefinition in 3D-Modellen im jt |
| **VDA 231‑301 – Generic**  
https://github.com/VDA231-301/VDA231-301 | Generic core definitions and reusable model elements | Generische Basismodelle und wiederverwendbare Strukturen |
| **Substance Declaration**  
https://github.com/VDA231-301/Substance-Declaration | Structured substance and material composition data | Strukturierte Stoff‑ und Materialzusammensetzungen |
| **VDA 275 – Formaldehyde**  
https://github.com/VDA231-301/VDA275 | Formaldehyde emission test data | Formaldehyd‑Emissionsprüfungen |
| **VDA 278 – VOC / Fogging**  
https://github.com/VDA231-301/VDA278 | VOC and fogging emission test data | VOC‑ und Fogging‑Emissionsdaten |
| **VDA 270 – Odor**  
https://github.com/VDA231-301/VDA270 | Odor assessment based on panel testing | Geruchsprüfungen mit Panelbewertung |
| **SEP 1240**  
https://github.com/VDA231-301/SEP1240 | Odor‑relevant material requirements | Geruchsrelevante Werkstoffanforderungen |
| **EN 10204**  
https://github.com/VDA231-301/EN10204 | Digital inspection and acceptance certificates | Digitale Prüf‑ und Abnahmezeugnisse |

👉 Detailed data models, figures and examples are provided **within each subschema repository**.



---

## 🤝 Governance & Contribution

VDA 231‑301 is developed collaboratively within VDA structures.

- Technical collaboration takes place via GitHub  
- Contributions are discussed in the VDA project group  
- All repositories follow common rules for  
  - contributions  
  - code of conduct  
  - security  
  - licensing  

Please see the respective  
`CONTRIBUTING.md`, `CODE_OF_CONDUCT.md` and `SECURITY.md` files.

---

## 🔒 Stability & Versioning

Released versions of subschemas are **immutable**.

If software depends on a specific subschema version,  
that exact version will remain accessible at the same location.

This provides **planning security for long‑term system integrations**.

---

## 📨 Contact & Support

There is no individual support email.

Support and discussions are provided via:
- GitHub Issues
- the VDA Project Group meetings and collaboration formats

---

*VDA 231‑301 – enabling trusted, digital material data exchange.*
