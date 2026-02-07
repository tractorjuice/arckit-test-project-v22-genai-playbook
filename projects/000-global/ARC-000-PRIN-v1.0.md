# UK Government GenAI Playbook — Enterprise Architecture Principles

> **Template Status**: Live | **Version**: 1.5.0 | **Command**: `/arckit.principles`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-000-PRIN-v1.0 |
| **Document Type** | Enterprise Architecture Principles |
| **Project** | GenAI Playbook for UK Government (Project 000) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-02-07 |
| **Last Modified** | 2026-02-07 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-05-07 |
| **Owner** | [OWNER_NAME_AND_ROLE] |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | [DISTRIBUTION_LIST] |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-02-07 | ArcKit AI | Initial creation from `/arckit.principles` command | PENDING | PENDING |

---

## Executive Summary

This document establishes the architecture principles governing all technology decisions for the UK Government GenAI Playbook initiative. These principles ensure that Generative AI solutions deployed across government are safe, ethical, transparent, interoperable, accessible, and aligned with UK Government standards including the Technology Code of Practice (TCoP), the Government Service Standard, the UK AI Regulation framework, and the Central Digital & Data Office (CDDO) guidelines.

**Scope**: All GenAI-related projects, platforms, tools, and services deployed within or for UK Government departments
**Authority**: Enterprise Architecture Review Board / Senior Responsible Owner (SRO)
**Compliance**: Mandatory unless exception approved through the documented exception process

**Philosophy**: These principles are **technology-agnostic** — they describe WHAT qualities the architecture must have, not HOW to implement them with specific products. Technology selection happens during research and design phases guided by these principles.

---

## I. Strategic Principles

### 1. Responsible AI by Design

**Principle Statement**:
All GenAI systems MUST be designed, developed, and operated in accordance with responsible AI principles, ensuring fairness, transparency, accountability, and safety throughout the entire lifecycle.

**Rationale**:
UK Government has a duty of care to citizens. AI systems making or informing decisions that affect people's lives must be trustworthy, fair, and subject to appropriate human oversight. The UK Government AI Regulation framework and the Alan Turing Institute's guidance on responsible AI require proactive governance.

**Implications**:
- Conduct an AI ethics impact assessment before development begins
- Establish clear accountability chains — a named SRO for every GenAI system
- Implement human-in-the-loop or human-on-the-loop oversight for all decisions affecting citizens
- Document and publish the intended purpose, limitations, and known biases of each model
- Establish feedback mechanisms for affected users and communities
- Conduct regular bias audits and fairness assessments across protected characteristics (Equality Act 2010)

**Validation Gates**:
- [ ] AI ethics impact assessment completed
- [ ] Named SRO and accountability chain documented
- [ ] Human oversight model defined and tested
- [ ] Bias and fairness assessment conducted across protected characteristics
- [ ] Feedback and redress mechanisms operational
- [ ] Model limitations and intended use documented publicly

---

### 2. Transparency and Explainability

**Principle Statement**:
All GenAI systems MUST provide meaningful explanations of their outputs and MUST clearly disclose when citizens or users are interacting with AI-generated content.

**Rationale**:
Public trust in government depends on transparency. Citizens have a right to understand how decisions affecting them are made or influenced. The Algorithmic Transparency Recording Standard (ATRS) requires government departments to publish information about algorithmic tools used in decision-making.

**Implications**:
- Publish an ATRS record for every algorithmic tool used in service delivery
- Provide explanations appropriate to the audience (technical for reviewers, plain language for citizens)
- Clearly label AI-generated content, recommendations, and decisions
- Maintain audit trails of all inputs, outputs, and decision rationale
- Ensure explanations are available in accessible formats (WCAG 2.2 AA compliance)
- Document model provenance — training data sources, fine-tuning approaches, and version history

**Validation Gates**:
- [ ] ATRS record published on GOV.UK
- [ ] AI-generated content clearly labelled in all user interfaces
- [ ] Explanation capability tested with representative users
- [ ] Audit trail captures inputs, outputs, and rationale
- [ ] Explanations meet WCAG 2.2 AA accessibility standards

---

### 3. Data Sovereignty and UK Regulatory Compliance

**Principle Statement**:
All data processed by GenAI systems MUST comply with UK GDPR, the Data Protection Act 2018, and UK Government data residency requirements. Data MUST NOT leave approved jurisdictions without explicit legal basis and senior approval.

**Rationale**:
Government data — including citizen data — is subject to stringent UK regulatory requirements. Cross-border data transfers, particularly to AI model providers, create sovereignty, security, and compliance risks that must be explicitly managed.

**Implications**:
- Classify all data according to the Government Security Classifications (OFFICIAL, OFFICIAL-SENSITIVE, SECRET, TOP SECRET)
- Personal data processed by GenAI models MUST have a lawful basis under UK GDPR Article 6 (and Article 9 for special category data)
- Conduct a Data Protection Impact Assessment (DPIA) for all high-risk processing
- Data residency MUST comply with UK Government cloud security principles — data classified OFFICIAL and above MUST be processed within approved jurisdictions
- Ensure no training data or prompts containing sensitive government data are used to improve third-party models without explicit contractual controls
- Implement data minimisation — only process the minimum personal data necessary

**Validation Gates**:
- [ ] Data classification completed for all data flows
- [ ] Lawful basis identified for all personal data processing
- [ ] DPIA completed and signed off by Data Protection Officer
- [ ] Data residency mapped and compliant with classification requirements
- [ ] Contractual controls prevent data use for third-party model training
- [ ] Data minimisation principles applied and documented

---

### 4. Security by Design (NON-NEGOTIABLE)

**Principle Statement**:
All GenAI architectures MUST implement defence-in-depth security with zero-trust principles, aligned with the NCSC Secure by Design approach and the Government Cyber Security Strategy.

**Rationale**:
GenAI systems introduce novel attack vectors including prompt injection, data poisoning, model extraction, and adversarial inputs. Government systems must protect against both traditional and AI-specific threats.

**Zero Trust Pillars**:
1. **Identity-Based Access**: No network-based trust; every request authenticated and authorised
2. **Least Privilege**: Grant minimum necessary permissions, time-boxed where possible
3. **Encryption Everywhere**: Data encrypted in transit and at rest
4. **Continuous Verification**: Monitor, log, and analyse all access patterns

**AI-Specific Security Controls**:
- [ ] Input validation and sanitisation to mitigate prompt injection attacks
- [ ] Output filtering to prevent disclosure of sensitive data, PII leakage, or harmful content
- [ ] Rate limiting and abuse detection for all AI endpoints
- [ ] Model access controls — restrict who can query, fine-tune, or modify models
- [ ] Supply chain security for model artefacts, training data, and dependencies
- [ ] Red-teaming and adversarial testing before deployment

**Mandatory Controls**:
- [ ] Multi-factor authentication for all human access
- [ ] Service-to-service authentication (mutual TLS, signed tokens, or equivalent)
- [ ] Secrets management via secure vault (never in code or config files)
- [ ] Network segmentation with minimal trust zones
- [ ] Encryption at rest for all data stores
- [ ] Encrypted transport for all network communication
- [ ] Structured logging of all authentication/authorisation events
- [ ] Regular security testing (penetration testing, vulnerability scanning)

**Compliance Frameworks**:
- NCSC Cyber Assessment Framework (CAF)
- NIST Cybersecurity Framework
- Cyber Essentials Plus
- Government Cyber Security Strategy 2022-2030

**Exceptions**:
- NONE. Security principles are non-negotiable.
- Specific control implementations may vary with compensating controls approved by the CISO.

**Validation Gates**:
- [ ] Threat model completed including AI-specific threats
- [ ] Security controls mapped to requirements
- [ ] AI red-teaming / adversarial testing completed
- [ ] Prompt injection mitigation tested
- [ ] Incident response runbook created (including AI-specific scenarios)

---

### 5. Scalability and Elasticity

**Principle Statement**:
All GenAI systems MUST be designed to scale horizontally to meet demand, with the ability to dynamically adjust capacity based on load while maintaining cost efficiency.

**Rationale**:
Government services face variable demand patterns. GenAI workloads are computationally intensive and bursty. Systems must handle both growth and traffic spikes without manual intervention or degraded citizen experience.

**Implications**:
- Design for stateless components that can be replicated
- Avoid hard-coded limits or fixed capacity assumptions
- Plan for distributed deployment across multiple compute nodes
- Use load balancing to distribute traffic across instances
- Implement auto-scaling based on demand metrics
- Consider cost implications of elastic scaling — define budget thresholds and alerts

**Validation Gates**:
- [ ] System can scale horizontally (add more instances)
- [ ] No single points of failure that limit scaling
- [ ] Load testing demonstrates capacity growth with added resources
- [ ] Scaling metrics and triggers defined
- [ ] Cost model accounts for variable capacity with budget controls

---

### 6. Resilience and Fault Tolerance

**Principle Statement**:
All GenAI systems MUST gracefully degrade when dependencies fail and recover automatically without data loss or manual intervention.

**Rationale**:
Government services must be reliable for citizens. GenAI systems depend on external model providers, APIs, and data sources which may be unavailable. The architecture must assume failures will occur.

**Implications**:
- Implement circuit breakers for external model API dependencies
- Define fallback behaviour when AI services are unavailable (e.g., route to human, present cached response, disable AI feature gracefully)
- Use timeouts on all network calls, especially to model inference endpoints
- Retry with exponential backoff for transient failures
- Automated health checks and recovery
- Avoid cascading failures through bulkhead isolation

**Validation Gates**:
- [ ] Failure modes identified and mitigated (including model provider outages)
- [ ] Fallback behaviour defined and tested for AI service unavailability
- [ ] Recovery Time Objective (RTO) and Recovery Point Objective (RPO) defined
- [ ] Automated failover tested
- [ ] Degraded mode behaviour documented and communicated to service teams

---

### 7. Observability and Operational Excellence

**Principle Statement**:
All GenAI systems MUST emit structured telemetry (logs, metrics, traces) enabling real-time monitoring, troubleshooting, cost tracking, and model performance monitoring.

**Rationale**:
We cannot operate what we cannot observe. GenAI systems require additional observability beyond traditional applications — including model performance metrics, token usage, cost attribution, and output quality monitoring.

**Telemetry Requirements**:
- **Logging**: Structured logs with correlation IDs for all requests through the AI pipeline
- **Metrics**: Request volume, latency percentiles (p50, p95, p99), error rates, token consumption
- **Tracing**: Distributed trace context for request flows through model chains
- **Alerting**: SLO-based alerting with actionable runbooks
- **AI-Specific Metrics**: Model accuracy/relevance scores, hallucination detection rates, output quality assessments, prompt token usage, cost per request

**Log Retention**:
- **Security/audit logs**: As required by compliance (minimum 12 months, up to 7 years for regulated data)
- **Application logs**: 90 days minimum for troubleshooting
- **AI interaction logs**: Sufficient for model performance analysis and audit (minimum 12 months)
- **Metrics**: Long-term trends (minimum 2 years with aggregation)

**Validation Gates**:
- [ ] Logging, metrics, tracing instrumented for all AI pipeline components
- [ ] Dashboards and alerts configured including AI-specific metrics
- [ ] Service Level Objectives (SLOs) and Service Level Indicators (SLIs) defined
- [ ] Token usage and cost attribution tracked per department/service
- [ ] Model performance monitoring (accuracy, relevance, hallucination rate) operational
- [ ] Runbooks created for common failure scenarios including AI-specific incidents

---

## II. Data Principles

### 8. Data Quality and Fitness for Purpose

**Principle Statement**:
Data used to train, fine-tune, or ground GenAI systems MUST meet defined quality standards and be demonstrably fit for the intended purpose.

**Rationale**:
AI outputs are only as good as the data they are built on. Poor quality training or grounding data leads to inaccurate, biased, or harmful outputs. Government decisions informed by AI must be based on trustworthy data.

**Quality Standards**:
- **Completeness**: No unexpected gaps in datasets used for training or retrieval
- **Accuracy**: Validated against authoritative sources; known error rates documented
- **Currency**: Data freshness requirements defined; stale data flagged or excluded
- **Representativeness**: Training data must represent the population it will serve, including protected groups
- **Provenance**: Source and transformation history fully documented

**Validation Gates**:
- [ ] Data quality assessment completed for all training/grounding data
- [ ] Data provenance and lineage documented
- [ ] Representativeness audit conducted across protected characteristics
- [ ] Data freshness SLAs defined and monitored
- [ ] Data quality metrics tracked and reported

---

### 9. Single Source of Truth

**Principle Statement**:
Every data domain MUST have a single authoritative source. GenAI systems MUST ground their outputs in authoritative government data sources wherever possible.

**Rationale**:
Government information must be consistent and authoritative. GenAI systems that reference outdated or unofficial sources undermine public trust and create inconsistency across services.

**Implications**:
- Identify the system of record for each data domain used by GenAI
- Use Retrieval-Augmented Generation (RAG) patterns grounded in authoritative sources (GOV.UK, legislation.gov.uk, departmental registers)
- Derived/cached copies are read-only and clearly labelled as such
- Synchronisation strategy defined for all derived copies
- Avoid bidirectional synchronisation (creates split-brain scenarios)

**Validation Gates**:
- [ ] System of record identified for each data entity used by GenAI
- [ ] RAG knowledge bases sourced from authoritative government sources
- [ ] Content freshness and synchronisation frequency defined
- [ ] No bidirectional sync without conflict resolution strategy

---

### 10. Data Sovereignty and Governance

**Principle Statement**:
Data classification, residency, retention, and access controls MUST comply with UK regulatory requirements and HMG data governance policies.

**Data Classification Tiers** (Government Security Classifications):
1. **OFFICIAL**: The majority of government information — routine business
2. **OFFICIAL-SENSITIVE**: OFFICIAL data requiring additional handling controls (COMMERCIAL, PERSONAL, LOCSEN)
3. **SECRET**: Serious damage to defence, foreign relations, or public order
4. **TOP SECRET**: Exceptionally grave damage (out of scope for most GenAI systems)

**Data Residency**:
- OFFICIAL data MUST be processed in jurisdictions with UK adequacy decisions or appropriate safeguards
- OFFICIAL-SENSITIVE data SHOULD be processed within UK sovereign infrastructure where feasible
- Data sent to third-party AI model providers MUST NOT include data above OFFICIAL classification without specific NCSC-approved arrangements
- Cross-border data transfers require Transfer Impact Assessment per UK GDPR

**Data Retention**:
- Automatic deletion after defined retention period
- Legal hold process for litigation, FOI requests, or investigation
- Backup retention aligned with compliance and recovery requirements
- AI training data retention governed by the original data retention policies

**Validation Gates**:
- [ ] Data classification performed for all data stores and AI data flows
- [ ] Residency requirements mapped to infrastructure
- [ ] Retention policies configured with automated deletion
- [ ] Access controls enforce least privilege and need-to-know
- [ ] Third-party data sharing agreements reviewed and approved

---

## III. Integration Principles

### 11. Interoperability and Open Standards

**Principle Statement**:
All GenAI systems MUST expose functionality through well-defined, versioned interfaces using open standards. Direct database access across system boundaries is prohibited.

**Rationale**:
Government operates a diverse technology landscape. The Technology Code of Practice requires use of open standards. Loose coupling through standard interfaces enables independent evolution, avoids vendor lock-in, and enables cross-departmental reuse.

**Implications**:
- Use open, standardised protocols for all interfaces
- Version all interfaces with backward compatibility strategy
- Publish interface specifications (API contracts, event schemas)
- No direct database access across system boundaries
- AI model interfaces MUST use standardised request/response patterns to enable model portability
- Avoid proprietary integrations that create vendor lock-in for model providers

**Validation Gates**:
- [ ] Interface specifications published using open standards
- [ ] Versioning strategy defined with backward compatibility
- [ ] Authentication and authorisation model documented
- [ ] Model interface abstraction layer enables provider switching
- [ ] No proprietary lock-in to a single AI model provider

---

### 12. Loose Coupling and Model Portability

**Principle Statement**:
Systems MUST be loosely coupled through published interfaces. GenAI components MUST be abstracted to enable switching between model providers without redesigning the solution.

**Rationale**:
The GenAI landscape is evolving rapidly. Government must avoid deep dependency on any single model provider. Loose coupling enables independent deployment, technology diversity, team autonomy, and the ability to respond to market changes or security concerns.

**Implications**:
- Abstract model provider interfaces behind a consistent API layer
- Design prompts and chains to be model-agnostic where feasible
- Communicate through published APIs or asynchronous events
- No direct database access across system boundaries
- Each system manages its own data lifecycle
- Avoid distributed transactions across systems

**Validation Gates**:
- [ ] Model provider abstracted behind a consistent interface
- [ ] Systems communicate via APIs or events, not databases
- [ ] Deployment of one system does not require deployment of another
- [ ] Model switching tested with at least one alternative provider
- [ ] Interface changes versioned with backward compatibility

---

### 13. Asynchronous Communication

**Principle Statement**:
Systems SHOULD use asynchronous communication for non-real-time interactions and long-running AI processing tasks to improve resilience and decoupling.

**Rationale**:
GenAI inference can be slow and resource-intensive. Asynchronous patterns reduce temporal coupling, improve fault tolerance, enable better scalability, and provide better user experience for long-running operations.

**When to Use Async**:
- Batch document processing and summarisation
- Large-scale data analysis and report generation
- Non-real-time business processes triggered by AI outputs
- Integration with model providers that have variable response times

**When Synchronous is Acceptable**:
- Real-time conversational AI interactions with citizens
- Quick lookup or classification tasks with low latency requirements
- Query operations (read-only, idempotent)

**Validation Gates**:
- [ ] Async patterns used for long-running AI processing
- [ ] Message durability and delivery guarantees defined
- [ ] Event schemas versioned and published
- [ ] Dead letter queues and error handling configured
- [ ] User experience designed for async workflows (progress indicators, notifications)

---

## IV. Quality Attributes

### 14. Accessibility and Inclusivity

**Principle Statement**:
All GenAI-powered services MUST meet WCAG 2.2 AA accessibility standards and MUST be designed to be inclusive of all users, including those with disabilities, limited digital skills, or limited English proficiency.

**Rationale**:
UK Government has a legal obligation under the Equality Act 2010 and the Public Sector Bodies Accessibility Regulations 2018. AI must not create new barriers to accessing government services.

**Implications**:
- AI-generated content MUST be presented in accessible formats
- Voice and conversational AI MUST provide text alternatives
- AI systems MUST NOT assume a baseline level of digital literacy
- Provide alternative (non-AI) channels for all critical government services
- AI-generated content MUST be available in Welsh where required (Welsh Language Act 1993)
- Test with assistive technologies and users with diverse needs

**Validation Gates**:
- [ ] WCAG 2.2 AA compliance tested and verified
- [ ] Alternative non-AI service channels available
- [ ] Tested with assistive technologies (screen readers, voice control)
- [ ] User research conducted with diverse user groups including disabled users
- [ ] Welsh language obligations assessed and met where applicable

---

### 15. Performance and Efficiency

**Principle Statement**:
All GenAI systems MUST meet defined performance targets under expected load with efficient use of computational resources and responsible energy consumption.

**Rationale**:
Government services must be responsive for citizens. GenAI workloads are computationally expensive, and government has sustainability commitments (Greening Government Commitments). Performance and efficiency must be balanced.

**Performance Targets** (define for each system):
- **Response Time**: p50, p95, p99 latency targets for AI-augmented endpoints
- **Throughput**: Requests per second, documents processed per hour
- **Concurrency**: Simultaneous user/request capacity
- **Resource Efficiency**: Token usage optimisation, compute utilisation targets

**Implications**:
- Performance requirements defined before implementation
- Load testing performed before production deployment
- Optimise prompt engineering to reduce token usage and latency
- Cache frequently requested AI outputs where appropriate
- Monitor and report on energy consumption and carbon impact of AI workloads

**Validation Gates**:
- [ ] Performance requirements defined with measurable targets
- [ ] Load testing performed at expected capacity
- [ ] Performance metrics monitored in production
- [ ] Token usage and cost optimised
- [ ] Sustainability impact assessed

---

### 16. Availability and Reliability

**Principle Statement**:
All GenAI systems MUST meet defined availability targets with automated recovery and minimal data loss, with clear fallback procedures when AI services are unavailable.

**Availability Targets** (define for each system):
- **Uptime SLA**: e.g., 99.9% (43.8 min downtime/month), 99.95%, 99.99%
- **Recovery Time Objective (RTO)**: Maximum acceptable downtime
- **Recovery Point Objective (RPO)**: Maximum acceptable data loss

**High Availability Patterns**:
- Redundancy across availability zones / data centres
- Automated health checks and failover
- Active-active or active-passive configurations
- Regular disaster recovery testing
- Defined fallback to non-AI service delivery when AI is unavailable

**Validation Gates**:
- [ ] Availability SLA defined
- [ ] RTO and RPO requirements documented
- [ ] Redundancy strategy implemented
- [ ] Failover tested regularly
- [ ] Non-AI fallback procedures documented and tested

---

### 17. Maintainability and Evolvability

**Principle Statement**:
All GenAI systems MUST be designed for change, with clear separation of concerns, modular architecture, and comprehensive documentation enabling teams to evolve solutions as AI capabilities advance.

**Rationale**:
The GenAI landscape is evolving rapidly. Systems must be designed so that models, prompts, and architectures can be updated without wholesale replacement.

**Implications**:
- Modular architecture with clear boundaries between AI and non-AI components
- Prompt management as a first-class concern — versioned, tested, and reviewable
- Architecture Decision Records (ADRs) for all significant AI-related choices
- Automated testing to enable confident refactoring and model updates
- Knowledge base content managed separately from application code

**Validation Gates**:
- [ ] Architecture documentation exists and is current
- [ ] Prompt templates versioned and managed separately from application code
- [ ] Module boundaries clear with defined responsibilities
- [ ] Automated test coverage enables safe refactoring and model swapping
- [ ] ADRs document key AI architecture choices

---

## V. Development Practices

### 18. Infrastructure as Code

**Principle Statement**:
All infrastructure MUST be defined as code, version-controlled, and deployed through automated pipelines. This includes AI model deployment infrastructure, vector stores, and knowledge bases.

**Rationale**:
Manual infrastructure changes create drift, inconsistency, and undocumented state. Infrastructure as Code enables repeatability, auditability, and disaster recovery — critical for government audit requirements.

**Implications**:
- All infrastructure defined in declarative code
- Infrastructure changes go through code review
- Environments are reproducible from code
- No manual changes to production infrastructure
- AI-specific infrastructure (model endpoints, embedding stores, knowledge bases) included in IaC

**Validation Gates**:
- [ ] Infrastructure defined as code (including AI components)
- [ ] Infrastructure code version-controlled
- [ ] Automated deployment pipeline for infrastructure
- [ ] No manual infrastructure changes in production

---

### 19. Automated Testing (Including AI-Specific Testing)

**Principle Statement**:
All code changes MUST be validated through automated testing before deployment. GenAI systems MUST additionally undergo AI-specific testing including output quality, safety, and bias evaluation.

**Test Pyramid**:
- **Unit Tests**: Fast, isolated, high coverage (70-80% of tests)
- **Integration Tests**: Test component interactions including model API integration (15-20% of tests)
- **End-to-End Tests**: Critical user journeys through AI-powered features (5-10% of tests)

**AI-Specific Test Types**:
- **Output Quality Tests**: Evaluate relevance, accuracy, and coherence of AI outputs against golden datasets
- **Safety Tests**: Verify output filtering, harmful content detection, and PII leakage prevention
- **Bias Tests**: Evaluate outputs across protected characteristics for fairness
- **Adversarial Tests**: Prompt injection, jailbreak, and data extraction attempts
- **Regression Tests**: Ensure model updates or prompt changes don't degrade quality

**Validation Gates**:
- [ ] Automated tests exist and pass before merge
- [ ] Test coverage meets defined thresholds
- [ ] AI output quality evaluation automated with golden datasets
- [ ] Safety and bias tests included in CI/CD pipeline
- [ ] Adversarial testing conducted before each release

---

### 20. Continuous Integration and Deployment

**Principle Statement**:
All code changes MUST go through automated build, test, and deployment pipelines with quality gates at each stage, including AI-specific quality gates.

**Pipeline Stages**:
1. **Source Control**: All changes committed to version control
2. **Build**: Automated compilation and packaging
3. **Test**: Automated test execution (including AI-specific tests)
4. **Security Scan**: Dependency and code vulnerability scanning
5. **AI Quality Gate**: Model output quality, safety, and bias checks
6. **Deployment**: Automated deployment to environments

**Quality Gates**:
- All tests must pass (including AI quality and safety tests)
- No critical security vulnerabilities
- Code review approval required
- AI output quality score above defined threshold
- Deployment requires production readiness checklist

**Validation Gates**:
- [ ] Automated CI/CD pipeline exists
- [ ] Pipeline includes security scanning
- [ ] Pipeline includes AI-specific quality gates
- [ ] Deployment is automated and repeatable
- [ ] Rollback capability tested (including model rollback)

---

## VI. UK Government-Specific Principles

### 21. Government Service Standard Alignment

**Principle Statement**:
All GenAI-powered services MUST comply with the Government Service Standard's 14 points, including user research, accessibility, open source, and multi-channel delivery.

**Rationale**:
Government digital services must meet the Service Standard to pass service assessment. GenAI does not exempt services from these requirements — it adds additional considerations.

**Key Implications for GenAI**:
- **Point 1 (Understand users)**: Conduct user research specifically on AI interactions and user trust
- **Point 3 (Provide a joined-up experience)**: AI must complement, not fragment, the user journey
- **Point 5 (Make sure everyone can use the service)**: AI must not create accessibility barriers
- **Point 8 (Iterate and improve)**: Monitor AI performance and iterate based on evidence
- **Point 9 (Create a secure service)**: Address AI-specific security risks
- **Point 12 (Make new source code open)**: Application code should be open-source; model weights and sensitive data excluded

**Validation Gates**:
- [ ] Service assessment readiness reviewed for each of 14 points
- [ ] User research conducted on AI-specific interactions
- [ ] Open source strategy defined (what is open, what is not)
- [ ] Multi-channel delivery includes non-AI alternatives

---

### 22. Procurement and Vendor Management

**Principle Statement**:
GenAI procurement MUST follow UK Government procurement standards, ensure fair competition, avoid vendor lock-in, and include contractual safeguards for data protection, intellectual property, and service continuity.

**Rationale**:
The GenAI market is concentrated among a few large providers. Government must maintain competitive tension, protect Crown intellectual property, and ensure continuity of service.

**Implications**:
- Use Government Digital Marketplace (G-Cloud, DOS) frameworks where appropriate
- Contractual terms MUST address: data ownership, model training restrictions, IP rights, exit strategy, and sub-processor controls
- Conduct vendor assessments for security (Cyber Essentials Plus minimum), data handling, and sustainability
- Avoid contractual arrangements that create single-provider dependency
- Include price review mechanisms given the rapidly evolving GenAI market
- Ensure compliance with Cabinet Office Spend Controls for technology spend

**Validation Gates**:
- [ ] Procurement follows approved government frameworks
- [ ] Data protection and IP contractual safeguards in place
- [ ] Vendor lock-in risk assessed and mitigated
- [ ] Exit strategy and data portability defined
- [ ] Spend control approvals obtained where required

---

### 23. Sustainability and Environmental Responsibility

**Principle Statement**:
GenAI systems SHOULD be designed and operated with environmental sustainability in mind, supporting the Greening Government Commitments and Net Zero targets.

**Rationale**:
GenAI workloads are computationally intensive with significant energy consumption and carbon footprint. Government has committed to achieving Net Zero by 2050 and interim Greening Government targets.

**Implications**:
- Select compute infrastructure powered by renewable energy where available
- Optimise model selection — use the smallest effective model for each task
- Cache and reuse AI outputs to reduce redundant computation
- Monitor and report energy consumption and carbon emissions of AI workloads
- Consider the environmental cost in build vs buy decisions

**Validation Gates**:
- [ ] Energy consumption monitored for AI workloads
- [ ] Model sizing justified (not over-provisioned)
- [ ] Caching strategy reduces redundant AI computation
- [ ] Sustainability metrics included in operational reporting

---

## VII. Exception Process

### Requesting Architecture Exceptions

Principles are mandatory unless a documented exception is approved by the Enterprise Architecture Review Board.

**Valid Exception Reasons**:
- Technical constraints that prevent compliance
- Regulatory or legal requirements that conflict
- Transitional state during migration (time-bound)
- Pilot/proof-of-concept with defined end date
- Urgent operational need (ministerial priority)

**Exception Request Requirements**:
- [ ] Justification with business/technical rationale
- [ ] Alternative approach and compensating controls
- [ ] Risk assessment and mitigation plan
- [ ] Expiration date (exceptions are time-bound)
- [ ] Remediation plan to achieve compliance
- [ ] SRO sign-off

**Approval Process**:
1. Submit exception request to Enterprise Architecture team
2. Review by Architecture Review Board
3. CTO/CIO approval for exceptions to critical principles (Security, Data Sovereignty, Responsible AI)
4. Document exception in project architecture documentation
5. Regular review of exceptions (quarterly)

---

## VIII. Governance and Compliance

### Architecture Review Gates

All GenAI projects must pass architecture reviews at key milestones:

**Discovery/Alpha**:
- [ ] Architecture principles understood and applicable principles identified
- [ ] High-level approach aligns with principles
- [ ] AI ethics impact assessment initiated
- [ ] Data classification and DPIA initiated
- [ ] No obvious principle violations

**Beta/Design**:
- [ ] Detailed architecture documented
- [ ] Compliance with each applicable principle validated
- [ ] Exceptions requested and approved
- [ ] Security threat model completed (including AI-specific threats)
- [ ] ATRS record drafted
- [ ] DPIA completed

**Pre-Production**:
- [ ] Implementation matches approved architecture
- [ ] All validation gates passed
- [ ] Operational readiness verified
- [ ] AI-specific testing completed (quality, safety, bias, adversarial)
- [ ] ATRS record published
- [ ] Accessibility audit completed

### Enforcement

- Architecture reviews are **mandatory** for all GenAI projects
- Principle violations must be remediated before production deployment
- Approved exceptions are time-bound and reviewed quarterly
- Retrospective reviews for compliance on live systems (annual minimum)
- Non-compliance escalated to SRO and the Departmental Architecture Board

---

## IX. Appendix

### Principle Summary Checklist

| # | Principle | Category | Criticality | Validation |
|---|-----------|----------|-------------|------------|
| 1 | Responsible AI by Design | Strategic | CRITICAL | Ethics assessment, bias audit |
| 2 | Transparency and Explainability | Strategic | CRITICAL | ATRS record, labelling |
| 3 | Data Sovereignty and UK Compliance | Strategic | CRITICAL | DPIA, classification, residency |
| 4 | Security by Design | Strategic | CRITICAL | Threat model, red-teaming |
| 5 | Scalability and Elasticity | Strategic | HIGH | Load testing, scaling metrics |
| 6 | Resilience and Fault Tolerance | Strategic | HIGH | RTO/RPO, fallback testing |
| 7 | Observability | Strategic | HIGH | Metrics, logs, traces, AI monitoring |
| 8 | Data Quality and Fitness | Data | HIGH | Quality assessment, provenance |
| 9 | Single Source of Truth | Data | HIGH | Authoritative source mapping |
| 10 | Data Sovereignty and Governance | Data | CRITICAL | Classification, residency |
| 11 | Interoperability and Open Standards | Integration | HIGH | API specs, open standards |
| 12 | Loose Coupling and Model Portability | Integration | HIGH | Provider abstraction |
| 13 | Asynchronous Communication | Integration | MEDIUM | Async patterns |
| 14 | Accessibility and Inclusivity | Quality | CRITICAL | WCAG 2.2 AA, user research |
| 15 | Performance and Efficiency | Quality | HIGH | Load testing, token optimisation |
| 16 | Availability and Reliability | Quality | HIGH | SLA monitoring, fallback |
| 17 | Maintainability and Evolvability | Quality | MEDIUM | Documentation, ADRs |
| 18 | Infrastructure as Code | DevOps | HIGH | IaC coverage |
| 19 | Automated Testing | DevOps | HIGH | Test coverage, AI quality |
| 20 | CI/CD | DevOps | HIGH | Pipeline with AI gates |
| 21 | Service Standard Alignment | UK Gov | HIGH | 14-point assessment |
| 22 | Procurement and Vendor Management | UK Gov | HIGH | Framework compliance |
| 23 | Sustainability | UK Gov | MEDIUM | Energy monitoring |

---

## External References

| Document | Type | Source | Key Extractions | Path |
|----------|------|--------|-----------------|------|
| UK Government AI Regulation Framework | Policy | GOV.UK | Principles-based approach to AI regulation | External |
| Algorithmic Transparency Recording Standard (ATRS) | Standard | CDDO | Mandatory disclosure of algorithmic tools | External |
| Technology Code of Practice (TCoP) | Standard | CDDO | 12-point code for government technology | External |
| Government Service Standard | Standard | GDS | 14-point standard for digital services | External |
| NCSC Secure by Design | Guidance | NCSC | Security principles for digital services | External |
| Government Security Classifications | Policy | Cabinet Office | OFFICIAL / SECRET / TOP SECRET framework | External |
| UK GDPR / Data Protection Act 2018 | Legislation | ICO | Data protection requirements | External |
| Equality Act 2010 | Legislation | UK Parliament | Protected characteristics, accessibility duties | External |
| Greening Government Commitments | Policy | DEFRA | Sustainability targets for government | External |
| Government Cyber Security Strategy 2022-2030 | Strategy | Cabinet Office | Cyber security requirements | External |

---

**Generated by**: ArcKit `/arckit.principles` command
**Generated on**: 2026-02-07
**ArcKit Version**: 1.5.0
**Project**: GenAI Playbook for UK Government (Project 000)
**AI Model**: Claude Opus 4.6
