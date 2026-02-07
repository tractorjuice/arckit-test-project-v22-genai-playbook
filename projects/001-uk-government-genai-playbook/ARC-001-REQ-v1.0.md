# Project Requirements: UK Government GenAI Playbook

> **Template Status**: Live | **Version**: 2.1.3 | **Command**: `/arckit.requirements`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-REQ-v1.0 |
| **Document Type** | Business and Technical Requirements |
| **Project** | UK Government GenAI Playbook (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-02-07 |
| **Last Modified** | 2026-02-07 |
| **Review Cycle** | Monthly |
| **Next Review Date** | 2026-03-09 |
| **Owner** | [PENDING] |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | Project Team, Architecture Team, CDDO, GDS |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-02-07 | ArcKit AI | Initial creation from `/arckit.requirements` command | [PENDING] | [PENDING] |

## Document Purpose

This document defines the comprehensive business, functional, non-functional, integration, and data requirements for the UK Government GenAI Playbook. The playbook will provide a standardised framework, guidance, reusable patterns, and tooling to enable UK Government departments to safely, responsibly, and efficiently adopt Generative AI. These requirements will drive architecture design, vendor evaluation, implementation planning, and service assessment.

---

## Executive Summary

### Business Context

The UK Government is under increasing pressure to harness the transformative potential of Generative AI to improve public services, reduce costs, and enhance civil servant productivity. However, departments face significant challenges: fragmented approaches, inconsistent governance, skills gaps, vendor lock-in risks, and the imperative to maintain public trust through responsible and transparent AI use.

Currently, individual departments are experimenting with GenAI in silos — building bespoke solutions, duplicating effort, and inconsistently addressing safety, ethics, and compliance. Without a coordinated approach, government risks wasted spend, security incidents, public trust erosion, and non-compliance with UK AI regulation, UK GDPR, the Equality Act 2010, and the Government Service Standard.

The UK Government GenAI Playbook addresses this by providing a single, authoritative, cross-government resource that codifies best practices, architecture patterns, procurement guidance, safety frameworks, and reusable components for GenAI adoption. It aligns with the AI Regulation framework, the Technology Code of Practice (TCoP), the Algorithmic Transparency Recording Standard (ATRS), and CDDO/GDS guidance.

### Objectives

- Establish a standardised, cross-government framework for safe and responsible GenAI adoption
- Reduce duplication of effort and cost by providing reusable patterns, templates, and tooling
- Accelerate departmental GenAI adoption with clear, actionable guidance from discovery through live
- Ensure compliance with UK AI regulation, UK GDPR, Equality Act 2010, ATRS, and the Government Service Standard
- Build public trust through transparency, explainability, and robust governance

### Expected Outcomes

- **50% reduction** in time-to-first-GenAI-deployment for departments following the playbook (baseline: 12 months, target: 6 months)
- **100% ATRS compliance** for all GenAI tools deployed using playbook guidance
- **Cross-government adoption** — minimum 10 departments actively using the playbook within 12 months
- **30% reduction** in duplicated GenAI infrastructure spend through shared patterns and procurement frameworks
- **Zero critical safety incidents** from GenAI systems deployed following playbook guidance in first 24 months

### Project Scope

**In Scope**:
- GenAI adoption framework covering the full lifecycle: discovery, alpha, beta, live, and retirement
- Architecture patterns and reference architectures for common GenAI use cases (RAG, summarisation, classification, chatbot, document processing)
- Safety, ethics, and responsible AI assessment frameworks
- Security patterns addressing AI-specific threats (prompt injection, data poisoning, model extraction)
- Procurement guidance for GenAI services via G-Cloud, DOS, and bespoke procurement
- Data governance and UK GDPR compliance guidance for AI data pipelines
- Monitoring, observability, and operational guidance for GenAI in production
- Skills and capability frameworks for GenAI teams
- Templates, checklists, and reusable artifacts

**Out of Scope**:
- Building or hosting a shared GenAI platform (infrastructure decisions are departmental)
- Classified (SECRET/TOP SECRET) GenAI use cases — addressed by separate MOD/intelligence frameworks
- Specific vendor product recommendations (playbook is vendor-neutral)
- Departmental-specific policy decisions (playbook provides framework, departments decide)
- Training content development (playbook references existing GDS Academy and Civil Service Learning)

---

## Stakeholders

> **Note**: No stakeholder analysis (`ARC-001-STKE-v*.md`) was found. The stakeholders below are inferred from the project context. Run `/arckit.stakeholders` to create a formal stakeholder analysis with goals, drivers, conflict analysis, and RACI matrix.

| Stakeholder | Role | Organization | Involvement Level |
|-------------|------|--------------|-------------------|
| CDDO Chief Architect | Executive Sponsor | CDDO | Decision maker |
| GDS Head of AI & Data | Product Owner | GDS | Requirements definition |
| Departmental CTOs | Key Stakeholder | Cross-government | Input and adoption |
| Departmental Enterprise Architects | Technical Stakeholder | Cross-government | Architecture alignment |
| Data Protection Officers (DPOs) | Compliance Stakeholder | Cross-government | UK GDPR compliance |
| NCSC Technical Lead | Security Stakeholder | NCSC | Security assurance |
| Government Chief Digital Officer | Strategic Sponsor | Cabinet Office | Strategic direction |
| Civil Servants (end users) | End User Representative | Cross-government | User acceptance |
| AI Ethics Advisory Board | Advisory | Independent | Ethics oversight |
| Departmental Service Owners | Operational Stakeholder | Cross-government | Service delivery |

---

## Business Requirements

### BR-001: Standardised GenAI Adoption Framework

**Description**: The playbook MUST provide a standardised, phased framework enabling UK Government departments to adopt GenAI safely and consistently, covering discovery through live service and retirement.

**Rationale**: Departments currently adopt GenAI in ad-hoc ways, leading to inconsistent safety standards, duplicated effort, and non-compliance. A standardised framework ensures consistent quality, safety, and compliance across government.

**Success Criteria**:
- Framework covers all GDS service phases: discovery, alpha, beta, live, retirement
- Each phase has clear entry/exit criteria, mandatory activities, and decision gates
- Framework is validated by at least 3 departments in a pilot
- Framework maps to Government Service Standard 14 points

**Priority**: MUST_HAVE

**Stakeholder**: CDDO Chief Architect, GDS Head of AI & Data

**Principle Alignment**: Principle 21 — Government Service Standard Alignment

---

### BR-002: Reduce Duplicated GenAI Spend Across Government

**Description**: The playbook MUST provide reusable architecture patterns, procurement frameworks, and shared component guidance to reduce duplicated GenAI infrastructure and service spend by at least 30%.

**Rationale**: Multiple departments are independently procuring similar GenAI capabilities (e.g., document summarisation, chatbots, RAG systems), leading to duplicated cloud spend, duplicated vendor management, and inconsistent pricing.

**Success Criteria**:
- At least 10 reusable architecture patterns published covering common GenAI use cases
- Procurement framework includes pre-approved G-Cloud/DOS call-off guidance for GenAI services
- Shared cost benchmarks published for common GenAI workloads (e.g., cost per 1M tokens, cost per RAG query)
- Measurable 30% reduction in duplicated spend across adopting departments within 18 months

**Priority**: MUST_HAVE

**Stakeholder**: Government Chief Digital Officer, Departmental CTOs

**Principle Alignment**: Principle 22 — Procurement and Vendor Management

---

### BR-003: Ensure Responsible AI and Public Trust

**Description**: The playbook MUST embed responsible AI principles throughout, ensuring all GenAI systems deployed following playbook guidance meet UK Government standards for fairness, transparency, accountability, and safety.

**Rationale**: Public trust in government AI is fragile. A single high-profile AI safety failure could damage trust across all government digital services. The playbook must make responsible AI the default, not an afterthought.

**Success Criteria**:
- Responsible AI assessment template included and mandatory at discovery and beta gates
- ATRS record template provided with step-by-step guidance
- Bias and fairness testing guidance included with specific tools and methods
- 100% of GenAI systems following the playbook publish an ATRS record before live deployment
- No Equality Act 2010 violations from GenAI systems using playbook guidance

**Priority**: MUST_HAVE

**Stakeholder**: AI Ethics Advisory Board, Data Protection Officers

**Principle Alignment**: Principle 1 — Responsible AI by Design, Principle 2 — Transparency and Explainability

---

### BR-004: Accelerate Departmental GenAI Capability

**Description**: The playbook MUST reduce time-to-first-GenAI-deployment for departments from an estimated 12 months to 6 months or less through actionable guidance, templates, and pre-built components.

**Rationale**: Departments with limited AI expertise face long lead times to deploy GenAI safely. Ready-to-use patterns, templates, and worked examples significantly accelerate delivery while maintaining quality.

**Success Criteria**:
- End-to-end worked examples for at least 5 common GenAI use cases
- Template library covering all mandatory governance artifacts (DPIA, ATRS, threat model, etc.)
- Skills and capability framework identifying required roles and competencies
- Pilot departments achieve first GenAI deployment within 6 months using playbook

**Priority**: MUST_HAVE

**Stakeholder**: Departmental CTOs, Departmental Enterprise Architects

**Principle Alignment**: Principle 17 — Maintainability and Evolvability

---

### BR-005: Maintain Vendor Neutrality and Avoid Lock-In

**Description**: The playbook MUST be technology and vendor-neutral, providing guidance that applies across cloud providers (AWS, Azure, GCP) and AI model providers without favouring any specific vendor.

**Rationale**: Government procurement rules require fair competition. The GenAI market is evolving rapidly, and vendor lock-in creates long-term cost and risk exposure. Departments must retain the ability to switch providers.

**Success Criteria**:
- All architecture patterns use abstraction layers enabling model provider switching
- No vendor-specific product names in mandatory guidance (vendor examples in appendices only)
- Procurement guidance explicitly addresses vendor lock-in risk assessment
- Model portability testing included as a mandatory gate

**Priority**: MUST_HAVE

**Stakeholder**: Government Chief Digital Officer, CDDO Chief Architect

**Principle Alignment**: Principle 12 — Loose Coupling and Model Portability, Principle 11 — Interoperability and Open Standards

---

### BR-006: Build Cross-Government GenAI Community

**Description**: The playbook SHOULD establish a cross-government community of practice for GenAI, enabling knowledge sharing, pattern reuse, and collective problem-solving.

**Rationale**: GenAI is a rapidly evolving field. A community of practice ensures the playbook stays current, departments share lessons learned, and government builds collective capability rather than isolated expertise.

**Success Criteria**:
- Community of practice established with representation from at least 10 departments
- Quarterly cross-government GenAI knowledge-sharing events
- Contribution model enabling departments to submit new patterns and case studies
- Playbook updated at least quarterly based on community feedback

**Priority**: SHOULD_HAVE

**Stakeholder**: GDS Head of AI & Data, Departmental CTOs

---

### BR-007: Align with UK AI Regulation and International Standards

**Description**: The playbook MUST ensure alignment with the UK's principles-based AI regulation framework, the EU AI Act (for cross-border services), and international standards (OECD AI Principles, ISO/IEC 42001).

**Rationale**: UK Government departments may operate services that cross borders or serve international users. The playbook must help departments navigate the evolving regulatory landscape.

**Success Criteria**:
- Regulatory mapping matrix linking playbook requirements to UK AI Regulation, EU AI Act risk tiers, and OECD principles
- Risk classification guidance for GenAI systems aligned with regulatory risk tiers
- Compliance checklist for each regulatory framework
- Annual regulatory horizon scan and playbook update process

**Priority**: MUST_HAVE

**Stakeholder**: Compliance Officers, CDDO Chief Architect

**Principle Alignment**: Principle 3 — Data Sovereignty and UK Regulatory Compliance

---

## Functional Requirements

### User Personas

#### Persona 1: Departmental Enterprise Architect
- **Role**: Enterprise Architect in a UK Government department
- **Goals**: Design GenAI solutions that align with cross-government standards, pass architecture reviews, and meet service assessment criteria
- **Pain Points**: Lack of GenAI-specific architecture patterns, unclear security requirements for AI, no reusable reference architectures
- **Technical Proficiency**: High

#### Persona 2: Departmental Product Owner
- **Role**: Product Owner or Service Owner responsible for a GenAI-enabled service
- **Goals**: Deliver a GenAI-powered service that passes GDS service assessment, meets user needs, and is operationally sustainable
- **Pain Points**: Unclear governance requirements for AI, difficulty assessing AI risks, no standard templates for ATRS/DPIA
- **Technical Proficiency**: Medium

#### Persona 3: Departmental Data Scientist / AI Engineer
- **Role**: Technical practitioner building and deploying GenAI solutions
- **Goals**: Build production-ready GenAI systems with appropriate safety, security, and monitoring
- **Pain Points**: No clear patterns for prompt engineering at scale, unclear production readiness standards, no guidance on model evaluation and testing
- **Technical Proficiency**: High

#### Persona 4: Senior Responsible Owner (SRO)
- **Role**: Senior civil servant accountable for GenAI programme governance
- **Goals**: Ensure GenAI investments deliver value, manage risk, and maintain public trust
- **Pain Points**: Difficulty understanding AI risks, no standard governance framework, unclear accountability model
- **Technical Proficiency**: Low

#### Persona 5: Departmental CISO / Security Lead
- **Role**: Security leader responsible for assuring GenAI deployments
- **Goals**: Ensure GenAI systems meet security standards and address AI-specific threat vectors
- **Pain Points**: Traditional security assessments don't cover AI threats, lack of AI red-teaming guidance, unclear prompt injection mitigations
- **Technical Proficiency**: High

---

### Use Cases

#### UC-001: Department Discovers GenAI Opportunity

**Actor**: Departmental Product Owner

**Preconditions**:
- Department has identified a potential GenAI use case
- Product Owner has access to the GenAI Playbook

**Main Flow**:
1. Product Owner accesses the playbook's use case assessment tool
2. System presents a structured questionnaire to evaluate GenAI suitability
3. Product Owner provides use case details (problem statement, users, data, outcomes)
4. System returns a suitability assessment with risk classification and recommended approach
5. Product Owner reviews recommended patterns and reference architectures for the use case
6. System generates a pre-populated discovery brief with mandatory governance activities

**Postconditions**:
- Use case assessed for GenAI suitability with documented rationale
- Risk classification assigned (low/medium/high per UK AI Regulation tiers)
- Discovery brief generated with playbook-aligned activities

**Alternative Flows**:
- **Alt 1a**: If use case is not suitable for GenAI, system recommends alternative approaches
- **Alt 2a**: If use case is high-risk, system flags additional governance requirements (ethics board review, ministerial approval)

**Priority**: CRITICAL

---

#### UC-002: Architect Designs GenAI Solution

**Actor**: Departmental Enterprise Architect

**Preconditions**:
- Discovery phase completed
- Use case approved with risk classification

**Main Flow**:
1. Architect selects the relevant GenAI pattern (RAG, summarisation, chatbot, classification, etc.)
2. System presents reference architecture with component descriptions and decision points
3. Architect customises the reference architecture for their departmental context
4. System validates architecture alignment with playbook principles (automated checks)
5. Architect generates mandatory governance artifacts (threat model template, DPIA template, ATRS template)
6. System produces an architecture review pack for HLD review

**Postconditions**:
- Solution architecture documented using playbook patterns
- Governance artifacts generated from templates
- Architecture ready for review against playbook principles

**Priority**: CRITICAL

---

#### UC-003: Team Deploys GenAI to Production

**Actor**: Data Scientist / AI Engineer

**Preconditions**:
- Architecture approved
- Development and testing complete

**Main Flow**:
1. Engineer accesses the production readiness checklist
2. System presents mandatory pre-production gates (security, safety, accessibility, performance)
3. Engineer completes each gate, uploading evidence
4. System validates all mandatory gates are satisfied
5. Engineer publishes ATRS record using playbook template
6. System confirms production readiness and generates deployment authorisation request

**Postconditions**:
- All pre-production gates passed with evidence
- ATRS record published
- Deployment authorised

**Priority**: HIGH

---

### Functional Requirements Detail

#### FR-001: GenAI Use Case Assessment Tool

**Description**: The playbook MUST provide a structured assessment tool that evaluates whether a proposed use case is suitable for GenAI, classifies its risk level, and recommends an approach.

**Relates To**: BR-001, BR-003, UC-001

**Acceptance Criteria**:
- [ ] Given a user submits a use case description, when the assessment runs, then a suitability score (suitable/unsuitable/conditional) is returned with rationale
- [ ] Given a use case is assessed, when risk factors are present (citizen-facing, decision-making, personal data), then the appropriate risk tier (low/medium/high) is assigned per UK AI Regulation
- [ ] Given a high-risk use case, when assessment completes, then mandatory additional governance activities are listed (ethics board, DPIA, ministerial briefing)

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: BR-003 (responsible AI framework)

---

#### FR-002: Reference Architecture Library

**Description**: The playbook MUST provide a library of reference architectures for common GenAI patterns, including RAG, document summarisation, classification, chatbot, and content generation.

**Relates To**: BR-002, BR-004, UC-002

**Acceptance Criteria**:
- [ ] Given a user selects "RAG pattern", then a complete reference architecture is displayed with component descriptions, data flows, and decision points
- [ ] Given a reference architecture is viewed, then it includes cloud-agnostic component descriptions with vendor-specific implementation notes in appendices
- [ ] Given a reference architecture, then security controls, monitoring requirements, and scaling considerations are embedded
- [ ] At least 5 reference architectures available at launch covering: RAG, document summarisation, classification/triage, conversational AI, and content generation

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Dependencies**: FR-001 (assessment determines which pattern)

---

#### FR-003: Governance Template Library

**Description**: The playbook MUST provide a library of governance templates including DPIA, ATRS record, threat model, ethics impact assessment, service assessment evidence pack, and bias audit framework.

**Relates To**: BR-003, BR-004, UC-002, UC-003

**Acceptance Criteria**:
- [ ] Given a user needs a DPIA, then a pre-populated template is available with GenAI-specific sections (training data, model risks, automated decision-making)
- [ ] Given a user needs an ATRS record, then a step-by-step template guides them through all mandatory fields per the CDDO standard
- [ ] Given a user needs a threat model, then an AI-augmented threat model template is available covering OWASP Top 10 for LLMs
- [ ] Templates are available in editable Markdown format
- [ ] At least 10 governance templates available at launch

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

---

#### FR-004: Production Readiness Checklist

**Description**: The playbook MUST provide a mandatory production readiness checklist that validates a GenAI system meets all safety, security, performance, accessibility, and governance requirements before deployment.

**Relates To**: BR-001, BR-003, UC-003

**Acceptance Criteria**:
- [ ] Given a system is ready for production, then a checklist presents all mandatory gates grouped by category (security, safety, accessibility, performance, governance)
- [ ] Given a mandatory gate is not satisfied, then deployment is flagged as blocked with remediation guidance
- [ ] Given all gates are satisfied, then a signed-off production readiness summary is generated
- [ ] Checklist includes AI-specific gates: prompt injection testing, output filtering validation, bias audit, ATRS publication, model rollback capability

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Dependencies**: FR-003 (governance templates feed evidence)

---

#### FR-005: Security Patterns for GenAI

**Description**: The playbook MUST provide security patterns and controls specific to GenAI, addressing threats including prompt injection, data poisoning, model extraction, adversarial inputs, and PII leakage.

**Relates To**: BR-003, UC-002

**Acceptance Criteria**:
- [ ] Given an architect designs a GenAI system, then security patterns for each AI-specific threat vector are available (prompt injection, data poisoning, model extraction, adversarial inputs, PII leakage, training data extraction)
- [ ] Given a security pattern, then it includes: threat description, attack examples, mitigation controls, testing approach, and monitoring indicators
- [ ] Given a prompt injection pattern, then it covers input validation, output filtering, system prompt protection, and detection mechanisms
- [ ] All patterns aligned with OWASP Top 10 for Large Language Model Applications

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Principle Alignment**: Principle 4 — Security by Design (NON-NEGOTIABLE)

---

#### FR-006: Procurement Guidance for GenAI Services

**Description**: The playbook MUST provide procurement guidance for GenAI services including G-Cloud framework guidance, evaluation criteria, contractual safeguards, and vendor lock-in assessment.

**Relates To**: BR-002, BR-005

**Acceptance Criteria**:
- [ ] Given a department needs to procure GenAI services, then step-by-step procurement guidance is available for G-Cloud, DOS, and bespoke routes
- [ ] Given procurement guidance, then mandatory contractual clauses are provided covering: data ownership, model training restrictions, IP rights, exit strategy, sub-processor controls, and price review mechanisms
- [ ] Given a vendor evaluation, then a scoring framework is available with weighted criteria for: capability, security, data handling, lock-in risk, sustainability, and cost
- [ ] Vendor lock-in risk assessment template included

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Principle Alignment**: Principle 22 — Procurement and Vendor Management

---

#### FR-007: Data Governance for AI Pipelines

**Description**: The playbook MUST provide data governance guidance specific to GenAI, covering data classification for AI workloads, UK GDPR compliance for training/fine-tuning/RAG data, data residency, and retention.

**Relates To**: BR-003, BR-007

**Acceptance Criteria**:
- [ ] Given a department is building a RAG system, then guidance covers: data classification of knowledge base content, lawful basis for processing, data minimisation, and retention
- [ ] Given personal data is used in AI processing, then a decision tree guides the department through UK GDPR Article 6 lawful basis assessment and Article 9 special category checks
- [ ] Given data crosses borders to a model provider, then guidance covers Transfer Impact Assessment requirements and approved jurisdictions
- [ ] Data classification guidance maps Government Security Classifications to AI workload types (OFFICIAL data with commercial models, OFFICIAL-SENSITIVE with sovereign models)

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Principle Alignment**: Principle 3 — Data Sovereignty and UK Regulatory Compliance, Principle 10 — Data Sovereignty and Governance

---

#### FR-008: Monitoring and Observability Patterns

**Description**: The playbook MUST provide monitoring and observability patterns for GenAI systems in production, including AI-specific metrics (model performance, hallucination detection, cost attribution, output quality).

**Relates To**: BR-001, UC-003

**Acceptance Criteria**:
- [ ] Given a GenAI system is in production, then a monitoring pattern covers: request/response logging, latency metrics, error rates, token consumption, cost attribution per department
- [ ] Given an AI-specific monitoring need, then patterns cover: output quality scoring, hallucination detection, relevance metrics, bias drift detection, and prompt injection attempt detection
- [ ] Given a monitoring pattern, then it includes: recommended metrics, alerting thresholds, dashboard layout, and runbook references
- [ ] SLO/SLI templates provided for common GenAI service types

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Principle Alignment**: Principle 7 — Observability and Operational Excellence

---

#### FR-009: Skills and Capability Framework

**Description**: The playbook SHOULD provide a skills and capability framework identifying required roles, competencies, and training pathways for departmental GenAI teams.

**Relates To**: BR-004, BR-006

**Acceptance Criteria**:
- [ ] Given a department is building a GenAI team, then a capability framework defines required roles (AI Engineer, Prompt Engineer, AI Ethics Lead, AI Product Manager, MLOps Engineer)
- [ ] Given a role, then required competencies are listed with proficiency levels (foundational, practitioner, expert)
- [ ] Given a skills gap, then training pathways are recommended referencing GDS Academy, Civil Service Learning, and external providers
- [ ] Framework includes guidance on team structures and minimum viable team composition

**Priority**: SHOULD_HAVE

**Complexity**: MEDIUM

---

#### FR-010: Worked Examples and Case Studies

**Description**: The playbook MUST include end-to-end worked examples demonstrating how to apply playbook guidance for common GenAI use cases, from discovery through live service.

**Relates To**: BR-004

**Acceptance Criteria**:
- [ ] Given a user wants to learn by example, then at least 5 worked examples are available (RAG for policy Q&A, document summarisation for FOI, citizen chatbot, internal knowledge management, automated triage/classification)
- [ ] Given a worked example, then it includes: use case description, assessment outcome, architecture decisions, governance artifacts, code samples, testing approach, deployment, and operational monitoring
- [ ] Given a worked example, then it follows the full playbook lifecycle (discovery → alpha → beta → live)
- [ ] Code samples use open-source tooling and are cloud-agnostic

**Priority**: MUST_HAVE

**Complexity**: HIGH

---

#### FR-011: Prompt Engineering Best Practices

**Description**: The playbook MUST provide prompt engineering guidance covering system prompt design, few-shot examples, chain-of-thought reasoning, guardrails, and prompt testing.

**Relates To**: BR-004, FR-002

**Acceptance Criteria**:
- [ ] Given a practitioner is designing prompts, then guidance covers: system prompt structure, few-shot example selection, chain-of-thought techniques, and output formatting
- [ ] Given prompt security concerns, then guidance covers: system prompt protection, prompt injection resistance patterns, and output filtering
- [ ] Given prompt quality requirements, then a prompt testing framework is provided with evaluation criteria (relevance, accuracy, safety, bias)
- [ ] Prompt version management guidance included (versioning, A/B testing, rollback)

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

---

#### FR-012: Ethical AI Impact Assessment Framework

**Description**: The playbook MUST provide an ethical AI impact assessment framework that evaluates GenAI systems against fairness, bias, discrimination, and societal impact criteria.

**Relates To**: BR-003, BR-007

**Acceptance Criteria**:
- [ ] Given a GenAI system is being assessed, then a structured framework evaluates: potential for discrimination across protected characteristics (Equality Act 2010), societal impact, power imbalances, and human oversight adequacy
- [ ] Given an assessment, then it produces a risk rating and mandatory mitigations for identified issues
- [ ] Given a high-risk assessment, then escalation to an AI Ethics Advisory Board is triggered
- [ ] Framework includes guidance on ongoing bias monitoring post-deployment

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Principle Alignment**: Principle 1 — Responsible AI by Design

---

#### FR-013: Service Assessment Preparation Guide

**Description**: The playbook MUST provide guidance for preparing GenAI-enabled services for GDS Service Standard assessment, mapping AI-specific considerations to each of the 14 points.

**Relates To**: BR-001, FR-004

**Acceptance Criteria**:
- [ ] Given a service preparing for assessment, then a mapping document shows how each of the 14 Service Standard points applies to GenAI services
- [ ] Given Point 1 (Understand users), then guidance covers AI-specific user research considerations (trust, explainability, confidence in AI outputs)
- [ ] Given Point 9 (Create a secure service), then guidance covers AI-specific security threats and mitigations
- [ ] Given Point 12 (Make new source code open), then guidance covers what to open-source and what to protect (model weights, sensitive prompts, training data)

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Principle Alignment**: Principle 21 — Government Service Standard Alignment

---

#### FR-014: Model Evaluation and Selection Guide

**Description**: The playbook MUST provide guidance for evaluating and selecting GenAI models, covering capability assessment, safety testing, cost modelling, and provider comparison frameworks.

**Relates To**: BR-005, FR-002

**Acceptance Criteria**:
- [ ] Given a department needs to select a model, then an evaluation framework covers: task suitability, accuracy benchmarks, safety scores, cost per query, latency, data residency, and vendor lock-in risk
- [ ] Given a model evaluation, then standardised benchmark tests are provided for common government use cases
- [ ] Given model selection guidance, then decision trees help departments choose between: commercial API, open-source self-hosted, fine-tuned, and sovereign options
- [ ] Guidance updated at least quarterly to reflect rapidly evolving model landscape

**Priority**: MUST_HAVE

**Complexity**: HIGH

**Principle Alignment**: Principle 12 — Loose Coupling and Model Portability

---

#### FR-015: Accessibility Guidance for AI Interfaces

**Description**: The playbook MUST provide accessibility guidance specific to GenAI interfaces, ensuring AI-powered services meet WCAG 2.2 AA standards and are inclusive of all users.

**Relates To**: BR-003

**Acceptance Criteria**:
- [ ] Given a GenAI chatbot is being designed, then accessibility guidance covers: keyboard navigation, screen reader compatibility, plain language output, and alternative non-AI channels
- [ ] Given AI-generated content, then guidance covers: structuring output for accessibility, providing text alternatives for any visual AI output, and ensuring content is understandable at reading age appropriate for the audience
- [ ] Given Welsh language obligations, then guidance assesses when AI outputs must be available in Welsh (Welsh Language Act 1993)
- [ ] Accessibility testing checklist specific to AI interfaces included

**Priority**: MUST_HAVE

**Complexity**: MEDIUM

**Principle Alignment**: Principle 14 — Accessibility and Inclusivity

---

---

## Non-Functional Requirements (NFRs)

### Performance Requirements

#### NFR-P-001: Playbook Content Delivery Performance

**Requirement**: Playbook content MUST be accessible with page load times under 3 seconds for all users on standard government network connections.

- Web page load time: < 3 seconds (95th percentile)
- Search results return: < 2 seconds (95th percentile)
- Template download: < 5 seconds for any single template

**Measurement Method**: Synthetic monitoring from government network locations

**Load Conditions**:
- Peak load: 500 concurrent users across government
- Average load: 50 concurrent users
- Content volume: 500+ pages of guidance, patterns, and templates

**Priority**: HIGH

---

#### NFR-P-002: GenAI Reference Implementation Response Time

**Requirement**: Any interactive GenAI reference implementations (e.g., assessment tools, decision trees) MUST respond within acceptable latency bounds.

- Interactive tool response time: < 5 seconds (95th percentile)
- Assessment questionnaire submission: < 10 seconds for full assessment
- Template generation: < 15 seconds for complex governance artifacts

**Priority**: MEDIUM

---

### Availability and Resilience Requirements

#### NFR-A-001: Playbook Availability

**Requirement**: The playbook MUST achieve 99.9% uptime (8.76 hours maximum downtime per year) as a critical cross-government resource.

- Maximum planned downtime: 4 hours/month for maintenance (during off-peak hours)
- Maximum unplanned downtime: 1 hour per incident

**Maintenance Windows**: Weekends 02:00-06:00 GMT

**Priority**: HIGH

---

#### NFR-A-002: Disaster Recovery

**RPO (Recovery Point Objective)**: Maximum acceptable data loss = 1 hour (content updates)

**RTO (Recovery Time Objective)**: Maximum acceptable downtime = 4 hours

**Backup Requirements**:
- Backup frequency: Daily full backup, hourly incremental
- Backup retention: 90 days
- Geographic backup location: UK-based secondary location

**Priority**: HIGH

---

### Scalability Requirements

#### NFR-S-001: Cross-Government Scaling

**Requirement**: The playbook MUST support scaling to serve all UK Government departments (100+ organisations) without performance degradation.

**Growth Projections**:
- Year 1: 10 departments, 1,000 monthly active users
- Year 2: 30 departments, 5,000 monthly active users
- Year 3: 50+ departments, 10,000+ monthly active users

**Priority**: HIGH

---

#### NFR-S-002: Content Volume Scaling

**Requirement**: The playbook MUST support growing content volumes as new patterns, case studies, and guidance are added without architectural redesign.

**Data Archival Strategy**: Content versioning with historical versions retained for audit; superseded content archived but accessible

**Priority**: MEDIUM

---

### Security Requirements

#### NFR-SEC-001: Authentication and Access Control

**Requirement**: The playbook MUST support access via government SSO where applicable, with public sections accessible without authentication.

**Access Tiers**:
- **Public**: General guidance, high-level patterns (no authentication required)
- **Government**: Detailed templates, assessment tools, community forums (government SSO — GOV.UK One Login or departmental IdP)
- **Contributor**: Content creation, pattern submission, community moderation (named accounts with MFA)

**Session Management**:
- Session timeout: 30 minutes of inactivity
- Re-authentication required for: content contribution, template generation

**Priority**: HIGH

**Principle Alignment**: Principle 4 — Security by Design

---

#### NFR-SEC-002: Data Protection

**Requirement**: All data stored and processed by the playbook platform MUST comply with UK GDPR and the Data Protection Act 2018.

- No personal data stored beyond minimum necessary for authentication
- Usage analytics anonymised and aggregated
- Data residency: UK only
- Data classification: OFFICIAL

**Priority**: MUST_HAVE (CRITICAL)

**Principle Alignment**: Principle 3 — Data Sovereignty and UK Regulatory Compliance

---

#### NFR-SEC-003: Content Integrity

**Requirement**: All playbook content MUST be version-controlled with tamper-evident audit trails to ensure authoritative government guidance cannot be maliciously modified.

- All content changes tracked in version control with author attribution
- Content review and approval workflow before publication
- Cryptographic integrity verification for published guidance
- Content delivery via HTTPS with HSTS

**Priority**: HIGH

**Principle Alignment**: Principle 4 — Security by Design

---

#### NFR-SEC-004: Vulnerability Management

**Requirement**: The playbook platform MUST undergo regular security testing and maintain a vulnerability management programme.

- Dependency scanning in CI/CD pipeline
- SAST and DAST testing quarterly
- Penetration testing annually by CHECK-approved provider
- Cyber Essentials Plus certification

**Remediation SLA**:
- Critical vulnerabilities: 24 hours
- High vulnerabilities: 7 days
- Medium vulnerabilities: 30 days

**Priority**: HIGH

---

### Compliance and Regulatory Requirements

#### NFR-C-001: UK GDPR Compliance

**Applicable Regulations**: UK GDPR, Data Protection Act 2018

**Compliance Requirements**:
- [ ] Privacy notice published for any personal data processing
- [ ] Data subject rights supported (access, deletion)
- [ ] Cookie consent management for analytics
- [ ] DPIA completed for the playbook platform itself
- [ ] Data breach notification process within 72 hours

**Data Residency**: All data processed and stored within the UK

**Priority**: MUST_HAVE (CRITICAL)

---

#### NFR-C-002: Accessibility Compliance

**Requirement**: The playbook platform MUST meet WCAG 2.2 Level AA accessibility standards and comply with the Public Sector Bodies Accessibility Regulations 2018.

**Accessibility Features**:
- [ ] Keyboard navigation for all functions
- [ ] Screen reader compatibility (tested with JAWS, NVDA, VoiceOver)
- [ ] High contrast mode
- [ ] Adjustable font sizes
- [ ] Alt text for all images and diagrams
- [ ] Accessibility statement published

**Testing**: Automated accessibility testing in CI/CD + manual testing with assistive technologies

**Priority**: MUST_HAVE (CRITICAL)

**Principle Alignment**: Principle 14 — Accessibility and Inclusivity

---

#### NFR-C-003: Audit Logging

**Requirement**: Comprehensive audit trail for all content changes and administrative actions.

**Audit Log Contents**:
- Who: User identity (authenticated actions)
- What: Action performed (create, update, delete, approve, publish)
- When: Timestamp (UTC, millisecond precision)
- Where: System component / content path
- Result: Success/failure

**Log Retention**: 7 years for compliance logs

**Priority**: HIGH

---

#### NFR-C-004: Technology Code of Practice (TCoP) Compliance

**Requirement**: The playbook and its platform MUST comply with all 12 points of the Technology Code of Practice.

**Key TCoP Points**:
- [ ] Point 1: Define user needs (user research conducted)
- [ ] Point 3: Be open and use open source (open-source where possible)
- [ ] Point 4: Make use of open standards (open standards for all interfaces)
- [ ] Point 5: Use cloud first (cloud-hosted platform)
- [ ] Point 9: Integrate and adapt technology (standard APIs)
- [ ] Point 11: Make better use of data (analytics for continuous improvement)

**Priority**: MUST_HAVE

**Principle Alignment**: Principle 21 — Government Service Standard Alignment

---

### Usability Requirements

#### NFR-U-001: User Experience

**Requirement**: The playbook MUST be intuitive for users with varying technical proficiency, from SROs (low technical) to AI Engineers (high technical).

**UX Standards**:
- Consistent with GOV.UK Design System
- Mobile responsive design
- Browser support: Chrome, Firefox, Safari, Edge — last 2 versions
- Content structured by user journey and role, not by technical taxonomy

**Priority**: HIGH

---

#### NFR-U-002: Search and Navigation

**Requirement**: Users MUST be able to find relevant guidance within 3 clicks or a single search query.

**Search Requirements**:
- Full-text search across all playbook content
- Faceted filtering by: use case type, governance stage, role, risk level
- Search results ranked by relevance with highlighted snippets

**Priority**: HIGH

---

#### NFR-U-003: Welsh Language

**Requirement**: The playbook MUST assess Welsh Language Act 1993 obligations and provide Welsh language content where required.

**Scope Assessment**:
- Core guidance accessible from Wales-based government offices
- Key public-facing content translated to Welsh
- Welsh language accessibility statement

**Priority**: SHOULD_HAVE

---

### Maintainability Requirements

#### NFR-M-001: Content Management

**Requirement**: Playbook content MUST be managed in a version-controlled, peer-reviewed system enabling structured updates, review cycles, and community contributions.

**Content Management Requirements**:
- Git-based version control for all content
- Pull request workflow for content changes
- Automated validation (link checking, format validation, template compliance)
- Content freshness indicators (last reviewed date, next review date)

**Priority**: HIGH

---

#### NFR-M-002: Continuous Improvement

**Requirement**: The playbook MUST include mechanisms for continuous improvement based on usage analytics, community feedback, and evolving best practices.

**Improvement Mechanisms**:
- Usage analytics to identify most/least used sections
- Feedback mechanism on every page (helpful/not helpful + comments)
- Quarterly content review cycle
- Annual full playbook review and update
- Community contribution pipeline

**Priority**: HIGH

---

---

## Integration Requirements

### INT-001: GOV.UK Integration

**Purpose**: Publish key playbook guidance on GOV.UK for maximum discoverability across government.

**Integration Type**: Content publication pipeline

**Data Exchanged**:
- **From Playbook to GOV.UK**: Published guidance summaries, links to detailed playbook content
- **From GOV.UK to Playbook**: Analytics data on page views and user journeys

**Integration Pattern**: Publish pipeline (automated or semi-automated content export to GOV.UK publishing formats)

**Authentication**: GOV.UK publishing credentials (departmental)

**Priority**: SHOULD_HAVE

---

### INT-002: ATRS Registry Integration

**Purpose**: Enable departments to submit ATRS records generated by the playbook directly to the central ATRS registry.

**Integration Type**: API-based submission

**Data Exchanged**:
- **From Playbook to ATRS Registry**: Completed ATRS records in standard format
- **From ATRS Registry to Playbook**: Submission confirmation, publication status

**Integration Pattern**: REST API with standard government API authentication

**Authentication**: OAuth 2.0 / API key per department

**SLA**: Submission acknowledgement within 30 seconds

**Priority**: SHOULD_HAVE

---

### INT-003: G-Cloud Digital Marketplace Integration

**Purpose**: Link playbook procurement guidance to live G-Cloud service listings for GenAI-relevant services.

**Integration Type**: API-based search and linking

**Data Exchanged**:
- **From Digital Marketplace to Playbook**: Service listings, pricing, supplier details for GenAI services
- **From Playbook to Users**: Curated links to relevant G-Cloud services with playbook-aligned evaluation criteria

**Integration Pattern**: Digital Marketplace API (read-only)

**Authentication**: Public API (read-only access)

**Priority**: COULD_HAVE

---

### INT-004: Cross-Government Collaboration Platform

**Purpose**: Integrate with cross-government collaboration tools for community of practice activities (discussions, knowledge sharing, pattern submissions).

**Integration Type**: Embedded or linked collaboration

**Data Exchanged**:
- Discussion threads, pattern submissions, feedback
- User profiles (government identity)

**Integration Pattern**: SSO integration with government identity provider; embedded or linked collaboration tools

**Authentication**: Government SSO (GOV.UK One Login or departmental IdP)

**Priority**: SHOULD_HAVE

---

### INT-005: Government Single Sign-On (GOV.UK One Login)

**Purpose**: Authenticate government users accessing restricted playbook content.

**Integration Type**: Identity federation

**Data Exchanged**:
- **From GOV.UK One Login to Playbook**: Authentication tokens, user identity claims (department, role)
- **From Playbook to GOV.UK One Login**: Authentication requests

**Integration Pattern**: OIDC / SAML 2.0

**Authentication**: Government SSO federation

**SLA**: Authentication within 3 seconds

**Priority**: HIGH

---

---

## Data Requirements

### Data Entities

#### Entity 1: Playbook Content

**Description**: Structured content comprising guidance, patterns, templates, case studies, and worked examples.

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| content_id | UUID | Yes | Unique identifier | Primary key |
| title | String(255) | Yes | Content title | Not null |
| content_type | Enum | Yes | Type of content | ['guidance', 'pattern', 'template', 'case_study', 'worked_example', 'checklist'] |
| body | Markdown | Yes | Full content body | Not null |
| version | String(20) | Yes | Content version | Semantic versioning |
| status | Enum | Yes | Publication status | ['draft', 'review', 'approved', 'published', 'archived'] |
| author | String(255) | Yes | Content author | Not null |
| last_reviewed | Date | Yes | Last review date | Not null |
| next_review | Date | Yes | Next review date | Not null |
| applicable_roles | Array | No | Target user roles | From persona list |
| risk_tier | Enum | No | Applicable risk tier | ['low', 'medium', 'high', 'all'] |
| tags | Array | No | Content tags | Free-text tags |

**Data Volume**: 500+ content items at launch, growing to 2,000+ over 3 years

**Data Classification**: OFFICIAL

**Data Retention**: Active content retained indefinitely; archived content retained for 7 years

---

#### Entity 2: Governance Templates

**Description**: Reusable templates for governance artifacts (DPIA, ATRS, threat model, ethics assessment, etc.)

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| template_id | UUID | Yes | Unique identifier | Primary key |
| template_name | String(255) | Yes | Template name | Not null, unique |
| template_type | Enum | Yes | Type of template | ['dpia', 'atrs', 'threat_model', 'ethics_assessment', 'checklist', 'other'] |
| template_body | Markdown | Yes | Template content | Not null |
| version | String(20) | Yes | Template version | Semantic versioning |
| mandatory | Boolean | Yes | Whether template is mandatory | Default: false |
| applicable_phases | Array | Yes | GDS phases where applicable | ['discovery', 'alpha', 'beta', 'live'] |

**Data Volume**: 30+ templates at launch, growing to 100+

**Data Classification**: OFFICIAL

**Data Retention**: Active templates retained indefinitely; superseded versions archived for 5 years

---

#### Entity 3: Assessment Records

**Description**: Records of use case assessments, risk classifications, and production readiness checks completed by departments.

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| assessment_id | UUID | Yes | Unique identifier | Primary key |
| department | String(255) | Yes | Submitting department | Not null |
| use_case_name | String(255) | Yes | Use case description | Not null |
| assessment_type | Enum | Yes | Type of assessment | ['suitability', 'risk', 'production_readiness'] |
| risk_tier | Enum | Yes | Assigned risk tier | ['low', 'medium', 'high'] |
| result | Enum | Yes | Assessment outcome | ['suitable', 'unsuitable', 'conditional', 'passed', 'failed'] |
| evidence | JSON | No | Supporting evidence | Structured data |
| assessed_date | Timestamp | Yes | Assessment timestamp | Not null |
| assessed_by | String(255) | Yes | Assessor identity | Not null |

**Data Volume**: 100+ assessments in Year 1, growing to 1,000+ by Year 3

**Data Classification**: OFFICIAL (may contain OFFICIAL-SENSITIVE departmental information)

**Data Retention**: 7 years for audit purposes

---

#### Entity 4: Community Contributions

**Description**: Pattern submissions, case studies, feedback, and discussion threads from the cross-government community.

**Attributes**:
| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| contribution_id | UUID | Yes | Unique identifier | Primary key |
| contributor | String(255) | Yes | Contributor identity | Not null |
| department | String(255) | Yes | Contributor's department | Not null |
| contribution_type | Enum | Yes | Type of contribution | ['pattern', 'case_study', 'feedback', 'discussion', 'correction'] |
| title | String(255) | Yes | Contribution title | Not null |
| body | Markdown | Yes | Contribution content | Not null |
| status | Enum | Yes | Review status | ['submitted', 'under_review', 'approved', 'published', 'rejected'] |
| submitted_date | Timestamp | Yes | Submission timestamp | Not null |

**Data Volume**: 50+ contributions in Year 1, growing to 500+ by Year 3

**Data Classification**: OFFICIAL

**Data Retention**: Published contributions retained indefinitely; rejected contributions retained for 1 year

---

### Data Quality Requirements

**Data Accuracy**: All playbook guidance must be technically reviewed by subject matter experts before publication; factual errors must be corrected within 48 hours of identification

**Data Completeness**: Every published content item must have all mandatory fields populated; no placeholder or draft content in published state

**Data Consistency**: Cross-references between content items validated automatically; broken links detected and flagged within 24 hours

**Data Timeliness**: Content freshness monitored; any content not reviewed within its review cycle flagged as stale; quarterly content currency audit

**Data Lineage**: All content changes tracked via version control with full author attribution and change description

---

### Data Migration Requirements

**Migration Scope**: No legacy system migration required — this is a greenfield project. However, existing government AI guidance (scattered across GOV.UK, departmental intranets, and CDDO publications) should be collated and integrated.

**Migration Strategy**: Phased content ingestion — priority content (security patterns, responsible AI, procurement) in Phase 1; remaining content in Phase 2

**Data Validation**: Subject matter expert review of all migrated content before publication

---

## Constraints and Assumptions

### Technical Constraints

**TC-001**: Platform MUST be deployable on UK Government-approved cloud infrastructure (AWS, Azure, or GCP UK regions)

**TC-002**: Platform MUST use GOV.UK Design System for all user-facing interfaces

**TC-003**: All source code MUST be open source (published on GitHub) per Government Service Standard Point 12

**TC-004**: Platform MUST NOT store data classified above OFFICIAL-SENSITIVE

**TC-005**: Platform MUST comply with Government Digital Service technology standards and CDDO architectural guidelines

---

### Business Constraints

**BC-001**: Initial playbook version MUST be available within 6 months to support active departmental GenAI programmes

**BC-002**: Budget constrained to existing CDDO/GDS programme funding — no new capital expenditure for infrastructure

**BC-003**: Content development MUST leverage existing government AI expertise — no external consultancy dependency for core content

**BC-004**: Playbook MUST be usable by departments with minimal AI expertise — cannot assume specialist knowledge

---

### Assumptions

**A-001**: Departments will adopt the playbook voluntarily — there is no mandatory adoption mechanism (initially)

**A-002**: GOV.UK One Login will be available for government user authentication by the playbook launch date

**A-003**: The ATRS registry will provide an API for programmatic submission of records

**A-004**: Departments have access to cloud infrastructure capable of deploying GenAI workloads

**A-005**: The UK AI Regulation framework will remain principles-based (not prescriptive) through the playbook's initial lifecycle

**A-006**: Open-source GenAI models will continue to improve in capability, providing viable alternatives to commercial APIs for government use

**Validation Plan**: Assumptions A-001 through A-006 will be validated during the discovery phase through stakeholder interviews, technical feasibility assessments, and regulatory consultation.

---

## Success Criteria and KPIs

### Business Success Metrics

| Metric | Baseline | Target | Timeline | Measurement Method |
|--------|----------|--------|----------|-------------------|
| Departments using playbook | 0 | 10 | 12 months | Registration/analytics |
| Time-to-first-deployment | 12 months (est.) | 6 months | 18 months | Department survey |
| ATRS compliance rate | Unknown | 100% | 12 months | ATRS registry |
| Duplicated GenAI spend | Unknown | 30% reduction | 18 months | Department spend analysis |
| GenAI safety incidents | Unknown | Zero critical | 24 months | Incident reporting |

---

### Technical Success Metrics

| Metric | Target | Measurement Method |
|--------|--------|-------------------|
| Playbook availability | 99.9% | Uptime monitoring |
| Page load time (p95) | < 3 seconds | Synthetic monitoring |
| Search relevance | > 80% first-page relevance | User feedback |
| Content freshness | 100% within review cycle | Automated tracking |
| Accessibility score | 100% WCAG 2.2 AA | Automated + manual audit |

---

### User Adoption Metrics

| Metric | Target | Timeline | Measurement Method |
|--------|--------|----------|-------------------|
| Monthly active users | 1,000 | 6 months post-launch | Analytics |
| Monthly active users | 5,000 | 18 months post-launch | Analytics |
| Template downloads | 500/month | 6 months post-launch | Download tracking |
| Community contributions | 50 | 12 months post-launch | Submission tracking |
| User satisfaction (CSAT) | > 4.0/5.0 | Ongoing | User surveys |

---

## Dependencies and Risks

### Dependencies

| Dependency | Description | Owner | Target Date | Status | Impact if Delayed |
|------------|-------------|-------|-------------|--------|-------------------|
| GOV.UK One Login | SSO for government users | GDS | 2026-06 | On Track | HIGH — fallback to basic auth |
| GOV.UK Design System | UI component library | GDS | Available | Complete | LOW — already available |
| ATRS Registry API | Programmatic ATRS submission | CDDO | 2026-09 | At Risk | MEDIUM — manual submission fallback |
| Cloud hosting | UK-region cloud account | CDDO/GDS | 2026-04 | On Track | HIGH — blocks deployment |
| SME availability | Subject matter experts for content | Cross-gov | Ongoing | On Track | MEDIUM — delays content quality |

---

### Risks

| Risk ID | Description | Probability | Impact | Mitigation Strategy | Owner |
|---------|-------------|-------------|--------|---------------------|-------|
| R-001 | Low voluntary adoption by departments | MEDIUM | HIGH | Mandate adoption via CDDO guidance; demonstrate value through pilot departments; secure CTO Council endorsement | GDS Head of AI |
| R-002 | Content becomes outdated due to rapid GenAI evolution | HIGH | HIGH | Quarterly review cycle; community contribution model; dedicated content team; automated staleness alerts | Content Lead |
| R-003 | Vendor-neutral guidance perceived as too abstract/unhelpful | MEDIUM | MEDIUM | Include vendor-specific implementation appendices; worked examples with real tooling; community-contributed vendor guides | Product Owner |
| R-004 | Security guidance insufficient for novel AI attack vectors | MEDIUM | HIGH | Collaborate with NCSC on AI-specific threat intelligence; quarterly security pattern reviews; red-team testing of guidance | Security Lead |
| R-005 | Accessibility requirements delay launch | LOW | MEDIUM | Accessibility built in from start (GOV.UK Design System); automated accessibility testing in CI/CD; phased content rollout | Delivery Manager |
| R-006 | UK AI Regulation changes require major playbook revision | MEDIUM | MEDIUM | Regulatory horizon scanning; modular content structure enabling targeted updates; legal team review process | Compliance Lead |

---

## Requirement Conflicts & Resolutions

### Conflict C-001: Comprehensiveness vs Speed of Delivery

**Conflicting Requirements**:
- **Requirement A**: BR-001 — Standardised framework covering full lifecycle with comprehensive governance (complete playbook)
- **Requirement B**: BR-004 — Accelerate adoption with playbook available within 6 months (BC-001)

**Stakeholders Involved**:
- **Stakeholder A** (CDDO Chief Architect): Wants comprehensive coverage ensuring consistent standards across government
- **Stakeholder B** (Departmental CTOs): Want actionable guidance NOW — departments are already deploying GenAI without guidance

**Nature of Conflict**: A comprehensive playbook covering all use cases, risk tiers, and governance scenarios requires 12-18 months of content development. Departments cannot wait — they need guidance within 6 months.

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| **Option 1**: Full playbook in 18 months | Complete coverage; consistent quality | Departments deploy without guidance for 18 months; increased safety risk | CDDO happy; CTOs frustrated |
| **Option 2**: MVP playbook in 6 months | Immediate value; addresses urgent need | Incomplete coverage; may miss edge cases | CTOs happy; CDDO concerned |
| **Option 3**: Phased delivery (MVP in 6 months, full in 18 months) | Balance both needs; iterative improvement | Phase 1 gaps may cause inconsistency; requires clear scope management | Both partially satisfied |

**Resolution Strategy**: PHASE

**Decision**: Option 3 — Phased delivery with MVP in 6 months covering the highest-priority content (security patterns, responsible AI, RAG pattern, procurement, production readiness checklist), followed by quarterly releases expanding coverage.

**Rationale**: Active departmental GenAI programmes cannot wait 18 months. Phased delivery addresses the most critical guidance immediately while building toward comprehensive coverage. The community of practice (BR-006) will help identify priority content for subsequent releases.

**Decision Authority**: CDDO Chief Architect (with CTO Council input)

**Impact on Requirements**:
- **Modified**: BR-001 rephrased to "Phase 1 MVP covering top 5 use cases and mandatory governance; Phase 2+ expanding coverage"
- **Added**: Content prioritisation matrix as Phase 1 deliverable
- **FR-002**: Phase 1 delivers 3 reference architectures (RAG, chatbot, document processing); remaining 2+ in Phase 2

**Stakeholder Management**:
- **CDDO Chief Architect**: Accepted phased approach with commitment to comprehensive coverage by Month 18. Quarterly review gates ensure quality.
- **Departmental CTOs**: Phase 1 MVP addresses their top 3 use cases. Community contribution model enables them to share department-specific patterns immediately.

---

### Conflict C-002: Vendor Neutrality vs Actionable Guidance

**Conflicting Requirements**:
- **Requirement A**: BR-005 — Maintain strict vendor neutrality (no vendor names in guidance)
- **Requirement B**: FR-010 — Provide worked examples with real, deployable code samples

**Stakeholders Involved**:
- **Stakeholder A** (Government Chief Digital Officer): Fair competition requires vendor neutrality; cannot favour specific providers
- **Stakeholder B** (Data Scientists / AI Engineers): Generic guidance without concrete tooling is unhelpful; they need real code with real SDKs

**Nature of Conflict**: Truly vendor-neutral code examples are either abstract pseudo-code (unhelpful) or require implementing every example on every platform (unfeasible).

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| **Option 1**: Strict neutrality — abstract patterns only | Fair competition; no favouritism | Unhelpful to practitioners; low adoption | CDO happy; Engineers frustrated |
| **Option 2**: Pick one vendor per example | Concrete, deployable code | Perceived favouritism; procurement challenge | Engineers happy; CDO concerned |
| **Option 3**: Multi-vendor examples (all major providers) | Concrete AND fair | 3x content effort; maintenance burden | Both happy if feasible |
| **Option 4**: Abstraction layer with vendor-specific appendices | Core guidance neutral; implementation detail per vendor | Extra complexity; appendices may lag | Both partially satisfied |

**Resolution Strategy**: INNOVATE (Option 4 with community contribution)

**Decision**: Core playbook content is vendor-neutral using abstraction patterns. Vendor-specific implementation appendices are maintained separately, with community contributions enabling coverage of multiple providers without central team maintaining all.

**Rationale**: This satisfies procurement fairness (core guidance is neutral) while providing actionable value (vendor appendices have real code). Community contribution scales vendor coverage.

**Decision Authority**: Government Chief Digital Officer

**Impact on Requirements**:
- **Modified**: BR-005 clarified — vendor neutrality applies to core guidance; vendor-specific appendices clearly labelled as "implementation examples" not "recommendations"
- **Modified**: FR-010 restructured — worked examples have vendor-neutral architecture + vendor-specific code appendices
- **Added**: Vendor appendix contribution guidelines in community governance

---

### Conflict C-003: Open Source vs Security of Sensitive Patterns

**Conflicting Requirements**:
- **Requirement A**: TC-003 — All source code MUST be open source (Government Service Standard Point 12)
- **Requirement B**: FR-005 — Security patterns include detailed attack/defence techniques that could aid adversaries if publicly disclosed

**Stakeholders Involved**:
- **Stakeholder A** (GDS): Open source is mandatory per Service Standard
- **Stakeholder B** (NCSC): Detailed prompt injection attack patterns published openly could be used against government systems

**Nature of Conflict**: Publishing detailed adversarial attack patterns openly educates both defenders and attackers. Withholding them undermines the open-source mandate and limits defensive knowledge sharing.

**Resolution Strategy**: COMPROMISE

**Decision**: Application code and general security patterns are open source. Specific adversarial attack payloads, red-team test suites, and detailed exploitation techniques are published in a restricted-access repository available to government security teams only.

**Rationale**: Service Standard Point 12 states "Make new source code open" but also acknowledges exceptions for security-sensitive material. NCSC guidance supports restricting detailed attack information to authorised parties.

**Decision Authority**: NCSC Technical Lead (with GDS agreement)

**Impact on Requirements**:
- **Modified**: TC-003 clarified — "All source code open source EXCEPT security test payloads and detailed adversarial techniques, which are restricted to government security teams"
- **Modified**: FR-005 split into public security patterns (open) and restricted adversarial testing suite (government-only access)
- **Added**: NFR-SEC-001 access tier for "Security Practitioner" with access to restricted content

---

## Timeline and Milestones

### High-Level Milestones

| Milestone | Description | Target Date | Dependencies |
|-----------|-------------|-------------|--------------|
| Requirements Approval | Stakeholder sign-off on requirements | 2026-03-15 | This document |
| Discovery Complete | User research, content strategy, architecture design | 2026-04-30 | Requirements |
| Alpha — Phase 1 MVP | Core guidance, top 3 patterns, mandatory templates | 2026-06-30 | Discovery |
| Beta — Phase 1 | Public beta with 3 pilot departments | 2026-08-31 | Alpha |
| Live — Phase 1 MVP | Phase 1 playbook live for all government | 2026-09-30 | Beta |
| Phase 2 — Expanded Patterns | Additional patterns, case studies, community features | 2026-12-31 | Phase 1 Live |
| Phase 3 — Full Playbook | Comprehensive coverage, all use cases, mature community | 2027-06-30 | Phase 2 |

---

## Budget

### Cost Estimate

| Category | Estimated Cost | Notes |
|----------|----------------|-------|
| Content Development | £250,000 | 5 FTE content authors × 6 months (Phase 1) |
| Platform Development | £150,000 | 3 FTE developers × 6 months |
| Security Assurance | £50,000 | NCSC review, penetration testing, CHECK assessment |
| User Research | £30,000 | GDS user researchers, accessibility audit |
| Cloud Hosting (Year 1) | £20,000 | UK-region cloud hosting, CDN |
| **Total Phase 1** | **£500,000** | |

### Ongoing Operational Costs

| Category | Annual Cost | Notes |
|----------|-------------|-------|
| Cloud Hosting | £25,000/year | Scaling with adoption |
| Content Maintenance | £200,000/year | 3 FTE for content updates, community management |
| Security Maintenance | £30,000/year | Annual pen test, vulnerability management |
| **Total Annual** | **£255,000/year** | |

---

## Approval

### Requirements Review

| Reviewer | Role | Status | Date | Comments |
|----------|------|--------|------|----------|
| [PENDING] | CDDO Chief Architect | [ ] Approved | [PENDING] | |
| [PENDING] | GDS Head of AI & Data | [ ] Approved | [PENDING] | |
| [PENDING] | NCSC Technical Lead | [ ] Approved | [PENDING] | |
| [PENDING] | Data Protection Officer | [ ] Approved | [PENDING] | |
| [PENDING] | Accessibility Lead | [ ] Approved | [PENDING] | |

### Sign-Off

By signing below, stakeholders confirm that requirements are complete, understood, and approved to proceed to design phase.

| Stakeholder | Signature | Date |
|-------------|-----------|------|
| [PENDING], CDDO Chief Architect | _________ | [PENDING] |
| [PENDING], GDS Head of AI & Data | _________ | [PENDING] |

---

## Requirements Traceability Matrix

| Req ID | Requirement | Stakeholder | Principle | Priority | Phase |
|--------|-------------|-------------|-----------|----------|-------|
| BR-001 | Standardised GenAI Adoption Framework | CDDO, GDS | P21 | MUST | 1 |
| BR-002 | Reduce Duplicated GenAI Spend | CDO, CTOs | P22 | MUST | 1-2 |
| BR-003 | Ensure Responsible AI and Public Trust | Ethics Board, DPOs | P1, P2 | MUST | 1 |
| BR-004 | Accelerate Departmental GenAI Capability | CTOs, Architects | P17 | MUST | 1 |
| BR-005 | Vendor Neutrality and Avoid Lock-In | CDO, CDDO | P12, P11 | MUST | 1 |
| BR-006 | Cross-Government GenAI Community | GDS, CTOs | — | SHOULD | 2 |
| BR-007 | UK AI Regulation Alignment | Compliance, CDDO | P3 | MUST | 1 |
| FR-001 | Use Case Assessment Tool | Product Owners | P1 | MUST | 1 |
| FR-002 | Reference Architecture Library | Architects | P12 | MUST | 1 (3 patterns), 2 (remaining) |
| FR-003 | Governance Template Library | All | P1, P2, P3 | MUST | 1 |
| FR-004 | Production Readiness Checklist | Engineers, SROs | P4, P21 | MUST | 1 |
| FR-005 | Security Patterns for GenAI | CISOs, Architects | P4 | MUST | 1 |
| FR-006 | Procurement Guidance | CTOs, Procurement | P22 | MUST | 1 |
| FR-007 | Data Governance for AI | DPOs, Architects | P3, P10 | MUST | 1 |
| FR-008 | Monitoring and Observability Patterns | Engineers | P7 | MUST | 1 |
| FR-009 | Skills and Capability Framework | CTOs, HR | P17 | SHOULD | 2 |
| FR-010 | Worked Examples and Case Studies | Engineers, POs | P17 | MUST | 1-2 |
| FR-011 | Prompt Engineering Best Practices | Engineers | P4, P17 | MUST | 1 |
| FR-012 | Ethical AI Impact Assessment | Ethics Board | P1 | MUST | 1 |
| FR-013 | Service Assessment Preparation | POs, GDS | P21 | MUST | 1 |
| FR-014 | Model Evaluation and Selection | Architects, Engineers | P12 | MUST | 1 |
| FR-015 | Accessibility Guidance for AI | Accessibility Lead | P14 | MUST | 1 |
| NFR-P-001 | Content Delivery Performance | All users | P15 | HIGH | 1 |
| NFR-P-002 | Interactive Tool Response Time | All users | P15 | MEDIUM | 1 |
| NFR-A-001 | Playbook Availability 99.9% | All users | P16 | HIGH | 1 |
| NFR-A-002 | Disaster Recovery | Operations | P6 | HIGH | 1 |
| NFR-S-001 | Cross-Government Scaling | All departments | P5 | HIGH | 1 |
| NFR-SEC-001 | Authentication and Access Control | All users | P4 | HIGH | 1 |
| NFR-SEC-002 | Data Protection | DPOs | P3 | CRITICAL | 1 |
| NFR-SEC-003 | Content Integrity | Security Lead | P4 | HIGH | 1 |
| NFR-SEC-004 | Vulnerability Management | Security Lead | P4 | HIGH | 1 |
| NFR-C-001 | UK GDPR Compliance | DPOs | P3 | CRITICAL | 1 |
| NFR-C-002 | Accessibility (WCAG 2.2 AA) | Accessibility Lead | P14 | CRITICAL | 1 |
| NFR-C-003 | Audit Logging | Compliance | P7 | HIGH | 1 |
| NFR-C-004 | TCoP Compliance | CDDO | P21 | MUST | 1 |
| NFR-U-001 | User Experience (GOV.UK Design) | All users | P14 | HIGH | 1 |
| NFR-U-002 | Search and Navigation | All users | P15 | HIGH | 1 |
| NFR-M-001 | Content Management | Content team | P17 | HIGH | 1 |
| NFR-M-002 | Continuous Improvement | Product Owner | P17 | HIGH | 1 |
| INT-001 | GOV.UK Integration | GDS | P11 | SHOULD | 2 |
| INT-002 | ATRS Registry Integration | CDDO | P2, P11 | SHOULD | 2 |
| INT-003 | G-Cloud Marketplace Integration | Procurement | P22 | COULD | 3 |
| INT-004 | Collaboration Platform | Community | P11 | SHOULD | 2 |
| INT-005 | GOV.UK One Login SSO | GDS | P4 | HIGH | 1 |
| DR-001 | Playbook Content | Content team | P8, P9 | HIGH | 1 |
| DR-002 | Governance Templates | All | P8 | HIGH | 1 |
| DR-003 | Assessment Records | Departments | P3, P10 | HIGH | 1 |
| DR-004 | Community Contributions | Community | P17 | MEDIUM | 2 |

---

## Appendices

### Appendix A: Glossary

| Term | Definition |
|------|-----------|
| **ATRS** | Algorithmic Transparency Recording Standard — CDDO standard for disclosing algorithmic tools used in government |
| **CDDO** | Central Digital & Data Office — leads government digital and data strategy |
| **DPIA** | Data Protection Impact Assessment — required under UK GDPR Article 35 for high-risk processing |
| **DOS** | Digital Outcomes and Specialists — government procurement framework for digital services |
| **G-Cloud** | Government Cloud — procurement framework for cloud hosting and software services |
| **GDS** | Government Digital Service — responsible for GOV.UK and government service standards |
| **GenAI** | Generative AI — AI systems that generate text, images, code, or other content |
| **LLM** | Large Language Model — foundation model architecture used in most GenAI systems |
| **MLOps** | Machine Learning Operations — practices for deploying and managing ML/AI in production |
| **NCSC** | National Cyber Security Centre — UK's authority on cyber security |
| **RAG** | Retrieval-Augmented Generation — pattern that grounds AI outputs in authoritative data sources |
| **SRO** | Senior Responsible Owner — senior civil servant accountable for a programme |
| **TCoP** | Technology Code of Practice — 12-point code for government technology decisions |
| **WCAG** | Web Content Accessibility Guidelines — international standard for web accessibility |

### Appendix B: Reference Documents

| Document | Source | Relevance |
|----------|--------|-----------|
| ARC-000-PRIN-v1.0 | This project | 23 architecture principles governing GenAI decisions |
| UK Government AI Regulation Framework | GOV.UK | Principles-based approach to AI regulation |
| Algorithmic Transparency Recording Standard | CDDO | Mandatory disclosure standard for algorithmic tools |
| Technology Code of Practice | CDDO | 12-point code for government technology |
| Government Service Standard | GDS | 14-point standard for digital services |
| OWASP Top 10 for LLM Applications | OWASP | AI-specific security threat taxonomy |
| NCSC Secure by Design | NCSC | Security principles for digital services |
| UK GDPR / Data Protection Act 2018 | ICO | Data protection requirements |
| Equality Act 2010 | UK Parliament | Protected characteristics and accessibility |

### Appendix C: Wireframes and Mockups

[To be developed during discovery phase — will follow GOV.UK Design System patterns]

### Appendix D: Data Models

[To be developed — run `/arckit.data-model` to generate comprehensive data model from these requirements]

---

## External References

| Document | Type | Source | Key Extractions | Path |
|----------|------|--------|-----------------|------|
| ARC-000-PRIN-v1.0 | Architecture Principles | Project 000 | 23 principles — responsible AI, security, data sovereignty, accessibility, vendor management, observability, TCoP compliance | `projects/000-global/ARC-000-PRIN-v1.0.md` |

---

**Generated by**: ArcKit `/arckit.requirements` command
**Generated on**: 2026-02-07 14:30 GMT
**ArcKit Version**: 2.1.3
**Project**: UK Government GenAI Playbook (Project 001)
**AI Model**: claude-opus-4-6
**Generation Context**: Generated from architecture principles (ARC-000-PRIN-v1.0). No stakeholder analysis, risk register, or business case available — requirements inferred from project context and principles.
