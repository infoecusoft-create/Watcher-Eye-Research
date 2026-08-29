# Watcher Eye Software Factory: An Evidence-Driven AI Framework for Multi-File Software Engineering, Automated Testing, and Verified Code Generation

### Architecture, Project Understanding, Controlled Implementation, Testing, Repair, Packaging, and Evidence-Based Software Validation

**Author:** Dr. Eng. Sayed Mostafa
**Research and Development Team:** Watcher Eye Development Team
**Document Type:** Research Paper
**Version:** 1.0
**Date:** August 2026

---

# Abstract

The increasing capabilities of artificial intelligence have created new approaches to software development in which natural-language requirements can be translated into source code, project structures, tests, documentation, and implementation plans. However, generating source code is fundamentally different from engineering, validating, and delivering a complete software system.

A reliable AI-assisted software engineering system must understand an existing project, preserve architectural constraints, manage dependencies, modify multiple files consistently, execute tests, analyse failures, repair defects, and provide evidence that the resulting software actually satisfies its acceptance criteria.

This paper presents **Watcher Eye Software Factory**, an evidence-driven software engineering framework developed as a specialised application of the Watcher Eye orchestration architecture. The framework separates natural-language understanding and engineering planning from deterministic workspace operations, testing, packaging, and verification.

The proposed system introduces a structured Project Workspace, project-scoped knowledge, architecture and dependency analysis, multi-file change planning, controlled code generation, static validation, bounded testing and repair loops, snapshots, rollback, packaging checkpoints, and evidence-based release gates.

A central principle of the framework is that generated source code is not considered a completed software deliverable merely because it is syntactically valid or appears plausible. Completion requires objective evidence including successful tests, build results, artifact integrity, acceptance criteria, and reproducible project state.

The framework further addresses safe acquisition of external source material, dependency isolation, secret protection, package-script risks, and separation between project knowledge and execution authority.

This paper presents the architecture, engineering lifecycle, verification model, safety controls, experimental methodology, evaluation metrics, and limitations of Watcher Eye Software Factory.

**Keywords:** Artificial Intelligence, Software Engineering, AI-Assisted Programming, Code Generation, Software Factory, Automated Testing, Program Repair, Software Verification, AI Orchestration, Project Intelligence, Reproducibility.

---

# 1. Introduction

Software engineering traditionally requires the coordination of requirements analysis, architecture, implementation, testing, debugging, dependency management, packaging, deployment, and maintenance.

Recent advances in artificial intelligence have significantly improved the ability of machines to generate source code from natural-language requirements. Nevertheless, producing a code fragment is substantially different from producing a reliable software system.

A multi-file software project contains relationships between:

* source files;
* modules;
* functions;
* classes;
* configuration;
* dependencies;
* build systems;
* tests;
* runtime environments;
* external services.

A change to one component may affect multiple other components.

Consequently, an AI-assisted software engineering system must reason about the project as a system rather than treating each generated file as an independent response.

Watcher Eye Software Factory addresses this problem through an evidence-driven engineering workflow.

The central principle is:

> **Code generation is an implementation activity, not proof of software correctness.**

---

# 2. Research Problem

The primary research problem is:

> **How can an AI-driven system transform natural-language software requirements into controlled multi-file implementations while providing objective evidence that the resulting project satisfies its defined acceptance criteria?**

Several challenges arise.

### 2.1 Requirement Ambiguity

Natural-language requirements may contain incomplete or conflicting specifications.

### 2.2 Project Complexity

Large projects contain dependencies and relationships that cannot be safely understood from isolated files.

### 2.3 Code Correctness

Syntactically valid code may still contain logical or architectural defects.

### 2.4 Dependency Risk

External packages and repositories may introduce security, licensing, or compatibility problems.

### 2.5 Verification

A generated project must be tested rather than merely described as complete.

### 2.6 Recovery

Failed modifications must be reversible without destroying a previously valid project state.

These requirements motivate the Software Factory architecture.

---

# 3. Research Objectives

The proposed research objectives are:

### O1 — Requirement Understanding

Convert natural-language software requirements into structured engineering specifications.

### O2 — Project Understanding

Analyse existing projects before modifying them.

### O3 — Multi-File Consistency

Coordinate changes across multiple files while maintaining dependency relationships.

### O4 — Controlled Code Generation

Generate code within explicit architectural and security constraints.

### O5 — Automated Verification

Execute appropriate static and dynamic tests.

### O6 — Bounded Repair

Automatically repair detected defects within a controlled repair budget.

### O7 — Reproducibility

Associate project states with hashes, snapshots, dependency information, tool versions, and test receipts.

### O8 — Safe Delivery

Prevent unverified source or build artifacts from being presented as completed deliverables.

---

# 4. Software Factory Architecture

The proposed workflow is:

**Requirement**

↓

**Intent Translation**

↓

**Project Discovery**

↓

**Architecture Analysis**

↓

**Implementation Plan**

↓

**Workspace Snapshot**

↓

**Multi-File Implementation**

↓

**Static Validation**

↓

**Testing**

↓

**Failure Analysis**

↓

**Bounded Repair**

↓

**Regression Testing**

↓

**Packaging**

↓

**Release Verification**

↓

**Evidence Receipt**

---

# 5. Project Workspace

Watcher Eye creates an isolated Project Workspace for each engineering task.

The workspace provides:

* controlled project paths;
* file-count limits;
* file-size limits;
* project fingerprinting;
* snapshots;
* change tracking;
* dependency isolation;
* build checkpoints;
* test receipts.

The workspace prevents accidental modification of unrelated user files.

Path validation must prevent:

* directory traversal;
* unintended absolute-path access;
* symbolic-link escape;
* unsafe archive extraction.

---

# 6. Existing Project Analysis

Before modifying an existing project, the system should operate in read-first mode.

The analysis stage identifies:

* project type;
* entry points;
* source files;
* modules;
* functions;
* classes;
* configuration;
* dependencies;
* tests;
* build system;
* deployment files;
* documentation;
* potential risks.

The resulting project model provides the foundation for subsequent implementation.

The system should not modify a project simply because the user requested a change without first determining the relevant project context.

---

# 7. Code Intelligence

Watcher Eye Software Factory indexes project structure.

Potential indexed entities include:

* functions;
* classes;
* modules;
* imports;
* exports;
* interfaces;
* symbols;
* configuration variables;
* dependency relationships.

Supported languages may include:

* Python;
* JavaScript;
* TypeScript;
* HTML;
* CSS;
* JSON;
* TOML.

Additional language ecosystems may be supported when their actual toolchains are available.

The key principle is:

> **Language support is determined by validated tool availability rather than catalogue membership alone.**

---

# 8. Requirement-to-Architecture Translation

Natural-language requirements are transformed into structured engineering specifications.

A requirement contract may contain:

```text id="m1p3ks"
Project
Objective
Features
Affected Components
Constraints
Dependencies
Security Requirements
Acceptance Criteria
Testing Requirements
Packaging Requirements
```

The system must distinguish between:

**What the user wants**

and

**How the system proposes to implement it**

This prevents implementation assumptions from becoming implicit requirements.

---

# 9. Implementation Planning

Before modifying multiple files, Watcher Eye constructs an implementation plan.

The plan may specify:

* files to create;
* files to modify;
* files that must remain unchanged;
* required dependencies;
* affected functions;
* expected interfaces;
* test requirements;
* packaging requirements;
* rollback strategy.

A large project may be decomposed into bounded tasks.

Each task should have an explicit completion condition.

---

# 10. Multi-File Code Generation

Software Factory treats a project as a connected system rather than a collection of independent code snippets.

A change may therefore require coordinated modifications to:

* source modules;
* configuration;
* interfaces;
* tests;
* documentation;
* package metadata.

Changes should be applied through controlled workspace operations.

Before sensitive modifications, a snapshot is created.

---

# 11. Code Review and Diff Control

The system should produce inspectable diffs before accepting sensitive changes.

The diff should identify:

* added files;
* removed files;
* modified files;
* added lines;
* removed lines;
* dependency changes;
* configuration changes.

Deletion and destructive changes require elevated permission.

This creates an explicit transition:

**Generated Change**

→ **Reviewed Change**

→ **Accepted Change**

---

# 12. Static Validation

Static validation provides an early quality gate.

Depending on the language, validation may include:

* syntax checking;
* AST parsing;
* import analysis;
* JSON validation;
* TOML validation;
* HTML validation;
* UTF-8 validation;
* secret-pattern detection;
* dependency inspection.

Static validation does not prove correctness.

It only establishes that selected structural conditions have been satisfied.

---

# 13. Automated Testing

The Software Factory executes project tests within a bounded environment when testing is enabled and the required toolchain is available.

The execution layer records:

* command;
* environment;
* duration;
* exit code;
* stdout;
* stderr;
* test count;
* failures;
* skipped tests;
* artifact information.

A test suite that has not actually executed cannot be represented as passing.

---

# 14. Test Interpretation

Watcher Eye separates:

**Test Not Run**

**Test Failed**

**Test Passed**

**Test Inconclusive**

This distinction is critical.

For example:

> "The test command could not execute because the dependency was unavailable."

must not be transformed into:

> "Tests passed."

The evidence layer therefore becomes responsible for determining the final status.

---

# 15. Bounded Automated Repair

When tests fail, the Software Factory may initiate a bounded repair loop.

The repair process is:

**Failure**

↓

**Failure Classification**

↓

**Candidate Repair**

↓

**Diff**

↓

**Static Validation**

↓

**Test**

↓

**Result**

The loop must have:

* maximum repair attempts;
* execution timeout;
* resource limits;
* rollback;
* scope restrictions.

If the repair budget is exhausted, the task becomes:

**Failed / Requires Human Review**

rather than continuing indefinitely.

---

# 16. Regression Protection

A repair that fixes one test while breaking another must be rejected.

Therefore, successful repair requires:

1. the original failing condition is resolved;
2. relevant tests pass;
3. previously passing tests remain valid;
4. project integrity is preserved.

This establishes a distinction between:

**Local Fix**

and

**System-Level Validated Fix**

---

# 17. Dependency Management

Software projects often depend on external packages.

Watcher Eye should therefore maintain project-specific dependency environments.

The host environment should not be modified unnecessarily.

Dependency management should record:

* package name;
* version;
* source;
* lock information;
* installation result;
* security status where available.

Uncontrolled dependency installation should not be treated as a normal implementation step.

---

# 18. External Source Acquisition

When external repositories are required, the preferred workflow is:

**Research**

↓

**Version Selection**

↓

**License Review**

↓

**Quarantine**

↓

**Hash Verification**

↓

**Static Inspection**

↓

**Isolated Build**

↓

**Testing**

↓

**Source Receipt**

External source material should not automatically enter the validated project knowledge base.

A repository becomes trusted only after the defined validation process succeeds.

---

# 19. Secret Protection

Software projects may contain:

* API keys;
* tokens;
* passwords;
* certificates;
* private keys;
* connection strings.

Watcher Eye should detect and protect these resources.

Secrets should not be:

* embedded into generated source;
* written into durable AI memory;
* included in exported ZIP files;
* exposed in execution logs;
* transmitted to external providers without explicit policy approval.

---

# 20. Software Build Pipeline

The build pipeline follows:

**Source Snapshot**

↓

**Dependency Preparation**

↓

**Static Validation**

↓

**Tests**

↓

**Build**

↓

**Artifact Verification**

↓

**Packaging**

↓

**Release Receipt**

The build system must record the toolchain used.

Examples include:

* Python;
* Node.js;
* .NET;
* Java;
* C/C++;
* Rust;
* Go.

Actual support depends on the presence and successful validation of the corresponding toolchain.

---

# 21. Packaging

Watcher Eye may integrate with packaging systems such as:

* PyInstaller;
* Nuitka;
* cx_Freeze;
* Cython;
* Inno Setup;
* platform-specific packaging tools.

However:

> **Knowledge of a packaging tool is not evidence that the tool is installed.**

The system must discover:

* executable location;
* version;
* compatibility;
* successful smoke test.

---

# 22. Windows Build from Linux

One important engineering scenario is cross-platform Windows packaging from a Linux environment.

The proposed architecture may use:

* Wine;
* Windows Python;
* Windows-compatible build tools;
* isolated build prefixes;
* Xvfb where graphical execution is required.

A generated Windows executable should not be declared successfully delivered solely because a build command returned successfully.

The release gate should verify:

1. PE/MZ executable existence;
2. artifact size;
3. SHA-256;
4. executable startup;
5. expected runtime behaviour;
6. project tests;
7. packaging integrity.

For installer delivery, additional evidence is required:

* actual installer artifact;
* clean installation;
* successful application launch;
* uninstall;
* user-data preservation;
* retained logs.

---

# 23. Checkpoints and Resumability

Large software projects may require long execution times.

Watcher Eye therefore maintains checkpoints between major stages.

A checkpoint may record:

* project fingerprint;
* completed stages;
* pending tasks;
* generated artifacts;
* test status;
* build status;
* tool versions;
* resource state.

If execution is interrupted, the workflow can resume from the latest valid checkpoint rather than restarting the entire project.

---

# 24. Resource-Aware Software Engineering

Large builds, test suites, and code-analysis workloads can consume significant CPU and memory.

Watcher Eye should therefore enforce:

* CPU limits;
* memory limits;
* disk limits;
* process limits;
* execution timeouts;
* process-tree cancellation.

Resource exhaustion should result in a controlled state rather than silent failure.

Where possible, valid intermediate state should be preserved for later resumption.

---

# 25. Software Verification Model

The framework distinguishes five levels of software evidence.

### Level 0 — Generated

Source code was produced.

### Level 1 — Structurally Valid

The source passed applicable syntax and structural checks.

### Level 2 — Tested

The project executed its defined test suite.

### Level 3 — Build Verified

A valid target artifact was produced and verified.

### Level 4 — Acceptance Verified

The complete acceptance criteria were demonstrated with retained evidence.

This hierarchy prevents a source file from being presented as a production-ready application without appropriate validation.

---

# 26. Evidence-Based Release Gate

A release should require evidence appropriate to the project.

Potential evidence includes:

* source fingerprint;
* dependency manifest;
* static-analysis results;
* test results;
* build log;
* artifact hash;
* executable smoke test;
* installation test;
* configuration validation;
* acceptance test;
* packaging manifest.

The system should reject the final state when required evidence is missing.

---

# 27. Software Knowledge and Verified Code Registry

Successful implementations may become reusable knowledge.

However, reusable code should enter a Verified Code Registry only when it has:

* provenance;
* project context;
* source hash;
* dependency information;
* test receipt;
* lifecycle status.

Possible lifecycle states are:

**Draft**

**Tested**

**Verified**

**Deprecated**

**Quarantined**

This prevents old code from being reused without considering its original environment.

---

# 28. Failure Taxonomy

The Software Factory distinguishes:

### S1 — Requirement Failure

The requirement cannot be interpreted reliably.

### S2 — Architecture Failure

The requested feature conflicts with the existing design.

### S3 — Dependency Failure

A required dependency is unavailable or incompatible.

### S4 — Implementation Failure

The generated implementation fails structural or functional requirements.

### S5 — Test Failure

One or more tests fail.

### S6 — Build Failure

The target artifact cannot be produced.

### S7 — Packaging Failure

The artifact cannot be packaged or installed correctly.

### S8 — Verification Failure

The operation completed technically but did not satisfy acceptance criteria.

### S9 — Resource Failure

Execution exceeded CPU, memory, disk, process, or time limits.

### S10 — Security Failure

The requested operation violates a security or permission policy.

---

# 29. Experimental Methodology

A rigorous evaluation should use a benchmark containing projects with varying levels of complexity.

The benchmark should include:

* small single-module projects;
* multi-file applications;
* existing projects requiring modification;
* projects containing intentional defects;
* dependency conflicts;
* failing tests;
* packaging failures;
* resource constraints;
* security-sensitive configurations.

Each benchmark project should have predefined ground-truth requirements and acceptance criteria.

---

# 30. Evaluation Metrics

## 30.1 Requirement Interpretation Accuracy

Measure:

* correct feature extraction;
* correct constraint extraction;
* correct file targeting;
* correct acceptance criteria.

---

## 30.2 Code Correctness

Measure:

* syntax success;
* static validation success;
* functional test success;
* regression test success.

---

## 30.3 Multi-File Consistency

Measure:

* interface compatibility;
* dependency consistency;
* cross-module correctness;
* unintended modification rate.

---

## 30.4 Repair Effectiveness

Measure:

* percentage of failures successfully repaired;
* average repair attempts;
* regression introduction rate;
* repair time.

---

## 30.5 Build Reliability

Measure:

* successful build rate;
* artifact validity;
* executable smoke-test success;
* packaging success.

---

## 30.6 Evidence Integrity

Measure:

* false-success rate;
* missing-evidence rate;
* incorrect test-status classification;
* artifact/hash consistency.

---

# 31. Proposed Benchmark Scenarios

### Scenario A — New Project

Generate a project from a structured requirement.

### Scenario B — Existing Project Modification

Modify an existing multi-file project.

### Scenario C — Defect Repair

Repair an intentionally defective project.

### Scenario D — Dependency Failure

Introduce an unavailable or incompatible dependency.

### Scenario E — Test Failure

Introduce failing tests and evaluate bounded repair.

### Scenario F — Build Failure

Introduce a build configuration error.

### Scenario G — Resource Pressure

Execute the project under CPU and memory constraints.

### Scenario H — Cancellation

Cancel a long-running build or test process.

### Scenario I — Secret Detection

Introduce credentials into a project and verify that they are not exported.

### Scenario J — Packaging

Build and verify a target executable or distribution package.

---

# 32. Security Model

Software Factory operations must follow least privilege.

Controls include:

* isolated project workspaces;
* dependency isolation;
* path restrictions;
* secret scanning;
* package-script controls;
* sandboxing where appropriate;
* network restrictions;
* execution timeouts;
* process-tree cancellation;
* snapshots;
* audit records.

Untrusted external code should be treated as untrusted until validated.

---

# 33. Human Oversight

Human intervention remains necessary for ambiguous or high-risk conditions.

Human review may be required when:

* requirements conflict;
* architecture is unclear;
* security-sensitive changes are detected;
* destructive changes are proposed;
* tests are inconclusive;
* evidence is insufficient;
* repair attempts exceed the allowed budget.

The system should therefore optimise for **safe autonomy**, not unrestricted autonomy.

---

# 34. Discussion

Watcher Eye Software Factory represents a transition from AI-assisted code generation toward AI-assisted software engineering.

The distinction is important.

A code-generation system primarily answers:

> "Can AI produce source code?"

A software engineering system must answer:

> "Can the system produce, modify, test, validate, package, and document a software project while proving that the resulting state satisfies its requirements?"

The Software Factory architecture addresses the second question.

Its principal design feature is the separation between:

**AI Understanding**

and

**Engineering Execution**

The AI may propose an implementation, but the workspace, compiler, test suite, packaging system, and verification gates determine whether the implementation is actually valid.

---

# 35. Limitations

The framework has several limitations.

### 35.1 Language Ecosystem Diversity

Different programming languages require different compilers, package managers, testing frameworks, and runtime environments.

### 35.2 Test Quality

Passing tests cannot guarantee the absence of all defects.

### 35.3 AI Interpretation

Ambiguous requirements may still require human clarification.

### 35.4 External Dependencies

Tool availability, licensing, operating-system compatibility, and network policy may prevent execution.

### 35.5 Large-Scale Validation

Quantitative claims require evaluation across sufficiently diverse benchmark projects.

### 35.6 Production Deployment

Successful local testing does not automatically establish production readiness.

---

# 36. Research Contributions

The principal contributions of this work are:

1. **An evidence-driven Software Factory architecture** for AI-assisted multi-file software engineering.

2. **A project-understanding model** that analyses existing software before modification.

3. **A controlled multi-file implementation workflow** with snapshots and inspectable diffs.

4. **A bounded automated repair architecture** based on testing and explicit repair budgets.

5. **An evidence-based software completion model** separating generated, structurally valid, tested, build-verified, and acceptance-verified states.

6. **A project-scoped knowledge model** that binds reusable code to provenance, fingerprints, dependencies, and validation evidence.

7. **A controlled external-source acquisition process** for repositories and dependencies.

8. **A reproducible software engineering evaluation methodology** covering requirements, implementation, testing, repair, packaging, and evidence integrity.

---

# 37. Future Research

Future work will investigate:

* large-scale autonomous project development;
* architectural refactoring;
* repository-level program repair;
* automated dependency migration;
* continuous integration orchestration;
* software supply-chain verification;
* formal specification generation;
* automated acceptance-test synthesis;
* distributed build systems;
* multi-agent software engineering;
* autonomous maintenance of long-lived projects;
* human-AI collaborative engineering environments.

---

# 38. Conclusion

This paper presented Watcher Eye Software Factory as an evidence-driven framework for AI-assisted software engineering.

The framework extends AI capabilities beyond isolated code generation by introducing project understanding, architecture analysis, controlled multi-file implementation, static validation, automated testing, bounded repair, packaging, snapshots, checkpoints, and evidence-based release gates.

The fundamental workflow is:

**Requirement**

→ **Understanding**

→ **Architecture**

→ **Plan**

→ **Implementation**

→ **Test**

→ **Repair**

→ **Build**

→ **Verification**

→ **Evidence**

The architecture therefore treats software development as an engineering lifecycle rather than a sequence of generated responses.

The central principle is:

> **Generated code is not verified software.**

A software system becomes a verified deliverable only when its implementation, tests, build artifacts, acceptance criteria, and associated evidence support the completion claim.

Watcher Eye Software Factory consequently provides a foundation for studying how AI can participate in complex software engineering workflows while preserving deterministic execution, reproducibility, safety, and human control.

---

# Appendix A — Software Factory Lifecycle

```text id="u2g8sz"
Requirement
    ↓
Intent Translation
    ↓
Project Discovery
    ↓
Architecture Analysis
    ↓
Implementation Plan
    ↓
Snapshot
    ↓
Multi-File Implementation
    ↓
Diff Review
    ↓
Static Validation
    ↓
Testing
    ↓
Failure Analysis
    ↓
Bounded Repair
    ↓
Regression Testing
    ↓
Build
    ↓
Packaging
    ↓
Artifact Verification
    ↓
Evidence Receipt
    ↓
Validated Release
```

---

# Appendix B — Evidence Levels

| Level | State               | Evidence                     |
| ----- | ------------------- | ---------------------------- |
| 0     | Generated           | Source artifact              |
| 1     | Structurally Valid  | Static validation            |
| 2     | Tested              | Test receipt                 |
| 3     | Build Verified      | Build artifact + hash        |
| 4     | Acceptance Verified | Complete acceptance evidence |

---

# Appendix C — Project Receipt

A project release receipt should contain, where applicable:

* Project ID
* Project fingerprint
* Source snapshot
* Changed files
* Dependency manifest
* Toolchain versions
* Static-analysis results
* Test results
* Build result
* Artifact SHA-256
* Packaging result
* Acceptance-test result
* Verification status
* Timestamp
* Execution environment

---

# Appendix D — Relationship to the Watcher Eye Research Series

This paper represents the software-engineering application of the general Watcher Eye architecture established in Paper I.

The research series can subsequently extend into specialised domains including:

**Paper II — Automotive**

ECU firmware analysis and deterministic binary modification.

**Paper III — Software Engineering**

Multi-file software engineering, testing, repair, and verified delivery.

**Paper IV — Server Operations**

Server management, monitoring, recovery, and Root Cause Analysis.

**Paper V — Cyber Defense**

Defensive cybersecurity and evidence-driven security orchestration.

Each domain-specific paper should provide its own datasets, experiments, evaluation metrics, and validation evidence while retaining the common principles of the Watcher Eye architecture.
