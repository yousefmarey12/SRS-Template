# Software Requirements Specification
## For {{project name}}

Version 0.1  
Prepared by {{author}}  
{{organization}}  
{{date_modified}}

## Table of Contents
<!-- TOC -->
* [1. Introduction](#1-introduction)
    * [1.1 Document Purpose](#11-document-purpose)
    * [1.2 Product Scope](#12-product-scope)
    * [1.3 Definitions, Acronyms, and Abbreviations](#13-definitions-acronyms-and-abbreviations)
    * [1.4 References](#14-references)
    * [1.5 Document Overview](#15-document-overview)
* [2. Product Overview](#2-product-overview)
    * [2.1 Product Perspective](#21-product-perspective)
    * [2.2 Product Functions](#22-product-functions)
    * [2.3 Product Constraints](#23-product-constraints)
    * [2.4 User Characteristics](#24-user-characteristics)
    * [2.5 Assumptions and Dependencies](#25-assumptions-and-dependencies)
    * [2.6 Apportioning of Requirements](#26-apportioning-of-requirements)
* [3. Requirements](#3-requirements)
    * [3.1 External Interfaces](#31-external-interfaces)
    * [3.2 Functional](#32-functional)
    * [3.3 Quality of Service](#33-quality-of-service)
    * [3.4 Compliance](#34-compliance)
    * [3.5 Design and Implementation](#35-design-and-implementation)
    * [3.6 AI/ML](#36-aiml)
* [4. Verification](#4-verification)
* [5. Appendixes](#5-appendixes)
<!-- TOC -->

## Revision History

| Name | Date | Reason For Changes | Version |
|------|------|--------------------|---------|
|      |      |                    |         |
|      |      |                    |         |

## 1. Introduction
💬 _Provides an overview of the document and orients the reader to the system being specified._

➥ Briefly summarize the SRS’s purpose, product scope, intended audience, and how the document is organized. Do not include details here; reference the relevant sections instead.

The Software Requirement Specification is aimed to support the reader to understand the product, a web application for handling real estate, in a way such that all stakeholders are in agreement with each other.
### 1.1 Document Purpose
💬 _Clarifies why this SRS exists, what it contains, and who should use it._

➥ State the purpose of the SRS in 2–4 sentences. Name the primary audiences (e.g., product, engineering, QA, security, compliance, operations) and how they use it across the software lifecycle.

💡 Tips:
- Emphasize that the SRS defines what the system must do, not how it will do it.
- Mention related documents (vision/scope, architecture, roadmap, contracts) if relevant.

The SRS is a document for specifying the needs of the product. It is used by all internal stakeholders such that an agreement of the functionality of the product can be maintained.

### 1.2 Product Scope
💬 _Defines the software product’s purpose, boundaries, and relationship to business goals._

➥ Identify the product by name and version/release. In 3–5 sentences, describe its primary purpose, key capabilities, and intended outcomes. Clearly list inclusions and exclusions when this SRS covers part of a larger system. Focus on the “what” and “why.”

💡 Tips:
- Connect capabilities to business objectives and reference a separate vision/scope document if relevant.
- Include a simple diagram if it clarifies boundaries within a larger system.

The web application is devoted to selling the founder of Najd Cafe's real estate. It handles various features such as connecting to Airbnb, advising prospective buyers of life in Cairo, and allowing authorized admins to adjust features of the website. It does not handle other services such as offering tour packages and AI chatbot usage (at least for the current version)

### 1.3 Definitions, Acronyms, and Abbreviations
➥ Help readers understand specialized terms and notation by providing a glossary of domain terms, acronyms, and abbreviations used in the SRS.

💡 Tips:
- Include terms that impact interpretation of requirements (e.g., “user,” “tenant,” “near real-time”).
- Keep entries alphabetized and consistent across the document set.

| Term | Definition                                                                                                                   |
|------|------------------------------------------------------------------------------------------------------------------------------|
| API  | Application Programming Interface - A set of definitions and protocols for building and integrating application software     |
| SRS  | Software Requirements Specification - A document that describes the intended purpose, requirements, and nature of a software |
| UI   | User Interface - The visual part of computer application through which a user interacts with a software                      |

### 1.4 References
💬 _Lists external sources that are normative or informative for this SRS._

➥ Cite standards, contracts, policies, interface specs, UX style guides, use-case docs, architectural decisions, or a vision/scope document. For each reference, include title, author/owner, version, date, and location/URL. Indicate whether each reference is normative (binding) or informative (guidance).

💡 Tips:
- Prefer stable links or repository paths over volatile URLs.

### 1.5 Document Overview
💬 _Brief guide to the structure of the SRS so readers can quickly find what they need._

➥ Summarize what each major section covers (Product Overview, Requirements, Verification, Appendixes), note any document conventions, and mention how updates and revision history are managed.

💡 Tips:
- Keep to 3–5 sentences focusing on navigation and conventions.

## 2. Product Overview
💬 _Provides background and context influencing the product’s requirements._

Given that the founder of Najd Cafe has various real estate properties, this product is devoted to renting the properties to short-term temporary tennants.

### 2.1 Product Perspective
💬 _Places the product within a larger ecosystem or lineage._

➥ Describe context and origin of the product, whether this is a new product, replacement, or member of a family. If part of a larger system, briefly explain relationships, external interfaces, and key dependencies. Include details on ownership, service level agreements (SLAs), and support models.

💡 Tips:
- Highlight upstream/downstream systems and ownership boundaries.
- A high-level context diagram may help to orient the reader.

This product is built by Yousef Marey, an independent contractor. From prototyping to deployment, the website will be owned by Yousef Marey, Mr. Nawaf Abu Anas, and Mr. Abdulrahman Nadi. After deployment, it will be owned by only Mr. Nawaf Abu Anas, and Mr. Abdulrahman Nadi. Responsibility of maintaining individual prospective tennants needs is maintained by Mr. Nawaf Abu Anas, and Mr. Abdulrahman Nadi. Maintaining technical aspects and codebase is done solely by Yousef Marey. In the instance after hand-off, other developers maintain the pre-existing codebase, then technical aspects and failures including attacks is the responsibility of the new developers. If no hand-off is made to other developeres by Mr. Nawaf Abu Anas, and Mr. Abdulrahman Nadi, then Yousef Marey is solely responsibile for technical aspects and failure.

### 2.2 Product Functions
💬 _High-level summary of what the product enables users or systems to do._

➥ Provide a concise overview of the major functional areas/features. Defer detailed behaviors, data, and edge cases to Section 3.

💡 Tips:
- 5–10 bullets are often sufficient at this level, grouping related functions logically.
- Include a top-level data flow or use case diagram if helpful.

- Integrating Airbnb state to website state such that they are the same at all times
- Admin portal for publishing articles
- Payment via Credit/Debit Card and Bank Transfer with appropriate protocols for state management
- Authorization of data
- Price Management for Reservation based on duration of stay

### 2.3 Product Constraints
💬 _Defines contextual limitations or conditions shaping design and implementation._

➥ Describe constraints such as mandated interfaces, technology stacks, regulatory obligations, QoS baselines, hardware limitations, AI/ML model families, and organizational policies.

💡 Tips:
- State constraints as verifiable "must" statements (e.g., “must use FIPS 140–3 validated crypto modules”).
- Distinguish external/internal and mandatory/preferred constraints.
- Avoid design decisions unless truly binding.

Currently, there is no commercial registration for the product which will make it harder to register with a Saudi payment gateway. With some consultation & research, there may be workarounds from Payment Gateways with STCPay or very limited payment gateways.
📝 Note:
Requirements (Section 3) defines verifiable system obligations—specific behaviors or qualities the system shall exhibit in order to satisfy limits described in this section.

### 2.4 User Characteristics
💬 _Defines the user groups and the attributes that affect requirements._

➥ Identify user classes, roles, and personas, noting expertise, access levels, frequency of use, accessibility needs, and goals.

💡 Tips:
- Define user classes by behavior, not just titles.
- Note localization and accessibility considerations that affect UI/UX requirements.

Admin User: This user (for now) is only Yousef Marey, Mr. Nawaf Abu Anas, and Mr. Abdulrahman Nadi. These have access to the admin side and user side of the website with all authorizations.
Prospective Tennant: This user has landed on our website and is navigating with our hopes of him/her renting an apartment
Paid Tenant: This tenant has paid for a booking and has a note history regarding tenant events: check-in, cancellation, damaged properties/items, etc

### 2.5 Assumptions and Dependencies
💬 _External assumed factors or conditions, as opposed to known facts, that the project relies on._

➥ List assumptions about environment, hardware, usage patterns, third-party components/services, and organizational support. List dependencies on external systems, libraries, or teams. For each, indicate potential impact if proven false.

Assumption #1: It is possible to use a payment gateway without a commercial license.

### 2.6 Apportioning of Requirements
💬 _Allocation of requirements across components or increments._

➥ Map major requirements to subsystems, services, or releases/iterations. Use a cross-reference table to show allocation and to clearly identify deferred requirements.

💡 Tips:
- Note unknown allocations explicitly and track as follow-ups.

## 3. Requirements
💬 _This section specifies **verifiable** requirements of the software product to enable design and testing._

➥ State requirements to a level of detail sufficient for design and verification. Use unique identifiers, consistent keywords (shall/should/may), and clear conditions. Describe inputs, processing in response, and outputs where applicable. Reference the relevant 2.3 Product Constraints that the requirement addresses.

📃 Template (applies to **all** requirements):
```markdown
- ID: REQ-FUNC-001
- Title: Authentication & Authorization
- Statement: As a user, I want to login/signup to my properties or admin dashboard such that no one else can see my information
- Acceptance Criteria: In no way can the user access data they are not authorized to via frontend or backend
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-002
- Title: Admin Dashboard - Create, Update, Read, and Delete (CRUD) blog posts
- Statement: As an admin, I want to CRUD blog posts from the admin dashboard such that I do not need to tell the software developer to upload blogs
- Acceptance Criteria: Once a modification is done to a blog post, it's current content is visible to all users to public
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-003
- Title: Admin Dashboard - Format blog posts
- Statement: As an admin, I want a format for blog posts with a title, description, thumbnail, etc such that there is a standard layout
- Acceptance Criteria: Every input value will correspond to the correct place (title written by admin results in blog title, description written by admin results in blog description
- Verification Method: Demonstration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-004
- Title: Admin Dashboard - Add Images to Blog (left/right) based percentage from text
- Statement: As an admin, I want to add fixed MxN side images (and captions) relative to its position in text to illustrate aspects to user
- Acceptance Criteria: Given a text that is N pixels wide and a percentage less than 100% P, the photo will be placed in the correct relative place based on percentage
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-005
- Title: Admin Dashboard - Bold / Italics option for description text
- Statement: As an admin, I want to modify particular words to be bold or italic or both for description text to emphasize a word or phrase
- Acceptance Criteria: Bold / Italics text from the admin side is seen as bold / italics in the user side
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-006
- Title: Admin Dashboard - Create, Update, Read, and Delete (CRUD) Property Listings
- Statement: As an admin, I want to CRUD property listings with regards to information about the property to convey the user the list of properties available
- Acceptance Criteria: Once a modification is done to a property list, it's current content is visible to all users to public
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-007
- Title: Admin Dashboard - Format Property Listings
- Statement: As an admin, I want a format for property listings with a title, description, thumbnail, etc such that there is a standard layout
- Acceptance Criteria: Once a modification is done to a property list, it's current content is visible to all users to public
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-008
- Title: Admin Dashboard - Emphasize M x N picture size
- Statement: As an admin, I want the portal to reject a picture that is not JPG or PNG or is not in an M x N format such that there is no distortion of the image to user
- Acceptance Criteria: A modal opens with reason explaining why picture was rejected
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-009
- Title: Admin Dashboard - List Client Information
- Statement: As an admin, I want a table that lists client information with the ability to filter and sort
- Acceptance Criteria: Filtering a client will result in only the matched filter and sorting will result in correct sorting, 0 matched clients should be handled
- Verification Method: Demonstration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-010
- Title: Admin Dashboard - Clicking on client will lead to more details
- Statement: As an admin, I want to click on a client from the list which will lead to a page with more details regarding the client
- Acceptance Criteria: All available data for the client will be displayed
- Verification Method: Demonstration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-011
- Title: Admin Dashboard - Add information regarding client
- Statement: As an admin, I want to be able to add / modify specified information regarding client such as Passport Picture and Marriage Certificates
- Acceptance Criteria: Admin cannot modify things like name and email but can only modify passport picture
- Verification Method: Demonstration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-012
- Title: Admin Dashboard - Complex Query of Client and Property
- Statement: As an admin, I want to query between client and property such as give me all clients who booked this property from Time A to Time B or other queries to get business insight
- Acceptance Criteria: Results are the same as in the database
- Verification Method: Demonstration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-013
- Title: Admin Dashboard - Manual Mark Property as Booked
- Statement: As an admin, I want the ability mark a property as booked from Time A to Time B if not paid via Visa
- Acceptance Criteria: No one can book if an admin marked the property as booked
- Verification Method: Demonstration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-014
- Title: Admin Dashboard - Complex Query of Client and Property
- Statement: As an admin, I want the ability mark a property as booked from Time A to Time B if not paid via Visa
- Acceptance Criteria: No one can book if an admin marked the property as booked
- Verification Method: Demonstration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-015
- Title: Admin Dashboard & Airbnb Integration - Provide appropiate statistics 
- Statement: As an admin, I want separate & combined statistics for Airbnb and the website on the dashboard to know how well each is doing
- Acceptance Criteria: Correct statistics are aggregated
- Verification Method: Inspection and Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-016
- Title: Admin Dashboard & Airbnb Integration - Get Client information from Airbnb
- Statement: As an admin, I want all existing clients from Airbnb to be in my database and any new client gets stored into my database
- Acceptance Criteria: Every time a new client books a property through Airbnb, they get added to the database
- Verification Method: Inspection and Test
- More Information: N/A
```

```markdown
- ID: REQ-SEC-001
- Title: Rate Limitting
- Statement: As the owners of the app, I do not want anyone to spam the system
- Acceptance Criteria: Requests are dropped if user spams
- Verification Method: Demonstration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-017
- Title: Admin Dashboard & Airbnb Integration - Syncing Booking - Creation
- Statement: As an admin, the Airbnb calandar AND our calander for a property should be marked as booked if the user booked from our website or Airbnb
- Acceptance Criteria: Booking an appointment in either website syncs the calander
- Verification Method: Inspection and Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-018
- Title: Admin Dashboard & Airbnb Integration - Syncing Booking - Updating
- Statement: As an admin, the Airbnb calandar AND our calander for a property should be in sync with dates if the user changed dates for booking from our website or Airbnb
- Acceptance Criteria: Changing dates from airbnb or website results in calander being in sync
- Verification Method: Inspection and Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-019
- Title: Admin Dashboard & Airbnb Integration - Syncing Booking - Cancellation
- Statement: As an admin, the Airbnb calandar AND our calander for a property should be in sync if the user cancelled booking
- Acceptance Criteria: Cancelling a booking from airbnb or website frees up the space
- Verification Method: Demonstration
- More Information: N/A
```


```markdown
- ID: REQ-FUNC-020
- Title: Admin Dashboard & Airbnb Integration - Syncing Booking - Cancellation
- Statement: As an admin, the Airbnb calandar AND our calander for a property should be in sync if the user cancelled booking
- Acceptance Criteria: Cancelling a booking from airbnb or website frees up the space
- Verification Method: Demonstration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-021
- Title: Admin Dashboard - Pricing Number for Specfiied amount of dates
- Statement: As an admin, I can adjust the price depending on how long the user booked for
- Acceptance Criteria: User booking different durations will get the correct price
- Verification Method: Analysis
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-022
- Title: User Page - Access to Contact
- Statement: As a user, I can contact the owners via WhatsApp or other platforms
- Acceptance Criteria: Clicking on WhatsApp leads to the WhatsApp page
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-023
- Title: User Page - Payment of Deposit via Visa or Bank Transfer
- Statement: As a user, I can pay the deposit via visa or bank transfer (owner will text me if i choose bank transfer)
- Acceptance Criteria: Once paid, booking is made on Airbnb and database
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-023
- Title: User Page - Bank Transfer
- Statement: As a user, I can pay with a bank transfer and the booking will expire after 24 hours if no payment is made
- Acceptance Criteria: After 24 hours alongside the client has not paid, the booking will expire and the account is deleted
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-024
- Title: User Page - WhatsApp Verification or Email Verification OTP
- Statement: As a user, I have to verify my account through an OTP either sent via SMS or WhatsApp
- Acceptance Criteria: Register a user has verified if verified through OTP or WhatsApp
- Verification Method: Demostration
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-025
- Title: Email & SMS Management
- Statement: As an admin, I have to make my email for REQ-FUNC-024 a "do not reply" email to avoid spam
- Acceptance Criteria: No one should be able to reply to OTP message
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-026
- Title: User Page - Upload Documents Now or Later
- Statement: As a user, I can upload Passport/ID and marriage certificate (if married) at the time of booking or later
- Acceptance Criteria: Uploading documents is optional but a note that these documents will need to be uploaded later via user portal or shown physically on arrival
- Verification Method: Test
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-027
- Title: User Portal
- Statement: As a user, I can view recent notes regarding my status as well as upload any required documents
- Acceptance Criteria: Uploading documents can be done at any time between application and deposit
- Verification Method: Inspection
- More Information: N/A
```

```markdown
- ID: REQ-FUNC-028
- Title: User Portal & Admin Portal
- Statement: As a user, if I send documents to the admin via WhatsApp, the documents will be available on both the admin portal and user portal
- Acceptance Criteria: Uploading documents can be done at any time between application and check-in
- Verification Method: Demonstration
- More Information: N/A
```


Requirement ID schema and traceability:
- ID format: REQ-[AREA]-[NNN]-[VER] (optional -[VER] if versioned), where AREA ∈ {FUNC, INT, PERF, SEC, REL, AVAIL, OBS, COMP, INST, BUILD, DIST, MAINT, REUSE, PORT, COST, DEAD, POC, CM, ML}.
- Uniqueness: IDs must be unique and immutable; changes increment -[VER] and are recorded in Revision History.
- Traceability: Each test artifact may reference the requirement ID.

💡 Tips:
- Make each requirement testable and unambiguous, using standard metrics and avoiding vague terms (e.g., “user-friendly,” “fast”).

### 3.1 External Interfaces
💬 _Specifies all external inputs and outputs, covering both required and provided interfaces._

➥ Provide interface definitions sufficient for implementation and test.

💡 Tips:
- Use interface control documents or schemas where appropriate and reference them here.

#### 3.1.1 User Interfaces
💬 _Describes how users interact with the system at a logical level._

➥ Define UI elements, flows, and standards to be followed (style guides, accessibility guidelines). Include layout constraints, common controls (e.g., help, search), keyboard shortcuts, error/empty-state behavior, and localization. Keep visual designs in a separate UI specification and reference them.

💡 Tips:
- Reference accessibility standards (e.g., WCAG) and platform-specific guidelines.
- Consider organizing into subcategories for clarity: Usability/Accessibility (inputs/outputs and dialogs to fit user abstractions, abilities, and expectations), and Convenience.

#### 3.1.2 Hardware Interfaces
💬 _Details interactions with physical devices and platforms._

➥ Specify (un)supported device types, data/control signals, electrical or mechanical characteristics if relevant, and communication protocols. Include timing, throughput, and reliability expectations.

💡 Tips:
- Reference applicable hardware specs and certification requirements.

#### 3.1.3 Software Interfaces
💬 _Defines integrations with other software components and services._

➥ List connected systems (name and version), required or provided services/APIs, data items/messages exchanged, communication styles/protocols, and limit/error/timeout semantics. Identify shared data and ownership.

💡 Tips:
- Capture versioning and backward compatibility policies.
- Define authentication/authorization expectations for each integration.

### 3.2 Functional
💬 _Specifies the externally observable behaviors and functions the software shall provide._

➥ Organize functional requirements by feature, use case, or service. For each, describe triggers/inputs, processing/logic (at a black-box level), outputs, and error conditions. For AI behaviors, define determinism bounds (e.g., temperature), refusal criteria, safety rules, and human review points.

💡 Tips:
- Include edge cases and negative scenarios for completeness.
- For AI features, include fallback behaviors and thresholds for abstention.

### 3.3 Quality of Service
💬 _Quality attributes that constrain or qualify functional behavior._

➥ Use specific metrics, ranges, and conditions.

💡 Tips:
- When a quality applies only to a subset of functions, reference the related requirement IDs.
- Provide rationale when targets cut across functions to aid trade-off decisions.

#### 3.3.1 Performance
💬 _Response time, throughput, and resource usage expectations._

➥ Specify timing relationships, peak/steady-state loads, and performance targets under expected conditions. Include measurement methods, environments, and acceptance thresholds. Note any real-time constraints.

💡 Tips:
- Include scalability targets and capacity planning assumptions.
- Consider organizing into subcategories for clarity: Time (latency, throughput, etc.) and Space (memory, storage, bandwidth, etc.).

#### 3.3.2 Security
💬 _Defines the protection of data, identities, and operations._

➥ Define authentication, authorization, data protection (in transit/at rest), auditing, and privacy requirements. Address abuse/misuse and external attacks (e.g., injection, data exfiltration, or service compromise), and include secure defaults and incident response requirements.

💡 Tips:
- Distinguish mandatory controls vs. recommended practices.
- Consider organizing into subcategories for clarity: Safety (harmful external outcomes), Confidentiality (disclose data to unauthorized parties), Privacy (private data disclosed without consent), Integrity (data modified without authorization), and Availability (authorized data or resources made available when requested).

📝 Note:
Place generic security controls here (3.3.2), and cross-reference from supported controls as necessary:
- Use 3.1 External Interfaces for interface-level validation and secure protocols.
- Use 3.4 Compliance for regulatory/contractual obligations and audit evidence.
- Use 3.6 AI/ML for model-specific runtime protections and data governance.

#### 3.3.3 Reliability
💬 _Ability to consistently perform as specified._

➥ Specify reliability metrics and techniques (e.g., MTBF, error budgets, retry/backoff, idempotency, redundancy). Define conditions under which reliability is assessed and any failover behaviors. Define graceful degradation (e.g., fallback components, cached results, AI/ML deterministic heuristics), timeout/abstain policies, and rollback to previous versions.

#### 3.3.4 Availability
💬 _System uptime and readiness to deliver service._

➥ Define availability targets, maintenance windows, and mechanisms like checkpointing, recovery, and restart. Include geographical/zone redundancy if applicable.

💡 Tips:
- Express availability in terms meaningful to users (e.g., downtime per month) and tie to SLAs/SLOs.
- Capture scale-out/in behavior affecting availability (e.g., max failover time, quorum constraints).

#### 3.3.5 Observability
💬 _Ability to understand system state and behavior in production through telemetry._

➥ Define requirements for logs, metrics, traces, and profiling: events/fields, cardinality limits, sampling, retention, and privacy/PII handling in telemetry. Specify standard labels (e.g., service, version, tenant), correlation/trace IDs propagation, and redaction policies. State SLO-aligned alert rules, dashboards, and ownership.

💡 Tips:
- Avoid maintenance-process details (keep runbooks and on-call policies in 3.5.4 Maintainability).

### 3.4 Compliance
💬 _Requirements derived to satisfy external standards, regulations, or contracts._

➥ Specify mandated formats, naming conventions, accounting procedures, provider/user rights and agreements, licensing agreements, audit tracing, records retention, and reporting. For each compliance item, reference 2.3 Product Constraints if applicable, or cite the authoritative source directly.

### 3.5 Design and Implementation
💬 _Constraints or mandates affecting how the solution is designed, deployed, and maintained._

#### 3.5.1 Installation
💬 _Ensures the software runs smoothly in its target environments._

➥ Define (un)supported platforms/environments, prerequisites, installation methods, environment configuration (e.g., env vars, secrets), and rollback/uninstall procedures.

💡 Tips:
- Detail automation expectations (e.g., IaC, installer scripts, container images).
- Keep scaling mechanics (topology, multi-region) in 3.5.3 Distribution; keep scaling targets in 3.3 QoS.

#### 3.5.2 Build and Delivery
💬 _Defines the controls for building, packaging, and delivering software artifacts to ensure integrity, traceability, and reproducibility._

➥ Define how source code is transformed into deployable artifacts and moved through environments. Describe expectations for build reproducibility, dependency management, licensing, configuration management, artifact verification, and release promotion.

💡 Tips:
- Cross-reference 3.5.1 Installation and 3.5.10 Change Management for environment setup, versioning, and release traceability.
- Avoid operational topology details (those belong in 3.5.3 Distribution).

#### 3.5.3 Distribution
💬 _Addresses geographically or organizationally distributed deployments, data, and devices._

➥ Specify deployment topologies, component and data distribution/replication approaches and scale-out runbooks, and constraints imposed by organizational or network structure.

#### 3.5.4 Maintainability
💬 _Attributes that make the software easier to modify, fix, and evolve._

➥ Define expectations for modularity, code complexity, interfaces, coding standards, developer oriented observability, documentation, software delivery performance, and technical debt management.

#### 3.5.5 Reusability
💬 _Encourages leveraging components across products or contexts when appropriate._

➥ Identify components intended for reuse and any constraints on their dependencies or technology choices. Specify modularization, API stability, packaging, and documentation to enable reuse.

#### 3.5.6 Portability
💬 _Ability to run on multiple platforms or environments with minimal changes._

➥ Specify (un)supported operating systems, hardware architectures, cloud providers, or container runtimes. Define abstraction layers, configuration policies, and externalization of environment-specific settings.

#### 3.5.7 Cost
💬 _Financial considerations or cost targets._

➥ State budgetary limits, cost-per-transaction targets, licensing constraints, or cloud spend envelopes that influence design decisions.

💡 Tips:
- Keep costs high-level unless contractually defined.
- Link to a cost model or TCO assumptions where available.
- Note variable vs. fixed cost expectations impacting scaling strategies.

#### 3.5.8 Deadline
💬 _Schedule expectations that affect scope and prioritization._

➥ Specify key milestones, delivery dates, or phases/increments. Indicate dependencies between milestones and required readiness criteria.

💡 Tips:
- Use deadlines to guide apportioning of requirements (Section 2.6).

#### 3.5.9 Proof of Concept
💬 _Validates feasibility and de-risks critical assumptions before full-scale delivery._

➥ Define the objectives, scope, success criteria, and timebox for any POCs. Describe what will be validated (technical, usability, performance) and how results will influence requirements or design.

💡 Tips:
- Keep POCs narrowly focused and measurable. Focus on validation goals, not implementation details.

#### 3.5.10 Change Management
💬 _Controls how changes are introduced and communicated._

➥ Define change categories (breaking, additive, bugfix), approval workflow, and required artifacts (changelogs, evaluation summaries, migration guides, release notes). Specify backward/forward compatibility guarantees, client communication plans, deprecation timelines, and rollout/rollback procedures.

### 3.6 AI/ML
💬 _This section defines requirements unique to systems incorporating machine learning or data-driven components at their core. These requirements complement functional, quality, and design aspects in preceding sections but address ML-specific lifecycle, data, and ethical considerations._

#### 3.6.1 Model Specification
💬 _Defines what each model is intended to do and the measurable criteria for acceptable performance._

➥ Describe model(s) purpose, scope, expected behavior, key inputs and outputs, and measurable performance objectives. Note any validation datasets, benchmarks, or versioning practices used to ensure reproducibility.

💡 Tips:
- Distinguish baseline targets from aspirational improvements and define acceptable tolerance for drift.

#### 3.6.2 Data Management
💬 _Ensures integrity, traceability, and ethical lifecycle of data used in model training, validation, and operation._

➥ Specify dataset origin, ownership, consent conditions; labeling processes and quality controls; data lineage, versioning, and reproducibility (training → validation → inference); storage, access controls, and anonymization/pseudonymization standards; handling of missing, synthetic, or augmented data.

#### 3.6.3 Guardrails
💬 _Ensure that the AI system operates safely, predictably, and within approved boundaries._

➥ Specify how the system validates inputs, filters or constrains outputs, and limits available actions to prevent harm, misuse, or unintended consequences. Include mechanisms to detect and respond to malicious inputs or unsafe operational conditions.

💡 Tips:
- Treat “guardrails” across input, output, and action layers.
- Define escalation, logging, and rollback procedures when safety constraints are triggered.
- Cross-reference 3.3.2 Security for system-level protections and 3.6.4 Ethics for normative expectations.

#### 3.6.4 Ethics
💬 _Addresses fairness, transparency, and accountability in model behavior and outcomes._

➥ Define how ethical considerations will be identified, measured, and managed throughout development and operation. Include fairness objectives, explainability expectations, and documentation or review requirements.

💡 Tips:
- Use fairness metrics appropriate to context (e.g., demographic parity, equal opportunity).
- Consider organizing into subcategories for clarity: Fairness (societal bias in outcomes), Interpretability (can inspect the model and understand outputs), and Explainability (can explain an output for a given input).
- Coordinate with 3.6.3 Guardrails for enforcement mechanisms and 3.6.5 Human-in-the-Loop for human oversight.

#### 3.6.5 Human-in-the-Loop
💬 _Specifies the role of human oversight in decisions influenced or made by machine learning models._

➥ Describe where and how human review, approval, or intervention is required. Clarify review latency or throughput expectations, escalation paths, feedback mechanisms, traceability, and auditability of human actions.

💡 Tips:
- Link to applicable roles defined in 2.4 User Characteristics.

#### 3.6.6 Model Lifecycle and Operations
💬 _Defines requirements for deploying, monitoring, retraining, and retiring models in production._

➥ Outline how models transition from development to production, how their performance and data quality are monitored, and how retraining or rollback is triggered and managed. Include expectations for versioning and archival.

## 4. Verification
💬 _Describes how each requirement will be verified to provide objective evidence of compliance._

➥ Outline verification methods (test, canary metrics, analysis, inspection, demonstration) and test evidence preferably in a matrix paralleling Section 3. Consider adding environment details, tools, and test data requirements.

| Requirement ID | Verification Method | Test/Artifact Link | Status | Evidence           |
|----------------|---------------------|--------------------|--------|--------------------|
| REQ-FUNC-001   | test                | tests/UC01.md      | Passed | reports/tuc01.html |
| REQ-SEC-003    | analysis            | threat-model.md    | WIP    |                    |

💡 Tips:
- Include both positive and negative tests and include non-functional verification (performance, security, reliability).
- Verification artifacts may be versioned and linked to CI/CD.
- For AI, reference Model Cards and track eval datasets’ versions and ensure reproducibility of results.

## 5. Appendixes
💬 _Optional supporting material that aids understanding without being normative._

➥ Include glossaries, data dictionaries, models/diagrams, sample datasets, or change-impact analyses that support the main sections. Reference rather than duplicate content when possible.

💡 Tips:
- Keep appendixes organized and referenced from the main text.
