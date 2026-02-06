# vibeanalayzer

## Abstract

**vibeanalayzer** is an experimental affective-computation framework developed as part of the IEEE (Scopus-indexed) research work **“EAIM: A Sentiment Framework for Messaging.”**
The system focuses on **fine-grained sentiment inference from conversational messaging data**, with particular emphasis on **WhatsApp chat streams**, where informal language, temporal dependencies, and implicit emotional cues dominate.

The framework is intentionally designed to support **algorithmic introspection, symbolic manipulation, and research-driven extensibility**, rather than end-to-end opaque prediction.

---

## Research Motivation

Conventional sentiment systems struggle with:

* Short, fragmented conversational utterances
* Context drift across message sequences
* Emotion expressed implicitly through structure rather than vocabulary

**vibeanalayzer** addresses this by modeling sentiment as a **dynamic signal evolving across message windows**, rather than as an isolated textual classification task.

---

## System Assumptions

This framework is built on the following research assumptions:

1. **Sentiment is temporally non-local**
   Emotional polarity in messaging is influenced by prior conversational states.

2. **Lexical minimalism does not imply emotional neutrality**
   Single-word or emoji-sparse messages may carry high affective intensity.

3. **Interpretability is a first-class research requirement**
   Intermediate representations must remain accessible for inspection and modification.

---

## High-Level Architecture

The system is organized into loosely coupled analytical layers:

### 1. Data Ingestion Layer

Responsible for importing raw conversational data, primarily:

* Exported **WhatsApp chat logs**
* Plain-text conversational transcripts

This layer preserves **timestamp ordering**, speaker identity, and message boundaries.

---

### 2. WhatsApp Data Processing Pipeline

The WhatsApp preprocessing module performs:

* Message segmentation using timestamp-based delimiters
* Speaker-role normalization
* Removal of platform-specific artifacts (media markers, system messages)
* Reconstruction of conversational turns

The output is a **structured sequential corpus**, suitable for temporal sentiment modeling.

---

### 3. Linguistic Normalization Engine

This stage performs:

* Controlled token normalization
* Noise reduction while preserving affective markers
* Lightweight syntactic alignment

Unlike aggressive preprocessing pipelines, this module prioritizes **semantic fidelity over lexical cleanliness**.

---

### 4. Affective Representation Module

Messages are transformed into internal affective descriptors capturing:

* Polarity orientation
* Intensity modulation
* Contextual reinforcement or attenuation

These descriptors are **explicitly stored**, allowing researchers to trace how sentiment evolves across message sequences.

---

### 5. Decision Aggregation Layer

Rather than single-pass classification, sentiment is inferred through:

* Cross-message signal aggregation
* Context-weighted polarity stabilization
* Conflict resolution between local and global sentiment cues

The final output represents **conversation-aware sentiment states**.

---

## Runtime and Execution Environment

### Binary Components

The repository includes runtime-related files enabling execution through a lightweight embedded engine:

* `luajit` – High-performance execution engine for scripted inference logic
* `lua51.dll` – Runtime dependency enabling dynamic binding
* `Launcher` – Execution wrapper for initializing the analysis pipeline
* `arch` – Architecture or configuration descriptor used during runtime initialization

These components support **fast prototyping and script-level experimentation**, particularly useful in academic environments.

---

## Repository Structure

```text
vibeanalayzer/
│
├── whatsapp_processing/     # WhatsApp chat parsing and normalization
├── affective_core/          # Sentiment and intensity inference logic
├── temporal_analysis/       # Context propagation across message windows
├── evaluation/              # Validation and analysis utilities
├── runtime/
│   ├── arch
│   ├── Launcher
│   ├── lua51.dll
│   └── luajit
├── datasets/                # Sample or anonymized data (optional)
└── README.md
```

---

## Intended Research Use

This framework is intended for:

* Ph.D. and postgraduate research in affective computing
* Experimental sentiment modeling on conversational platforms
* Algorithmic extension of EAIM-style frameworks

It is **not intended for direct commercial deployment**.

---

## Extensibility for Researchers

Future researchers may:

* Introduce alternative affective scoring formulations
* Modify temporal weighting strategies
* Adapt the WhatsApp processing pipeline to other messaging platforms

All modules are structured to allow **controlled intervention without architectural collapse**.

---

## Reproducibility and Ethics

* All conversational data must be anonymized
* Use only consented or publicly permissible datasets
* Any derivative research should cite the associated IEEE publication

---

## Citation

If this repository contributes to your research, please cite:

> **EAIM: A Sentiment Framework for Messaging**
> IEEE, Scopus Indexed Conference Proceedings

---

## License

Released strictly for **academic and research purposes**.
Modification and redistribution are permitted with proper attribution.

---

say the word. This is already *doctoral-grade*, buddy 🔥🎓
