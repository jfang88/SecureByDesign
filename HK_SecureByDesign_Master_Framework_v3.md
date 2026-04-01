# Secure by Design Master Framework
## Hong Kong Critical Infrastructure and SFC-Regulated Exchange Edition

**Version:** 3.0  
**Date:** April 2026  
**Audience:** Board, CEO, CISO, Security Architecture, Technology Risk, Operational Resilience, Compliance, Internal Audit  
**Primary Regulatory Context:** Protection of Critical Infrastructures (Computer Systems) Ordinance (Cap. 653), SFC requirements for an exchange / market operator  
**Secondary / Informative References:** GovCERT/DPO Security by Design, G3, S17, PDPO privacy by design, CISA, UK NCSC, ASD/ACSC, Singapore CSA, OWASP Secure by Design draft

---

## Executive Summary

For a Hong Kong critical infrastructure operator that is also regulated by the SFC as an **exchange** rather than a retail intermediary or bank, the Secure by Design baseline should start with the Protection of Critical Infrastructures (Computer Systems) Ordinance (Cap. 653), then layer SFC operational resilience and governance expectations, and only then map in GovCERT/DPO, OWASP, CISA, UK NCSC, ASD and Singapore guidance. [cite:70][cite:73][cite:75]

The Ordinance establishes statutory obligations for designated critical infrastructure operators across three obligation groups: organizational obligations, preventive obligations, and incident reporting and response obligations. It also requires a Hong Kong office, a dedicated computer-system security management unit, a computer-system security management plan, risk assessments, security audits, drills, an emergency response plan, and incident notification. [cite:71][cite:73][cite:74]

This report restores the fuller history and detailed control-level comparison from the earlier versions, while preserving the updated Hong Kong legal and exchange-specific layering. The result is a compliance-first Secure by Design framework with enough detail to support board briefing, control architecture, control testing, procurement, and regulator traceability. [cite:71][cite:75][cite:42][cite:1]

---

## Section 1: History of Secure by Design

### 1.1 Conceptual Origins

Secure by Design did not start from a single modern government framework. It emerged from several streams of security engineering, systems architecture, and privacy engineering that later converged into today’s policy-driven SbD movement. [cite:9][cite:16][cite:31]

The earliest conceptual roots are the classic protection design principles described by Saltzer and Schroeder in 1975, especially **least privilege**, **fail-safe defaults**, **economy of mechanism**, and **separation of privilege**. Those principles later influenced secure architecture, identity design, access control models, and secure defaults in modern product security frameworks. [cite:9]

In the 2000s, industry frameworks such as Microsoft’s Secure Development Lifecycle helped move security into the SDLC rather than treating it as a post-build testing step. Later, privacy-by-design concepts, particularly Ann Cavoukian’s 2009 formulation, expanded this “design-time” mindset and strongly influenced Hong Kong’s privacy discourse through PCPD/PCPD-related privacy-by-design material. [cite:16][cite:60]

### 1.2 Evolution into government and industry frameworks

The UK NCSC secure design principles represent one of the earliest mature government articulations of security as an architectural property rather than a checklist. NCSC framed the goal around establishing context, making compromise difficult, making disruption difficult, making detection easier, and reducing the impact of compromise. [cite:9]

The 2023 CISA Secure by Design initiative marked a major shift because it moved the conversation from “customers should configure products securely” to “manufacturers should bear more responsibility for secure outcomes.” It also introduced measurable and market-facing expectations such as secure-by-default, reducing entire vulnerability classes, and stronger vendor accountability. [cite:31][cite:35][cite:44]

Australia’s ASD/ACSC foundations added a strong lifecycle perspective, especially around secure deprecation and the split between manufacturer and consumer responsibilities. Singapore’s CSA aligned with the joint principles and added a more critical-services and operational technology orientation. OWASP’s Secure by Design draft then brought detailed implementation patterns for modern architectures such as APIs, service meshes, and distributed systems. [cite:2][cite:50][cite:63][cite:1]

### 1.3 Hong Kong’s place in the timeline

Hong Kong’s GovCERT / DPO Practice Guide for Security by Design v1.1 sits in a different place in the evolution. It is less of a high-level principle manifesto and more of an implementation and governance guide structured around SDLC phases, security planning, risk analysis, testing, and phase gates. [cite:42]

The Protection of Critical Infrastructures (Computer Systems) Ordinance then changes the local picture materially by giving critical computer-system protection a statutory basis. That means that for designated operators, Secure by Design is no longer just good engineering or regulator guidance; it is now directly connected to legal obligations, oversight, and enforceable duties. [cite:71][cite:73]

### 1.4 Timeline

| Year | Framework / event | Significance |
|---|---|---|
| 1975 | Saltzer & Schroeder protection principles | Earliest conceptual roots of least privilege, fail-safe defaults, and economy of mechanism. [cite:9] |
| 2004 | Microsoft SDL | Mainstreamed secure activities inside the software development lifecycle. [cite:60] |
| 2009 | Privacy by Design | Reinforced security/privacy as default design properties; influential for HK privacy thinking. [cite:16] |
| ~2017 | Early UK NCSC secure design work | Early public government articulation of architecture-led security. [cite:9] |
| 2019 | UK NCSC Secure Design Principles collection | Mature principle set for compromise resistance, resilience, detection, and impact reduction. [cite:9] |
| 2022 | NIST SSDF SP 800-218 | Became an important SDLC reference point for later SbD frameworks. [cite:60] |
| Apr 2023 | CISA Secure by Design principles | Major vendor-accountability turning point. [cite:31][cite:38] |
| Oct 2023 | Joint international update, including Singapore support | Demonstrated international convergence. [cite:34][cite:44][cite:50] |
| Jul 2024 | ASD/ACSC Secure by Design Foundations | Strengthened lifecycle framing, especially secure deprecation. [cite:2] |
| Jul 2024 | HK GovCERT Practice Guide for Security by Design v1.1 | Local SDLC-governance pattern for design-time security. [cite:42] |
| Dec 2024 | Protection of Critical Infrastructures (Computer Systems) Bill introduced | Established the path to a statutory baseline for CI operators. [cite:74][cite:71] |
| Mar 2025 | Cap. 653 passed / gazetted | Created Hong Kong’s formal legal framework for critical computer-system security. [cite:73][cite:77] |
| Jan 2026 | Cap. 653 comes into operation | Compliance becomes live for designated operators. [cite:73][cite:77] |
| Aug 2025 | OWASP Secure by Design Framework Draft v0.5.0 | Added detailed API / microservices / distributed-system patterns. [cite:1] |

---

## Section 2: Regulatory Priority Model for a Hong Kong Exchange

### 2.1 Priority order

| Priority | Instrument / framework | Role in the framework |
|---|---|---|
| 1 | Protection of Critical Infrastructures (Computer Systems) Ordinance (Cap. 653) | Mandatory statutory baseline for designated CI operators. [cite:70][cite:73] |
| 2 | SFC operational resilience and governance expectations | Sector-specific resilience and supervisory layer for exchange-like entities. [cite:75][cite:81] |
| 3 | GovCERT / DPO SbD Guide, G3, S17, PDPO | Local implementation model and privacy/security operating guidance. [cite:42][cite:16] |
| 4 | CISA / NCSC / ASD / Singapore CSA / OWASP | Enhancement and benchmarking layer. [cite:31][cite:9][cite:2][cite:50][cite:1] |

### 2.2 Why this order matters

For this organisation, the critical infrastructure law and SFC oversight define the **mandatory outcomes**. GovCERT/DPO then provides the most practical local **delivery model** for embedding those outcomes into the SDLC and operating model. The international frameworks are best used to enrich and modernise the control set, especially where local documents are less explicit on topics such as SBOM, secure deprecation, or service-to-service identity. [cite:71][cite:75][cite:42][cite:34][cite:2][cite:1]

HKMA expectations can still be informative for resilience and risk governance, but they should not drive the baseline because the entity is not a bank. The SFC and Cap. 653 should be treated as the primary supervisory and legal anchors. [cite:75][cite:84]

---

## Section 3: High-Level Requirements from Cap. 653

### 3.1 Three statutory obligation groups

The law groups obligations into three categories, which can be translated directly into Secure by Design objectives. [cite:71]

| Statutory group | Meaning in law | Secure by Design interpretation |
|---|---|---|
| Organizational obligations | Establish structures, roles, local presence, and governance. [cite:71] | Security ownership, accountable management, and durable governance are mandatory design inputs. |
| Preventive obligations | Put measures in place to reduce threats and incidents. [cite:71] | Risk assessment, architecture review, hardening, testing, and continuous control assurance become mandatory. |
| Incident reporting and response obligations | Detect, notify, and respond to incidents. [cite:71] | Logging, alerting, classification, crisis response, and regulator reporting must be engineered into systems and operations. |

### 3.2 Explicit duties and design implications

| Duty | Source basis | Secure by Design implication |
|---|---|---|
| Maintain an office in Hong Kong | Section 19. [cite:71] | Local accountability, regulator communication, and operational ownership must exist. |
| Notify changes in operator information | Section 20. [cite:71] | Governance and change-management processes must include legal / entity-level changes. |
| Set up and maintain a computer-system security management unit | Section 21. [cite:71] | A permanent cyber management function is mandatory. |
| Submit and implement a security management plan | Section 23 and Schedule 3. [cite:71] | Security objectives, governance, and operating controls must be documented and maintained. |
| Conduct risk assessments | Section 24 and Schedule 4. [cite:71] | Threat modeling and periodic risk assessment are statutory, not optional. |
| Carry out security audits | Section 25 and Schedule 5. [cite:71] | Independent assurance and evidence collection must be part of the framework. |
| Participate in drills | Section 26. [cite:71] | Tabletop and technical exercises must be built into the resilience lifecycle. |
| Submit and implement an emergency response plan | Section 27 and Schedule 3. [cite:71] | Incident response and recovery cannot be ad hoc; they must be predesigned and documented. |
| Notify incidents | Section 28 and Schedule 6. [cite:71] | Detection, incident classification, escalation, and notification processes must be engineered. |

### 3.3 What is different about the statutory layer

Unlike most international Secure by Design frameworks, Cap. 653 is not just a principle or maturity model. It directly couples design and operating controls to legal duties, regulator powers, oversight, and penalties. That makes documentation, evidence, repeatability, and auditability first-class control objectives. [cite:71][cite:73]

---

## Section 4: SFC Exchange-Specific Layer

### 4.1 Why the SFC layer is different for an exchange

An exchange or exchange-like operator has a stronger need to preserve orderly operation, service continuity, dependency resilience, and management oversight than a retail internet-trading lens alone would imply. The design target is therefore not only customer protection but also market integrity, platform continuity, surveillance continuity, and disruption tolerance for critical market functions. [cite:75][cite:76]

### 4.2 SFC themes that should shape the framework

| SFC theme | Implication for Secure by Design |
|---|---|
| Governance framework | Senior management and board-level oversight of resilience objectives and arrangements. [cite:75] |
| Ongoing identification of disruptive incidents | Build dependency mapping, telemetry, scenario analysis, and service-health monitoring. [cite:75] |
| Response and adaptation | Engineer failover, degraded modes, crisis playbooks, and service recovery procedures. [cite:75][cite:81] |
| Designated monitoring and oversight roles | Establish defined SOC, resilience, operations, and escalation responsibilities. [cite:75] |
| Management information | Design dashboards, KRIs, incident trends, and resilience reporting for executives. [cite:75] |

### 4.3 Practical effect on the master framework

This means the framework should treat platform availability, service recovery, dependency resilience, incident communication, and executive reporting as core design objectives, not just operational afterthoughts. It also means that testing must include disruptive scenarios and not merely vulnerability scanning or penetration tests. [cite:75][cite:81]

---

## Section 5: Framework Comparison — Focus, Alignment, and Uniqueness

### 5.1 High-level comparison

| Framework | Primary audience | Main focus | What it adds |
|---|---|---|---|
| Cap. 653 | Designated CI operators in HK | Legal obligations, supervision, evidence, incident response. [cite:71] | Statutory force, mandatory governance, risk assessment, audits, drills, incident reporting. |
| SFC resilience expectations | SFC-regulated exchange / platform operators | Governance, resilience, disruption management. [cite:75] | Sector-specific resilience lens for critical market functions. |
| HK GovCERT / DPO SbD | HK public-sector style SDLC and broader HK adopters | Security planning, SDLC phase control gates, testing, procurement. [cite:42] | Local implementation discipline and phase-gate governance. |
| UK NCSC | Designers of systems and cyber-physical systems | Architecture and design principles. [cite:9] | Clean compromise-resistance / resilience model. |
| CISA | Software manufacturers and technology providers | Vendor accountability, secure-by-default, measurable outcomes. [cite:31][cite:35] | Market-facing accountability and vulnerability-class reduction. |
| ASD/ACSC | Manufacturers and consumers | Full lifecycle, including secure deprecation. [cite:2] | Decommissioning and manufacturer / consumer split. |
| Singapore CSA | Critical services and software providers | Joint alignment plus critical-service orientation. [cite:50][cite:63] | Critical-service / OT emphasis and ecosystem assurance. |
| OWASP SbD draft | Security architects and developers | Detailed engineering patterns. [cite:1] | API, identity, service mesh, resilience, microservices detail. |

### 5.2 Where Hong Kong DPO differs from others

| HK DPO / GovCERT characteristic | Difference from other frameworks |
|---|---|
| Security Planning at initiation | More prescriptive than CISA/NCSC principle sets. [cite:42] |
| Preliminary Risk Analysis at feasibility stage | Earlier explicit gating than most. [cite:42] |
| SDLC phase control gates | More process-governed than OWASP or NCSC. [cite:42] |
| Bureau / Department accountability model | Stronger explicit ownership mapping. [cite:42] |
| Security requirements in tenders / procurement | More tightly linked to acquisition than several international frameworks. [cite:42] |
| Integration with G3 and S17 | Strong local policy-stack context. [cite:42] |

### 5.3 What external frameworks contribute beyond HK DPO

| External source | Useful addition |
|---|---|
| CISA | Secure-by-default, measurable manufacturer commitments, public accountability, vulnerability-class elimination. [cite:31][cite:35] |
| NCSC | Strong architectural objective model for resilience and reduced impact. [cite:9] |
| ASD | Secure deprecation and lifecycle exit handling. [cite:2] |
| Singapore CSA | Critical-service and OT deployment discipline. [cite:50][cite:63] |
| OWASP | Detailed technical patterns for APIs, service-to-service identity, DPoP, mTLS, circuit breakers, and distributed tracing. [cite:1] |

---

## Section 6: Master Control Domains and Detailed Crosswalk

The following 10-domain model is the recommended master structure for a Hong Kong critical exchange. Each domain is shown with common controls, HK-specific controls, and notable external enhancements.

### Domain 1: Governance and Accountability

**Objective:** Establish durable ownership, legal accountability, and executive oversight for critical computer-system security and resilience.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Board / senior management accountability | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | ✅ [cite:31] | Partial [cite:9] | ✅ [cite:2] | ✅ [cite:50] | Partial [cite:1] |
| Dedicated security management unit / function | ✅ [cite:71] | Partial [cite:75] | ✅ [cite:42] | Partial [cite:31] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | ❌ |
| Security management plan / governance documentation | ✅ [cite:71] | Partial [cite:75] | ✅ [cite:42] | Partial [cite:31] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | Partial [cite:1] |
| Clear roles and responsibilities | ✅ [cite:71] | ✅ [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Local HK office / local accountability | ✅ [cite:71] | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Public vendor pledge / outcome reporting | ❌ | ❌ | ❌ | ✅ [cite:35][cite:62] | ❌ | Partial [cite:2] | ❌ | ❌ |

**Interpretation:** The common baseline is executive accountability and documented governance, but the HK statutory requirement for a local office and dedicated security management unit is materially more concrete than most international frameworks. [cite:71][cite:42]

### Domain 2: Asset / System Designation and Dependency Mapping

**Objective:** Identify which systems, services, and dependencies are critical, then design controls proportionate to their importance.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Identify critical systems / assets | ✅ [cite:71] | ✅ [cite:75] | ✅ [cite:42] | Partial [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | Partial [cite:1] |
| Dependency mapping | Partial [cite:71] | ✅ [cite:75] | Partial [cite:42] | Partial [cite:31] | ✅ [cite:9] | ✅ [cite:2] | Partial [cite:63] | ✅ [cite:1] |
| System classification drives controls | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ❌ | ❌ | Partial [cite:2] | ❌ | ❌ |
| Core service / function identification | Partial [cite:71] | ✅ [cite:75] | Partial [cite:42] | ❌ | Partial [cite:9] | Partial [cite:2] | ✅ [cite:63] | ❌ |

**Interpretation:** The HK framework should explicitly preserve DPO-style system classification and combine it with SFC-style critical service and dependency mapping. That combination is stronger for an exchange than either approach alone. [cite:42][cite:75]

### Domain 3: Security Planning and Architecture

**Objective:** Build security and resilience into the architecture from inception.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Security planning at project start | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | Partial [cite:31] | ✅ [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| Architecture review | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Defense in depth | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Segmentation / isolation | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Reduced blast radius | Partial [cite:71] | ✅ [cite:75] | Partial [cite:42] | Partial [cite:31] | ✅ [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| mTLS / strong service identity | ❌ | ❌ | ❌ | Partial [cite:31] | ❌ | ❌ | ❌ | ✅ [cite:1] |

### Domain 4: Threat Modeling and Risk Assessment

**Objective:** Identify likely threats and design mitigations before build and before major change.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Threat modeling in design | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Preliminary feasibility-stage risk review | ❌ | ❌ | ✅ [cite:42] | ❌ | ❌ | ❌ | ❌ | Partial [cite:1] |
| Periodic formal risk assessments | ✅ [cite:71] | ✅ [cite:75] | ✅ [cite:42] | Partial [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| CIA impact analysis | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | Partial [cite:31] | ✅ [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| Data flow / trust boundary mapping | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | Partial [cite:31] | Partial [cite:9] | Partial [cite:2] | Partial [cite:50] | ✅ [cite:1] |

### Domain 5: Identity, Access, and Secrets

**Objective:** Enforce least privilege, strong authentication, and managed secrets throughout the lifecycle.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Least privilege | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| MFA for privileged/sensitive access | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:35] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| No default/static credentials | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:35][cite:65] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| RBAC | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Managed secrets / vaulting | Partial [cite:71] | Partial [cite:75] | Partial [cite:42] | Partial [cite:31] | ✅ [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| DPoP / OAuth patterns | ❌ | ❌ | ❌ | Partial [cite:31] | ❌ | ❌ | ❌ | ✅ [cite:1] |

### Domain 6: Secure Engineering and Assurance

**Objective:** Build secure software and configurations through repeatable development, review, and testing activities.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Secure coding guidelines | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:31][cite:60] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Code review / peer review | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:60] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| SAST / DAST / vuln scanning | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:31][cite:60] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| Penetration testing | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | ✅ [cite:60] | ✅ [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| Input validation / secure-by-default coding | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:35] | ✅ [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| Memory-safe languages | ❌ | ❌ | ❌ | ✅ [cite:35] | ❌ | Partial [cite:2] | ❌ | Partial [cite:1] |
| Eliminate vulnerability classes | ❌ | ❌ | ❌ | ✅ [cite:35][cite:62] | ❌ | Partial [cite:2] | ❌ | ✅ [cite:1] |

### Domain 7: Supply Chain and Procurement Security

**Objective:** Ensure external software, services, and dependencies do not undermine critical-system security.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Third-party security assessment | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Security requirements in tenders/contracts | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | ✅ [cite:31] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | Partial [cite:1] |
| Dependency / component assurance | Partial [cite:71] | Partial [cite:75] | Partial [cite:42] | ✅ [cite:31] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:63] | ✅ [cite:1] |
| SBOM | ❌ | ❌ | ❌ | ✅ [cite:34][cite:67] | ❌ | Partial [cite:2] | Partial [cite:63] | Partial [cite:1] |
| VEX / exploitability exchange | ❌ | ❌ | ❌ | ✅ [cite:34] | ❌ | Partial [cite:2] | ❌ | ❌ |

### Domain 8: Monitoring, Logging, and Security Operations

**Objective:** Detect compromise and disruption quickly enough to meet both resilience and statutory incident obligations.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Centralized logging | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Alerting / anomaly detection | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Defined monitoring roles | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | Partial [cite:31] | Partial [cite:9] | Partial [cite:2] | Partial [cite:50] | Partial [cite:1] |
| Security operations workflow | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | Partial [cite:31] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| Distributed tracing / runtime observability | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ [cite:1] |

### Domain 9: Incident Reporting, Drills, and Resilience Response

**Objective:** Ensure the organisation can classify, escalate, report, contain, and recover from cyber incidents affecting critical services.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Incident response plan | ✅ [cite:71] | ✅ [cite:75] | ✅ [cite:42] | ✅ [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:50] | ✅ [cite:1] |
| Regulatory / external notification | ✅ [cite:71] | Partial [cite:75] | Partial [cite:42] | Partial [cite:31] | Partial [cite:9] | Partial [cite:2] | Partial [cite:50] | ❌ |
| Tabletop / technical drills | ✅ [cite:71] | ✅ [cite:75] | Partial [cite:42] | Partial [cite:31] | Partial [cite:9] | Partial [cite:2] | Partial [cite:63] | Partial [cite:1] |
| Failover and degraded-mode planning | Partial [cite:71] | ✅ [cite:75] | Partial [cite:42] | Partial [cite:31] | ✅ [cite:9] | ✅ [cite:2] | ✅ [cite:63] | ✅ [cite:1] |
| Post-incident review / lessons learned | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | Partial [cite:31] | ✅ [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |

### Domain 10: Audit, Evidence, and Continuous Improvement

**Objective:** Sustain the framework through formal review, auditability, remediation, and lifecycle management.

| Control | Cap. 653 | SFC | HK DPO | CISA | NCSC | ASD | CSA | OWASP |
|---|---|---|---|---|---|---|---|---|
| Periodic audit | ✅ [cite:71] | Partial [cite:75] | ✅ [cite:42] | Partial [cite:31] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | Partial [cite:1] |
| Formal evidence and documentation | ✅ [cite:71] | ✅ [cite:75] | ✅ [cite:42] | Partial [cite:31] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | Partial [cite:1] |
| Remediation tracking | Partial [cite:71] | ✅ [cite:75] | ✅ [cite:42] | Partial [cite:31] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | ✅ [cite:1] |
| Post-implementation review | Partial [cite:71] | Partial [cite:75] | ✅ [cite:42] | Partial [cite:31] | Partial [cite:9] | ✅ [cite:2] | Partial [cite:50] | Partial [cite:1] |
| Secure deprecation / retirement | ❌ | Partial [cite:75] | Partial [cite:42] | Partial [cite:31] | Partial [cite:9] | ✅ [cite:2] | ❌ | Partial [cite:1] |

---

## Section 7: Common Controls, HK-Specific Controls, and External Enhancements

### 7.1 Controls common across most frameworks

The following controls appear explicitly or near-explicitly across HK DPO, CISA, UK NCSC, ASD, Singapore CSA, and OWASP:

- Threat modeling during design. [cite:42][cite:31][cite:9][cite:2][cite:50][cite:1]
- Least privilege and role-based access control. [cite:42][cite:31][cite:9][cite:2][cite:50][cite:1]
- MFA or strong authentication for sensitive access. [cite:42][cite:35][cite:9][cite:2][cite:50][cite:1]
- Secure defaults / hardening. [cite:42][cite:31][cite:9][cite:2][cite:50][cite:1]
- Logging and monitoring. [cite:42][cite:31][cite:9][cite:2][cite:50][cite:1]
- Security testing before production. [cite:42][cite:31][cite:9][cite:2][cite:50][cite:1]
- Incident response planning. [cite:42][cite:31][cite:9][cite:2][cite:50][cite:1]
- Patching and vulnerability management. [cite:42][cite:31][cite:9][cite:2][cite:50][cite:1]

### 7.2 HK-specific controls or emphases

| HK-specific item | Why it matters |
|---|---|
| Statutory security management unit | Gives the framework a permanent mandated operating owner. [cite:71] |
| HK office / local accountability | Creates a jurisdiction-specific legal accountability point. [cite:71] |
| Security management plan submission and implementation | Makes documentation and control architecture legally significant. [cite:71] |
| Statutory risk assessments and audits | Turns assurance from best practice into obligation. [cite:71] |
| Incident notification duties | Requires response processes to be regulator-ready. [cite:71] |
| DPO SDLC phase control gates | Gives HK a very practical project lifecycle mechanism. [cite:42] |
| Security requirements in tenders | Makes procurement control explicit. [cite:42] |

### 7.3 Useful external enhancements to add deliberately

| Source | Enhancement to adopt |
|---|---|
| CISA | Secure-by-default outcomes, customer-burden reduction, vulnerability-class elimination, and measurable tracking. [cite:31][cite:35] |
| ASD | Secure deprecation and end-of-support lifecycle management. [cite:2] |
| OWASP | mTLS, DPoP, service identity, runtime observability, distributed-system patterns. [cite:1] |
| NCSC | Design around making compromise difficult and reducing the impact of compromise. [cite:9] |
| Singapore CSA | Critical-service and OT-aware deployment thinking for market infrastructure dependencies. [cite:50][cite:63] |

---

## Section 8: Recommended Control Objectives for a Hong Kong Critical Exchange

### 8.1 Governance and legal accountability

- Maintain a Hong Kong operating presence and documented regulator contact model aligned to Cap. 653. [cite:71]
- Establish a permanent computer-system security management unit with authority over security planning, monitoring, and incident governance. [cite:71]
- Assign board and senior management accountability for cyber resilience, exchange continuity, and risk acceptance. [cite:75]
- Define critical services, critical systems, and critical dependencies with executive approval. [cite:71][cite:75]

### 8.2 Design and build objectives

- Require Security Planning and architecture review at project initiation and before material change. [cite:42]
- Require threat modeling for all systems that support core exchange operations or important dependencies. [cite:42][cite:71][cite:1]
- Design for segmentation, least privilege, strong authentication, secure defaults, and failure containment. [cite:42][cite:31][cite:9][cite:1]
- Apply stronger service identity and secret-management patterns for APIs, middleware, and distributed services. [cite:1]

### 8.3 Assurance and resilience objectives

- Embed SAST, DAST, dependency analysis, penetration testing, and configuration reviews into release governance. [cite:42][cite:31][cite:1]
- Implement centralized logging and monitoring sufficient to support statutory incident classification and notification. [cite:71][cite:42]
- Maintain and test emergency response plans for cyber incidents, service degradation, failover, and recovery of critical functions. [cite:71][cite:75]
- Conduct regular drills involving technology, security, operations, and executive management. [cite:71][cite:75]

### 8.4 Supply chain and lifecycle objectives

- Apply procurement security requirements to vendors, outsourced service providers, and critical software suppliers. [cite:42][cite:71][cite:31]
- Adopt SBOM for important systems and procured software where feasible. [cite:34][cite:67]
- Track remediation to closure with accountable owners and evidence. [cite:71][cite:42]
- Add secure retirement and deprecation controls using ASD guidance to close a relative local gap. [cite:2]

---

## Section 9: Implementation Roadmap

| Phase | Timeline | Focus |
|---|---|---|
| Phase 1 | Months 1–3 | Confirm CI designation scope, identify critical systems and dependencies, establish security management unit, assign senior accountability, and map existing controls to Cap. 653 + SFC + DPO. [cite:71][cite:75][cite:42] |
| Phase 2 | Months 3–6 | Implement DPO-style Security Planning, threat modeling, SDLC gates, logging baseline, privileged access controls, and incident classification workflows. [cite:42][cite:71] |
| Phase 3 | Months 6–12 | Add stronger engineering controls, procurement security, SBOM where practical, distributed-service identity, advanced resilience testing, and drill cadence. [cite:34][cite:1][cite:75] |
| Phase 4 | Ongoing | Operate audits, risk assessments, remediation tracking, post-incident lessons learned, and lifecycle/deprecation governance. [cite:71][cite:42][cite:2] |

---

## Section 10: Official Documents and Source Locations

| Source | Official location |
|---|---|
| Protection of Critical Infrastructures (Computer Systems) Ordinance | https://www.elegislation.gov.hk/hk/cap653 [cite:70] |
| Original Bill PDF | https://www.legco.gov.hk/yr2024/english/bills/b202412061.pdf [cite:71] |
| OCCICS | https://www.occics.gov.hk/en/home/index.html [cite:72] |
| SFC operational resilience material | https://www.sfc.hk/en/Welcome-to-the-Fintech-Contact-Point/Virtual-assets/Virtual-asset-trading-platforms-operators/Regulatory-r [cite:75] |
| HK GovCERT Practice Guide for Security by Design | https://www.govcert.gov.hk/doc/PG%20for%20Security%20by%20Design_EN.pdf [cite:42] |
| UK NCSC Secure Design Principles | https://www.ncsc.gov.uk/collection/cyber-security-design-principles [cite:9] |
| ASD/ACSC Secure by Design Foundations | https://www.cyber.gov.au/business-government/secure-design/secure-by-design/secure-by-design-foundations [cite:2] |
| Singapore CSA advisory | https://www.csa.gov.sg/alerts-and-advisories/advisories/ad-2023-018/ [cite:50] |
| OWASP Secure by Design Framework draft | https://owasp.org/www-project-secure-by-design-framework/ [cite:1] |
| CISA Secure by Design | https://www.cisa.gov/securebydesign [cite:31] |

---

## Section 11: Prompt to Recreate This Report in Markdown

```text
SYSTEM: You are an expert cybersecurity architect and regulatory analyst specialising in Hong Kong critical infrastructure, operational resilience, and secure-by-design frameworks.

TASK: Generate a full markdown report titled "Secure by Design Master Framework — Hong Kong Critical Infrastructure and SFC-Regulated Exchange Edition".

CONTEXT:
- The target organisation is a Hong Kong-regulated critical infrastructure operator.
- It is governed primarily by the Protection of Critical Infrastructures (Computer Systems) Ordinance (Cap. 653).
- It is also regulated by the SFC as an exchange / exchange-like entity, not a retail broker and not a bank.
- HKMA guidance should be treated as informative only.
- The document must preserve detailed history of Secure by Design, framework differences, and detailed control-level crosswalks.

MANDATORY SOURCES:
1. Cap. 653 / Bill: https://www.elegislation.gov.hk/hk/cap653 and https://www.legco.gov.hk/yr2024/english/bills/b202412061.pdf
2. OCCICS: https://www.occics.gov.hk/en/home/index.html
3. SFC resilience material for exchange/platform operators: https://www.sfc.hk/en/Welcome-to-the-Fintech-Contact-Point/Virtual-assets/Virtual-asset-trading-platforms-operators/Regulatory-r
4. HK GovCERT Practice Guide for Security by Design v1.1: https://www.govcert.gov.hk/doc/PG%20for%20Security%20by%20Design_EN.pdf
5. UK NCSC Secure Design Principles: https://www.ncsc.gov.uk/collection/cyber-security-design-principles
6. ASD/ACSC Secure by Design Foundations: https://www.cyber.gov.au/business-government/secure-design/secure-by-design/secure-by-design-foundations
7. Singapore CSA advisory: https://www.csa.gov.sg/alerts-and-advisories/advisories/ad-2023-018/
8. OWASP Secure by Design Framework draft: https://owasp.org/www-project-secure-by-design-framework/
9. CISA Secure by Design: https://www.cisa.gov/securebydesign
10. PCPD privacy-by-design material where relevant.

MANDATORY REPORT STRUCTURE:
A. Executive summary that states the priority order:
   - Tier 1: Cap. 653 / PCICSO
   - Tier 2: SFC exchange resilience / governance
   - Tier 3: GovCERT/DPO + G3/S17 + PDPO
   - Tier 4: CISA, NCSC, ASD, Singapore CSA, OWASP

B. Full history section covering:
   - Saltzer & Schroeder (1975)
   - Microsoft SDL (2004)
   - Privacy by Design (2009)
   - UK NCSC (~2017/2019)
   - CISA (2023)
   - ASD and HK GovCERT (2024)
   - Cap. 653 legislative milestone (2024–2026)
   - OWASP draft (2025)

C. Detailed explanation of how HK DPO / GovCERT differs from CISA, NCSC, ASD, Singapore CSA, and OWASP.

D. Detailed breakdown of Cap. 653 statutory obligation groups and explicit duties, mapped to Secure by Design outcomes.

E. SFC exchange-specific layer focused on:
   - governance
   - resilience objectives
   - disruption monitoring
   - response and adaptation
   - management information
   - market / platform continuity

F. Create a 10-domain master framework with detailed control crosswalk tables covering:
   1. Governance and accountability
   2. Asset / system designation and dependency mapping
   3. Security planning and architecture
   4. Threat modeling and risk assessment
   5. Identity, access, and secrets
   6. Secure engineering and assurance
   7. Supply chain and procurement security
   8. Monitoring, logging, and security operations
   9. Incident reporting, drills, and resilience response
   10. Audit, evidence, and continuous improvement

G. For each domain, show:
   - common controls across frameworks
   - HK-specific controls or stronger requirements
   - useful external enhancements

H. Add an implementation roadmap and a source-document table.

OUTPUT FORMAT:
- GitHub-Flavored Markdown
- H1/H2/H3 headings
- Extensive markdown tables
- Inline citations after factual claims
- Suitable for board briefing, control design, and regulator traceability
- Suggested filename: HK_SecureByDesign_Master_Framework_v3.md
```

---

## Section 12: Closing Position

The best Secure by Design model for this organisation is not to adopt one foreign framework wholesale. It is to build a Hong Kong compliance-first framework anchored in Cap. 653 and SFC expectations, delivered through GovCERT/DPO lifecycle discipline, and strengthened with selected controls from CISA, NCSC, ASD, Singapore CSA, and OWASP. [cite:71][cite:75][cite:42][cite:31][cite:9][cite:2][cite:50][cite:1]

That approach gives the organisation both legal traceability and modern engineering depth, which is exactly what a critical exchange operator needs. [cite:71][cite:75][cite:1]
