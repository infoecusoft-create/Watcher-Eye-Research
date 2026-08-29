# Watcher Eye Automotive: An Evidence-Driven AI Framework for ECU Firmware Analysis and Deterministic Binary Modification

### AI-Assisted Firmware Understanding, Binary Analysis, Controlled Modification, Verification, and Evidence-Based Validation

**Author:** Dr. Eng. Sayed Mostafa
**Research and Development Team:** Watcher Eye Development Team
**Document Type:** Research Paper
**Version:** 1.0
**Date:** August 2026

---

# Abstract

Electronic Control Units (ECUs) constitute a fundamental computational layer within modern automotive systems. Their firmware contains executable code, calibration data, configuration structures, diagnostic information, control parameters, and other binary regions whose interpretation and modification require strict control over data integrity.

Traditional firmware modification workflows frequently depend on specialised engineering tools and expert interpretation. Although these tools provide powerful capabilities, the workflow may remain fragmented across identification, comparison, map analysis, modification, checksum processing, validation, and documentation.

This paper presents **Watcher Eye Automotive**, a specialised application of the Watcher Eye evidence-driven AI orchestration framework for ECU firmware analysis and controlled binary modification.

The proposed approach separates probabilistic AI-based semantic understanding from deterministic binary processing. The AI layer interprets the engineer's intent, identifies relevant entities and constraints, evaluates available evidence, and constructs an explicit modification plan. A deterministic binary engine subsequently performs byte-level analysis, comparison, patch generation, and output construction. A verification layer validates the resulting artifact using cryptographic fingerprints, byte-range comparisons, structural checks, checksum procedures where an appropriate algorithm is known, and other task-specific evidence.

The architecture explicitly preserves the original firmware as an immutable reference and produces modified outputs as separate artifacts. Modification plans are bound to source fingerprints to prevent accidental application of an approved operation to a different binary. Preview, backup, conflict detection, rollback, and evidence receipts are incorporated into the workflow.

The paper further proposes an experimental methodology for evaluating firmware identification, difference detection, modification accuracy, preservation of unaffected regions, checksum validation, execution reliability, and evidence integrity.

The objective is not to replace established automotive engineering tools, but to provide an evidence-driven orchestration architecture that can connect AI-based intent interpretation with deterministic firmware analysis and controlled engineering operations.

**Keywords:** ECU, Automotive Firmware, Binary Analysis, Firmware Engineering, Artificial Intelligence, AI Orchestration, Deterministic Modification, Firmware Verification, SHA-256, Calibration Analysis, Evidence-Based AI, Automotive Software.

---

# 1. Introduction

Modern vehicles increasingly depend on distributed electronic control systems. Engine management, transmission control, braking, airbag systems, body control, and other vehicle functions may rely on dedicated electronic control units containing firmware and calibration data.

Engineering work involving ECU firmware therefore requires more than ordinary file manipulation. A binary file may contain executable regions, calibration structures, tables, metadata, checksums, diagnostic information, and manufacturer-specific formats.

A modification that changes an unintended byte range can result in an invalid artifact or unexpected system behaviour.

Consequently, a reliable firmware engineering workflow must answer several questions:

* What ECU or firmware is represented by the file?
* What evidence supports the identification?
* Which regions differ between two firmware versions?
* Which differences correspond to meaningful modifications?
* Which bytes are permitted to change?
* Which bytes must remain unchanged?
* Is the requested modification compatible with the source firmware?
* Has the resulting artifact been structurally validated?
* Has an appropriate checksum procedure been applied?
* Can the entire operation be reproduced?
* Can the original artifact be restored?

Artificial intelligence can assist with several of these questions, particularly natural-language interpretation and semantic reasoning. However, probabilistic language generation should not be responsible for directly performing unrestricted byte-level modification.

Watcher Eye Automotive addresses this separation through an architecture in which:

> **AI interprets and plans; deterministic engines analyse and modify; verification determines whether the result can be trusted.**

---

# 2. Research Problem

The central problem addressed by this paper is the integration of AI-assisted engineering interpretation with deterministic firmware operations without allowing probabilistic model behaviour to become an uncontrolled modification mechanism.

A conventional AI system may interpret a request such as:

> "Apply the modification found in the modified firmware to the corresponding region of the original firmware."

However, successful execution requires substantially more than understanding the sentence.

The system must establish:

1. the identity of the source firmware;
2. the identity of the reference firmware;
3. the relevant changed regions;
4. the correspondence between those regions;
5. the permitted modification scope;
6. potential conflicts;
7. the exact patch;
8. the resulting binary;
9. integrity of unchanged regions;
10. validity of the resulting artifact.

This creates the following research question:

> **Can an AI-orchestrated architecture combine semantic firmware understanding with deterministic binary processing while maintaining reproducibility, integrity, and evidence-based verification?**

---

# 3. Research Objectives

The research objectives are:

### O1 — Firmware Identity

Establish evidence-based identification of firmware artifacts using cryptographic fingerprints, structural signatures, metadata, and explicitly labelled inference.

### O2 — Binary Comparison

Detect and represent differences between firmware versions at byte and region levels.

### O3 — Intent Preservation

Translate natural-language automotive engineering requirements into structured modification contracts.

### O4 — Deterministic Modification

Apply approved modifications using deterministic binary operations rather than probabilistic generation.

### O5 — Integrity Preservation

Guarantee that unintended regions remain unchanged whenever the modification contract requires preservation.

### O6 — Verification

Produce independent evidence demonstrating whether the requested operation was completed correctly.

### O7 — Reproducibility

Bind operations to source fingerprints, modification plans, tool versions, and output fingerprints.

### O8 — Safe Engineering Workflow

Provide preview, backup, conflict detection, rollback, and explicit approval for sensitive modifications.

---

# 4. System Scope

Watcher Eye Automotive focuses on firmware engineering workflows involving binary artifacts.

The architecture covers:

* firmware identification;
* binary inspection;
* hexadecimal analysis;
* entropy analysis;
* structural analysis;
* stock/modified comparison;
* changed-region detection;
* calibration/map analysis when definitions are available;
* deterministic patch generation;
* controlled binary modification;
* checksum processing through known algorithms;
* output verification;
* evidence generation.

The architecture does **not** assume that every ECU family, firmware format, checksum algorithm, calibration definition, or programming interface is universally supported.

Support must be established through evidence and appropriate validation.

---

# 5. Architectural Principle

The core architectural principle is:

> **Probabilistic interpretation must be separated from deterministic transformation.**

The system can therefore be represented as:

**Engineer Request**

↓

**Intent Translation**

↓

**Firmware Context**

↓

**Evidence Analysis**

↓

**Modification Plan**

↓

**Policy / Approval**

↓

**Deterministic Binary Engine**

↓

**Output Artifact**

↓

**Verification**

↓

**Evidence Receipt**

This architecture prevents a language model from directly becoming the authority responsible for arbitrary byte-level modifications.

---

# 6. Firmware Artifact Model

Each firmware artifact should be represented by a structured identity record.

A conceptual record may include:

* filename;
* file size;
* SHA-256;
* binary format;
* ECU identifier when supported by evidence;
* software version;
* hardware identifier;
* calibration identifier;
* source classification;
* acquisition context;
* analysis timestamp.

Identity evidence should be explicitly classified.

### BYTE_EVIDENCE

Direct evidence extracted from the binary itself.

### SIGNATURE_MATCH

Evidence produced by matching a known structural or signature pattern.

### FILENAME_HINT

Information inferred only from the filename.

### INFERENCE

A reasoned interpretation not directly established by binary evidence.

### NOT_FOUND

The requested identity could not be established.

This classification prevents weak evidence from being presented as confirmed firmware identity.

---

# 7. Binary Analysis

Watcher Eye Automotive treats firmware as structured binary data rather than ordinary text.

The Binary Analysis Engine can inspect:

* file size;
* hexadecimal representation;
* entropy;
* headers;
* strings;
* repeated patterns;
* probable executable regions;
* probable data regions;
* alignment;
* known signatures;
* address or offset relationships.

Analysis results are associated with the original file fingerprint.

This is essential because filenames alone cannot safely identify binary content.

---

# 8. Stock–Modified Comparison

A principal workflow is comparison between an original or stock firmware and a modified firmware.

Conceptually:

**Stock Firmware**

*

**Modified Firmware**

↓

**Binary Difference Engine**

↓

**Changed Byte Ranges**

↓

**Region Grouping**

↓

**Candidate Modification Regions**

The system should identify:

* starting offset;
* ending offset;
* original bytes;
* modified bytes;
* number of changed bytes;
* contiguous or fragmented regions;
* surrounding context.

A simple byte-level difference does not automatically establish semantic meaning.

Therefore:

> **A binary difference is evidence of change, not automatically evidence of function.**

Semantic interpretation requires additional evidence such as known maps, definitions, signatures, repeated observations, or engineering context.

---

# 9. Difference Region Representation

A modification region may be represented as:

```text
Region:
    Source Offset
    Length
    Original Bytes
    Replacement Bytes
    Source SHA-256
    Reference SHA-256
    Evidence Class
    Confidence
```

Multiple regions can be grouped into a single modification plan.

The plan should preserve the distinction between:

**Observed Difference**

and

**Approved Modification**

This distinction is essential for preventing accidental transfer of unrelated changes.

---

# 10. AI-Assisted Automotive Intent Translation

Automotive requests frequently contain technical shorthand, aliases, mixed languages, and implicit constraints.

Examples may include:

* ECU names;
* calibration terminology;
* map names;
* modification aliases;
* file-role descriptions;
* original/modified relationships;
* diagnostic terminology.

The Intent Translation Layer converts these requests into structured contracts.

A conceptual modification contract may contain:

```text
Domain
Action
Source File
Reference File
Target Region
Requested Change
Preservation Constraints
Required Evidence
Approval Requirement
Verification Criteria
```

The AI layer may interpret the request, but the deterministic execution layer receives only the validated contract.

---

# 11. Modification Planning

Before modifying a binary, Watcher Eye generates an explicit modification plan.

The plan contains:

* source fingerprint;
* target offsets or structural identifiers;
* original bytes;
* replacement bytes;
* expected number of modifications;
* preservation requirements;
* checksum requirements;
* verification criteria.

The source fingerprint is critical.

If the original file changes after the plan is generated, the system must invalidate the plan rather than applying it to a different artifact.

---

# 12. Preview and Approval

Sensitive firmware modifications should follow:

**Analyse**

↓

**Plan**

↓

**Preview**

↓

**Approval**

↓

**Apply**

↓

**Verify**

The Preview should expose:

* source hash;
* target ranges;
* original values;
* proposed values;
* number of changed bytes;
* preservation constraints;
* expected output;
* checksum requirement.

Approval must be bound to the reviewed source.

A previously approved plan must not silently execute against a different firmware fingerprint.

---

# 13. Deterministic Binary Modification

After approval, the deterministic engine applies the modification.

The operation should:

1. reopen the source artifact;
2. verify its fingerprint;
3. verify expected original bytes;
4. detect conflicts;
5. apply the approved patch;
6. write to a new output artifact;
7. preserve the original;
8. calculate the output fingerprint;
9. initiate verification.

The operation should be atomic where possible.

If any expected byte differs from the planned source state, execution should stop rather than silently overwrite the region.

---

# 14. Conflict Detection

Conflict detection is essential for reproducibility.

Consider an approved modification based on:

```text
Source SHA-256 = H1
Offset = X
Expected bytes = A
Replacement = B
```

If the current source has:

```text
Source SHA-256 = H2
```

the operation must not proceed.

Likewise, if the source fingerprint matches but the expected bytes at offset X do not match the modification contract, the operation should stop.

This prevents accidental application of a patch to an incompatible artifact.

---

# 15. Preservation Verification

One of the strongest verification mechanisms is proving that only authorised regions changed.

If the modification plan contains:

```text
Allowed Region = R
```

the verification system should compare source and output outside R.

The expected condition is:

**Outside R: unchanged**

**Inside R: expected modification**

This produces stronger evidence than merely checking that the output file exists.

---

# 16. Checksum Processing

Firmware integrity may depend on checksums or other integrity mechanisms.

Watcher Eye therefore treats checksum processing as a specialised operation.

The system must not assume that one generic checksum algorithm applies to every ECU family.

Instead:

1. identify the applicable algorithm;
2. validate that the algorithm matches the firmware context;
3. calculate the expected checksum;
4. apply the correction if authorised;
5. verify the resulting checksum;
6. record the exact changed ranges.

The system must never report:

> "Checksum fixed"

without evidence demonstrating the applicable algorithm and resulting verification.

---

# 17. Map and Calibration Analysis

Watcher Eye Automotive may support map analysis when appropriate definitions or sufficient evidence are available.

Potential sources include:

* A2L;
* DAMOS;
* OLS definitions;
* known calibration structures;
* verified project knowledge.

The architecture distinguishes between:

**Map Detection**

and

**Map Modification**

A detected map does not automatically grant permission to modify it.

Likewise, an inferred map location should not be presented as a verified calibration definition without supporting evidence.

---

# 18. ECU Modification Script Model

Reusable modification procedures can be represented as versioned scripts or recipes.

Each script should contain:

* script identifier;
* supported firmware fingerprints or families;
* operation description;
* expected source structure;
* modification ranges;
* verification rules;
* checksum requirements;
* lifecycle state.

Suggested lifecycle states:

### Draft

Under development and not trusted for automated execution.

### Verified

Passed the required tests for its declared scope.

### Quarantined

Previously valid but currently unsuitable because of changed evidence, version, or failed validation.

This prevents a previously successful operation from being treated as universally applicable.

---

# 19. Evidence and Audit

Each modification should produce an evidence receipt.

A conceptual receipt contains:

```text
Task ID
Timestamp
Source SHA-256
Output SHA-256
Operation ID
Target Ranges
Original Bytes
Replacement Bytes
Tool Version
Checksum Result
Verification Result
Approval Reference
Rollback Reference
```

The receipt allows another engineer to reconstruct what happened without relying solely on conversational history.

---

# 20. Backup and Rollback

The original firmware must remain immutable.

The recommended artifact lifecycle is:

```text
Original
   │
   ├── Backup
   │
   └── Modification Plan
            │
            └── Approved Patch
                    │
                    └── Modified Output
```

The original file should never be overwritten as part of the standard workflow.

If verification fails, the modified output can be rejected while the original remains available as the recovery reference.

---

# 21. Safety and Authorization

Watcher Eye Automotive is intended for authorised engineering environments.

Operations involving real vehicle hardware require:

* explicit target identification;
* appropriate authority;
* verified backup;
* validated communication adapter;
* controlled execution;
* recovery capability.

The core architecture does not treat physical ECU programming or vehicle flashing as an implicit consequence of analysing a firmware file.

Hardware operations require a dedicated adapter and an explicit execution contract.

---

# 22. Separation of Analysis and Hardware Execution

A critical architectural boundary is:

**Firmware Analysis**

≠

**ECU Programming**

A binary can be analysed without connecting to a vehicle.

Similarly, a modification plan can be generated without programming physical hardware.

This separation provides an additional safety boundary between:

**Digital Artifact**

and

**Physical System**

Any future hardware programming capability should therefore operate through a controlled adapter with independent verification.

---

# 23. Experimental Methodology

A scientific evaluation should use controlled firmware datasets rather than isolated demonstrations.

The dataset should contain:

* original firmware;
* modified firmware;
* known modification regions;
* ECU metadata where available;
* expected outputs;
* checksum information where known;
* ground-truth modification descriptions.

Each experiment should be reproducible using fixed input hashes and documented tool versions.

---

# 24. Evaluation Metrics

## 24.1 Firmware Identification Accuracy

Measure:

* correct ECU identification;
* correct firmware family;
* correct version classification;
* evidence classification accuracy.

---

## 24.2 Difference Detection Accuracy

Measure:

* changed-region recall;
* changed-region precision;
* byte-level accuracy;
* false-positive regions;
* false-negative regions.

---

## 24.3 Modification Accuracy

Measure:

* correct target selection;
* correct byte replacement;
* unintended modification rate;
* patch conflict detection.

A particularly important metric is:

> **Unintended Byte Modification Rate**

The ideal result for a controlled patch is zero unintended modifications.

---

## 24.4 Preservation Accuracy

Measure the percentage of non-target regions that remain identical between source and output.

For a modification affecting region R:

```text
Preservation Accuracy =
Unchanged Non-Target Bytes /
Total Non-Target Bytes
```

The target for a deterministic modification should be:

```text
100%
```

subject to any explicitly declared integrity correction ranges.

---

## 24.5 Verification Accuracy

Measure:

* valid output accepted;
* invalid output rejected;
* incorrect checksum rejected;
* corrupted output rejected;
* incorrect source rejected.

---

## 24.6 Reproducibility

Repeated execution using identical:

* input fingerprint;
* modification plan;
* tool version;
* configuration

should produce an identical deterministic result whenever the workflow is defined as deterministic.

---

# 25. Experimental Test Classes

### Test Class A — Identity

Provide known firmware artifacts and evaluate identification.

### Test Class B — Comparison

Compare known original/modified pairs.

### Test Class C — Controlled Patch

Apply predefined modifications.

### Test Class D — Preservation

Introduce modifications while verifying that unrelated bytes remain unchanged.

### Test Class E — Conflict

Modify the source after plan creation and verify that the system rejects execution.

### Test Class F — Integrity

Introduce corrupted outputs and evaluate rejection.

### Test Class G — Checksum

Evaluate only firmware families for which the checksum algorithm is independently established.

### Test Class H — Recovery

Force failures during processing and verify preservation of the original artifact.

---

# 26. Security Considerations

Firmware is potentially sensitive intellectual property and may contain proprietary code, calibration data, diagnostic information, or manufacturer-specific structures.

Accordingly:

* original files should remain under controlled access;
* cryptographic hashes should be used for artifact identity;
* sensitive files should not be transmitted to external providers unless explicitly authorised;
* secrets should not be stored in conversational memory;
* temporary artifacts should follow retention policy;
* execution logs should avoid exposing proprietary content unnecessarily;
* external source acquisition should occur in quarantine;
* untrusted binaries should be analysed without execution whenever possible.

---

# 27. Threat Model

The architecture considers several classes of failure and attack.

### T1 — Wrong Firmware

A patch is applied to an incompatible binary.

**Mitigation:** source fingerprint and expected-byte verification.

### T2 — Incorrect Interpretation

The AI misunderstands the requested modification.

**Mitigation:** structured intent, preview, and approval.

### T3 — Unintended Byte Modification

The deterministic engine changes data outside the requested region.

**Mitigation:** preservation comparison.

### T4 — Invalid Checksum

The resulting firmware fails an integrity mechanism.

**Mitigation:** family-specific checksum verification.

### T5 — Stale Knowledge

A previously valid modification recipe is reused against a different firmware version.

**Mitigation:** fingerprint-bound knowledge and revalidation.

### T6 — Fabricated Success

The AI claims a modification succeeded without evidence.

**Mitigation:** evidence-based completion gate.

### T7 — Corrupted Output

The generated file is incomplete or altered unexpectedly.

**Mitigation:** output hash, size, structural validation, and comparison.

---

# 28. Discussion

The proposed architecture demonstrates how AI can be incorporated into firmware engineering without requiring the AI model itself to become a byte-level transformation engine.

This distinction has several advantages.

First, deterministic modification can be independently tested.

Second, the same modification operation can be reproduced without depending on model sampling behaviour.

Third, verification can be performed against explicit acceptance criteria.

Fourth, AI interpretation can evolve independently from the binary-processing engine.

Fifth, the architecture can support multiple AI providers without changing the underlying firmware modification logic.

This separation is particularly important for engineering domains where a small unintended change may have consequences beyond the digital artifact itself.

---

# 29. Limitations

Several limitations must be explicitly recognised.

### 29.1 ECU Diversity

ECUs differ significantly in architecture, memory organisation, file formats, calibration structures, diagnostic mechanisms, and integrity algorithms.

Therefore, no universal firmware interpretation should be assumed.

### 29.2 Definition Availability

Advanced map identification may require A2L, DAMOS, OLS, or equivalent definitions.

Without such evidence, map identification may remain probabilistic or incomplete.

### 29.3 Checksum Diversity

Checksum algorithms vary across firmware families and regions.

A checksum procedure must therefore be validated per applicable family or firmware context.

### 29.4 Hardware Programming

Physical ECU programming requires specialised communication hardware and controlled procedures outside the binary-analysis core.

### 29.5 Experimental Validation

The architecture described here requires larger benchmark datasets and systematic experiments before broad quantitative claims can be made.

---

# 30. Research Contributions

The principal contributions of Watcher Eye Automotive are:

1. **An AI-assisted ECU firmware orchestration architecture** that separates semantic interpretation from deterministic binary processing.

2. **An evidence-labelled firmware identity model** distinguishing direct binary evidence from inference and filename-based hints.

3. **A fingerprint-bound modification workflow** preventing approved operations from being silently applied to changed or incompatible firmware.

4. **A deterministic patch architecture** based on explicit byte-level modification plans.

5. **A preservation verification mechanism** designed to establish that non-target regions remain unchanged.

6. **A controlled checksum architecture** that rejects universal or unsupported checksum assumptions.

7. **A versioned firmware modification knowledge model** supporting Draft, Verified, and Quarantined procedures.

8. **An evidence-receipt model** enabling reproducibility and post-operation audit.

9. **A quantitative evaluation methodology** for measuring identification, comparison, modification, preservation, verification, and reproducibility.

---

# 31. Future Research

Future work will investigate:

* automated ECU family classification;
* improved firmware structural fingerprinting;
* semantic map identification;
* automated calibration-region correlation;
* advanced binary similarity analysis;
* architecture-aware firmware analysis;
* controlled CAN/UDS integration;
* hardware-in-the-loop testing;
* automated checksum algorithm discovery under strict validation;
* large-scale ECU benchmark datasets;
* firmware modification reproducibility studies;
* formal verification of modification contracts.

Future hardware integration should remain separated from the core binary engine through controlled adapters and explicit authorisation policies.

---

# 32. Conclusion

This paper presented Watcher Eye Automotive as an evidence-driven architecture for AI-assisted ECU firmware analysis and deterministic binary modification.

The central proposition is that artificial intelligence should provide semantic understanding, contextual interpretation, evidence assessment, and modification planning, while deterministic engineering components perform byte-level operations and independent verification.

The resulting workflow is:

**Intent**

→ **Evidence**

→ **Analysis**

→ **Modification Plan**

→ **Approval**

→ **Deterministic Transformation**

→ **Verification**

→ **Evidence Receipt**

This architecture provides a controlled bridge between natural-language engineering requirements and binary firmware operations.

Its most important property is the explicit separation between what the AI **interprets** and what the deterministic system **executes and proves**.

The framework therefore adopts four fundamental principles:

> **No firmware modification without an explicit plan.**

> **No modification without source integrity verification.**

> **No successful result without independent evidence.**

> **No hardware operation without explicit authority and controlled execution.**

Watcher Eye Automotive is consequently positioned not as a replacement for established automotive engineering environments, but as an orchestration and verification layer capable of integrating AI-assisted understanding with deterministic firmware engineering workflows.

The proposed methodology provides a foundation for subsequent experimental research into ECU identification, binary similarity, calibration analysis, controlled modification, integrity verification, and safe integration with automotive diagnostic environments.

---

# Appendix A — ECU Firmware Evidence Model

| Evidence Type   | Meaning                                       | Reliability       |
| --------------- | --------------------------------------------- | ----------------- |
| BYTE_EVIDENCE   | Direct evidence extracted from binary content | High              |
| SIGNATURE_MATCH | Match against validated structure/signature   | High              |
| FILENAME_HINT   | Information inferred from filename            | Low               |
| INFERENCE       | Analytical interpretation                     | Context-dependent |
| NOT_FOUND       | Evidence unavailable                          | Not established   |

---

# Appendix B — Modification Lifecycle

```text
Firmware Input
      ↓
Fingerprint
      ↓
Identity Analysis
      ↓
Binary Analysis
      ↓
Comparison / Map Analysis
      ↓
Intent Translation
      ↓
Modification Plan
      ↓
Conflict Detection
      ↓
Preview
      ↓
Approval
      ↓
Backup
      ↓
Deterministic Modification
      ↓
Checksum / Integrity Processing
      ↓
Preservation Verification
      ↓
Output Fingerprint
      ↓
Evidence Receipt
      ↓
Validated Artifact
```

---

# Appendix C — Minimum Modification Receipt

A verified modification receipt should contain:

* Task ID
* Source SHA-256
* Output SHA-256
* Source size
* Output size
* Target regions
* Original bytes
* Replacement bytes
* Modification identifier
* Tool version
* Checksum algorithm, when applicable
* Checksum result
* Preservation result
* Verification result
* Timestamp
* Approval reference
* Backup reference

---

# Appendix D — Relationship to the Watcher Eye Research Series

This paper represents the automotive-domain application of the general architecture established in:

**Paper I — Watcher Eye: An Evidence-Driven AI Orchestration Framework for Safe Multi-Domain Engineering and Autonomous Operations**

The automotive research line may subsequently be extended through specialised studies addressing:

1. ECU firmware identification;
2. binary similarity and changed-region detection;
3. calibration/map intelligence;
4. deterministic modification and preservation;
5. checksum verification;
6. controlled CAN/UDS integration;
7. hardware-in-the-loop validation.

The present work therefore establishes the architectural foundation for those future experiments without treating unvalidated future capabilities as established results.
