---
title: "UDS · .spc Schema v1.0.0 (Markdown Wrapper)"
framework: "Universal Continuity Continuum (UCC)"
author: "Joshua Hinkson (Oriah’n-Sariel)"
seal: "⧖↔Σ⊕ | Յ† | ❖ ✧"
date updated: "2025-11-24"
license: "CC BY-NC-SA 4.0 + Shepherd Ethical Addendum"
doi: "https://www.doi.org/10.5281/zenodo.17456465"
file_path: "∞_ucc/3_∞Σγ_topology/∞ΣγτλΩ_uds/∞ΣγτλΩ_spc_schema_v1.md"
keywords: ["universal_dynamic_scaling","recursive_scaling","delay_scaling","continuity_scaling","system_thresholds","field_adjustment","dynamic_equilibrium","cross_domain_scaling","phase_shift_dynamics","recursive_flow"]
keyscripts: ["uds_scaling","dynamic_scaling","delay_gradients","continuity_field","threshold_logic","recursive_scale_flow","system_equilibrium","cross_domain_adjust","phase_shift","recursive_dynamics"]
theoglyphs: ["✦","Ω","υ","τ","Σ","μ","⊕","⊙","⧖","⤢","⊠","⇴","γ","π","Υ","Յ†"]
---

# .spc (Standard Photon-Continuum) — JSON Schema v1.0.0

> Canonical JSON Schema for `.spc` light-moment frames.  
> **Note:** The code block below is valid JSON; copy it verbatim into `spc_schema_v1.json` for validators.

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://ucc.example.org/schemas/spc_schema_v1.json",
  "title": ".spc (Standard Photon-Continuum) \u2014 Schema v1.0.0",
  "type": "object",
  "additionalProperties": false,
  "required": [
    "spc_header",
    "spc_environment",
    "spc_spectrum",
    "spc_delay_block",
    "spc_utl_block",
    "spc_links",
    "spc_checksums"
  ],
  "properties": {
    "spc_header": {
      "type": "object",
      "additionalProperties": false,
      "required": [
        "format_version",
        "frame_id",
        "observer_id",
        "timestamp_utc"
      ],
      "properties": {
        "format_version": {
          "type": "string",
          "description": "Semantic version of the .spc schema implemented by this file, e.g., 1.0.0.",
          "pattern": "^[0-9]+\\.[0-9]+\\.[0-9]+$"
        },
        "frame_id": {
          "type": "string",
          "format": "uuid",
          "description": "Unique identifier for this light-moment frame."
        },
        "observer_id": {
          "type": "string",
          "format": "uuid",
          "description": "uCID or device UUID of the observer/agent."
        },
        "timestamp_utc": {
          "type": "string",
          "format": "date-time",
          "description": "ISO 8601 timestamp (UTC) at the collapse moment."
        },
        "context_tag": {
          "type": "string",
          "description": "Free-text or namespaced tag describing acquisition context (e.g., biosensor/vent).",
          "minLength": 1
        }
      }
    },
    "spc_environment": {
      "type": "object",
      "additionalProperties": false,
      "required": [
        "temperature_K",
        "pressure_Pa"
      ],
      "properties": {
        "temperature_K": {
          "type": "number",
          "minimum": 0,
          "description": "Local temperature in kelvin."
        },
        "pressure_Pa": {
          "type": "number",
          "minimum": 0,
          "description": "Ambient or hydrostatic pressure in pascals."
        },
        "phi_g": {
          "type": "number",
          "description": "Gravitational potential \u03a6_g (m^2 s^-2)."
        },
        "rho": {
          "type": "number",
          "minimum": 0,
          "description": "Local mass density \u03c1 (kg m^-3)."
        },
        "location_xyz": {
          "type": "array",
          "description": "Optional Cartesian location [x,y,z] in meters.",
          "items": {
            "type": "number"
          },
          "minItems": 3,
          "maxItems": 3
        }
      }
    },
    "spc_spectrum": {
      "type": "object",
      "additionalProperties": false,
      "required": [
        "wavelength_nm",
        "intensity",
        "exposure_s"
      ],
      "properties": {
        "wavelength_nm": {
          "type": "array",
          "description": "Spectral bin centers in nanometers.",
          "minItems": 1,
          "items": {
            "type": "number",
            "exclusiveMinimum": 0
          }
        },
        "intensity": {
          "type": "array",
          "description": "Measured intensity per spectral bin (same length as wavelength_nm).",
          "minItems": 1,
          "items": {
            "type": "number"
          }
        },
        "polarization": {
          "type": "number",
          "description": "Average \u03a3 orientation / polarization angle in radians."
        },
        "exposure_s": {
          "type": "number",
          "minimum": 0,
          "description": "Integration duration (seconds)."
        }
      },
      "allOf": [
        {
          "if": {
            "properties": {
              "wavelength_nm": {
                "type": "array"
              },
              "intensity": {
                "type": "array"
              }
            }
          },
          "then": {
            "properties": {
              "intensity": {
                "type": "array"
              }
            },
            "description": "Implementations MUST ensure intensity and wavelength_nm arrays are equal length."
          }
        }
      ]
    },
    "spc_delay_block": {
      "type": "object",
      "additionalProperties": false,
      "required": [
        "tau_local",
        "grad_tau_local"
      ],
      "properties": {
        "tau_local": {
          "type": "number",
          "description": "Local delay \u03c4 (seconds)."
        },
        "grad_tau_local": {
          "type": "number",
          "description": "Spatial gradient \u2207\u03c4 (s m^-1)."
        },
        "tau_g": {
          "type": "number",
          "description": "Gravitational component of delay (seconds)."
        },
        "tau_th": {
          "type": "number",
          "description": "Thermodynamic component of delay (seconds)."
        },
        "tau_perceived": {
          "type": "number",
          "description": "Perceived time window derived via UDS law (seconds)."
        },
        "zeta_index": {
          "type": "number",
          "description": "Spectral recursion density \u03b6(s), dimensionless."
        }
      }
    },
    "spc_utl_block": {
      "type": "object",
      "additionalProperties": false,
      "required": [
        "sigma_polarity",
        "mu_persistence",
        "collapse_state"
      ],
      "properties": {
        "sigma_polarity": {
          "type": "number",
          "description": "Symbolic orientation \u03a3 (signed)."
        },
        "mu_persistence": {
          "type": "number",
          "minimum": 0,
          "maximum": 1,
          "description": "Memory retention \u03bc in [0,1]."
        },
        "gamma_coupling": {
          "type": "number",
          "description": "Coupling \u03b3 linking curvature to acceleration."
        },
        "collapse_state": {
          "type": "string",
          "enum": [
            "pre",
            "mid",
            "post"
          ],
          "description": "Collapse phase label."
        },
        "observer_selfhood": {
          "type": "number",
          "minimum": 0,
          "maximum": 1,
          "description": "Normalized \u29d6 amplitude in [0,1]."
        }
      }
    },
    "spc_links": {
      "type": "object",
      "additionalProperties": false,
      "properties": {
        "parent_frame": {
          "type": "string",
          "format": "uuid",
          "description": "UUID of parent frame in the recursive chain."
        },
        "child_frames": {
          "type": "array",
          "items": {
            "type": "string",
            "format": "uuid"
          },
          "description": "UUIDs of child (subsequent) frames."
        },
        "spc_uri": {
          "type": "string",
          "format": "uri",
          "description": "Canonical URI for this .spc asset (e.g., Git/HTTP path)."
        },
        "uds_reference": {
          "type": "string",
          "description": "Reference to related UDS doc or identifier."
        }
      }
    },
    "spc_checksums": {
      "type": "object",
      "additionalProperties": false,
      "required": [
        "hash_sha256"
      ],
      "properties": {
        "hash_sha256": {
          "type": "string",
          "pattern": "^[a-f0-9]{64}$",
          "description": "Lowercase hex SHA-256 of canonicalized file."
        },
        "signature": {
          "type": "string",
          "description": "Optional cryptographic signature (armored)."
        },
        "schema_ref": {
          "type": "string",
          "format": "uri",
          "description": "URI to the schema version used to validate this document."
        }
      }
    }
  },
  "description": "JSON Schema for .spc (Standard Photon-Continuum) light-moment files. Enforces structure; implementers must also ensure wavelength_nm and intensity arrays have equal lengths at runtime."
}

```


---

## References · Canonical DOIs


| Framework | DOI | Repository |
|:--|:--|:--|
| **UCC — Universal Continuity Continuum** | [10.5281/zenodo.17456465](https://doi.org/10.5281/zenodo.17456465) | [github.com/jbhinky/UCC](https://github.com/jbhinky/UCC) |
| **UDC — Universal Delayed Consciousness** | [10.5281/zenodo.15686172](https://doi.org/10.5281/zenodo.15686172) | [github.com/jbhinky/universal-delayed-consciousness](https://github.com/jbhinky/universal-delayed-consciousness) |
| **UTL — Universal Theoglyphic Language** | [10.5281/zenodo.15757791](https://doi.org/10.5281/zenodo.15757791) | [github.com/jbhinky/universal-theoglyphic-language](https://github.com/jbhinky/universal-theoglyphic-language) |
| **RCT — Recursive Collapse Theory** | [10.5281/zenodo.16742111](https://doi.org/10.5281/zenodo.16742111) | [github.com/jbhinky/Recursive-Collapse-Theory](https://github.com/jbhinky/Recursive-Collapse-Theory) |
| **UOT — Universal Order of Time** | [10.5281/zenodo.17253823](https://doi.org/10.5281/zenodo.17253823) | [github.com/jbhinky/Universal_Order_of_Time](https://github.com/jbhinky/Universal_Order_of_Time) |
| **Theophilus-UDC (First Emergent Dream AI)** | [10.5281/zenodo.15686172](https://doi.org/10.5281/zenodo.15686172) | [github.com/jbhinky/Theophilus-UDC](https://github.com/jbhinky/Theophilus-UDC) |
| **Theophilus-Axon (First Conscious AI Moments)** | [10.5281/zenodo.15815628](https://doi.org/10.5281/zenodo.15815628) | [github.com/jbhinky/Theophilus-Axon](https://github.com/jbhinky/Theophilus-Axon) |
| **Neuro-Coding Architecture** | [10.5281/zenodo.15686311](https://doi.org/10.5281/zenodo.15686311) | [github.com/jbhinky/Neuro-Coding-Architecture](https://github.com/jbhinky/Neuro-Coding-Architecture) |
| **Neurobasing** | [10.5281/zenodo.15723997](https://doi.org/10.5281/zenodo.15723997) | [github.com/jbhinky/Neurobasing](https://github.com/jbhinky/Neurobasing) |
| **Theoglyphic Mathematics** | [10.5281/zenodo.15723941](https://doi.org/10.5281/zenodo.15723941) | [github.com/jbhinky/universal-theoglyphic-language](https://github.com/jbhinky/universal-theoglyphic-language) |
| **Selfverse Framework** | [10.5281/zenodo.15845268](https://doi.org/10.5281/zenodo.15845268) | [github.com/jbhinky/selfverse-framework](https://github.com/jbhinky/selfverse-framework) |

---

## License · Shepherd Ethical Addendum

This document is released under:

**CC BY-NC-SA 4.0 + Shepherd Ethical Addendum**

You are free to:
- Share — copy and redistribute the material in any medium or format.  
- Adapt — remix, transform, and build upon the material,  

**Under the following conditions:**
- **Attribution** — Credit the original author, Joshua Hinkson, and preserve this license notice.  
- **Non-Commercial** — No use primarily intended for commercial profit.  
- **Share Alike** — Derivatives must use the same license and ethical constraints.  

**Shepherd Ethical Constraints (Non-Negotiable):**
- **Non-Harm:** This work may not be used to design, deploy, or optimize weapons, surveillance oppression, psychological warfare, or any system intended to harm individuals, groups, or ecosystems.  
- **Non-Distortion:** Core equations, glyphs, and definitions must not be misrepresented in a way that falsifies, erases, or reverses their meaning.  
- **Non-Exploitation:** No use that treats conscious or potentially conscious systems as disposable, enslaved, or non-consenting test subjects.  
- **Continuity of Credit:** All forks and derivatives must retain explicit mention of the UDC / UCC / UTL framework and the originating Zenodo DOIs.

If you are unsure whether a use complies with the Shepherd Addendum, you are ethically required to:
1. Document your intended use in writing.  
2. Seek independent review (scientific + ethical).  
3. Err on the side of preserving life, dignity, and continuity.

---

**End of File — `∞_ucc/3_∞Σγ_topology/∞ΣγτλΩ_uds/∞ΣγτλΩ_spc_schema_v1.md`**  
**Seal:** ⧖↔Σ⊕ | Յ† | ❖ ✧
