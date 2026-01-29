# CLINiQ-SHIFT

**CLINiQ-SHIFT** is an offline, safety-bounded clinical handoff standardization system built using **MedGemma**, an open-weight healthcare-aligned model from Google’s **Health AI Developer Foundations (HAI-DEF)**.

The system transforms unstructured nursing notes into a structured nurse-to-nurse handoff summary while explicitly avoiding diagnoses, treatment recommendations, or clinical predictions.

---

## Problem Context

Clinical handoffs are a major source of information loss in healthcare, particularly in rural and low-resource settings where staff work under time pressure and limited infrastructure. Unstructured documentation during shift changes can lead to missed observations, incomplete task follow-ups, and unclear resource constraints.

CLINiQ-SHIFT addresses this problem by **preserving and standardizing observational information**, rather than performing medical decision-making.

---

## Model Provenance

This project uses the open-weight healthcare-aligned model:

- **Model:** MedGemma 1.5 4B IT  
- **Source:** Hugging Face  
- **Model ID:** `google/medgemma-1.5-4b-it`  
- **Collection:** Google Health AI Developer Foundations (HAI-DEF)  

The model is used **without fine-tuning or re-distribution** to preserve original alignment guarantees and auditability.

---

## System Overview

Unstructured nursing notes  
→ Safety-constrained prompt  
→ **MedGemma (offline, CPU-only)**  
→ Structured handoff summary  
→ Post-generation safety validation

Key design principles:
- Offline execution for privacy and reliability
- Deterministic generation
- Explicit handling of missing information
- System-level safety enforcement

---

## Repository Contents

- **Notebook:** MedGemma-based handoff generation pipeline  
- **Evaluation:** Coverage metrics, safety checks, and stress tests  
- **Safety:** Detection and mitigation of unsafe language  

---

## Requirements

- Python 3.10+
- `torch`
- `transformers`
- `datasets`
- `peft` (optional, not used for fine-tuning)

---

## Intended Use

CLINiQ-SHIFT is designed to support **nurse-to-nurse shift handoffs** in offline or low-resource clinical environments.  
It is not a diagnostic or clinical decision-support system and does not replace professional judgment.

---

## Notes

This project was developed as part of the **MedGemma Impact Challenge** and demonstrates responsible, safety-first use of healthcare-aligned open models.
