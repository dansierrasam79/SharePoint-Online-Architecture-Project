# Content Type Architecture

**Organization:** QualityFirst Technologies  
**Version:** 2.0 Draft  
**Author:** Daniel Chakraborty  
**Platform:** Microsoft SharePoint Online

---

# 1. Purpose

The Content Type Architecture defines how business records are structured, classified, and managed within the QualityFirst Technologies Information Governance Platform.

Content Types provide consistency across sites, libraries, search, records management, automation, and future Copilot-enabled experiences.

The architecture is designed to:

- Standardize content classification
- Promote metadata reuse
- Improve enterprise search
- Enable records management
- Support automation workflows
- Reduce content duplication
- Improve Copilot readiness

The design follows a hierarchical inheritance model that allows common metadata and governance controls to be inherited by all business records.

---

# 2. Content Type Architecture Principles

The architecture follows these principles:

- Reuse before customization
- Metadata-driven classification
- Inheritance-based design
- Consistent governance controls
- Business-function alignment
- Search optimization
- Copilot readiness
- Scalability and extensibility

---

# 3. Content Type Hierarchy

```text
Business Record
│
├── Practice Area Record
│   │
│   ├── Quality Record
│   │   ├── Test Plan
│   │   ├── Test Case
│   │   ├── Test Report
│   │   ├── Defect Analysis Report
│   │   ├── Quality Metrics Report
│   │   └── Automation Framework Document
│   │
│   ├── Media Record
│   │   ├── Content Standard
│   │   ├── Editorial Guideline
│   │   ├── Accessibility Assessment
│   │   ├── Localization Review
│   │   └── Publishing Approval
│   │
│   ├── Security Record
│   │   ├── Risk Assessment
│   │   ├── Security Policy
│   │   ├── Vulnerability Report
│   │   ├── Penetration Test Report
│   │   ├── Incident Report
│   │   └── Compliance Evidence
│   │
│   └── Conformance Record
│       ├── Certification Report
│       ├── Conformance Test Result
│       ├── Interoperability Assessment
│       ├── Standards Documentation
│       └── Approval Record
│
├── Corporate Function Record
│   │
│   ├── Financial Record
│   │   ├── Budget
│   │   ├── Expense Report
│   │   ├── Invoice
│   │   └── Financial Statement
│   │
│   ├── HR Record
│   │   ├── Training Record
│   │   ├── Performance Review
│   │   ├── Recruitment Document
│   │   └── Policy Acknowledgement
│   │
│   └── Project Record
│       ├── Project Charter
│       ├── Status Report
│       ├── Risk Register
│       └── Lessons Learned
│
└── Governance Record
    ├── Policy
    ├── Procedure
    ├── Standard
    └── Guideline
```

---

# 4. Metadata Inheritance Model

```text
Business Record
        │
        ▼
Practice Area Record
        │
        ▼
Quality Record
        │
        ▼
Test Plan
```

Each child Content Type inherits metadata from its parent Content Type.

This approach ensures:

- Consistency
- Reduced administration effort
- Easier automation
- Improved governance

---

# 5. Enterprise Site Columns

The following Site Columns shall be inherited by all business Content Types.

## Core Metadata

### Record ID

**Purpose**

Unique identifier assigned to each record.

**Type**

Single Line of Text

**Examples**

```text
QE-TR-0001
SEC-RA-0005
```

---

### Document Type

**Purpose**

Classifies the record according to the Enterprise Taxonomy.

**Type**

Managed Metadata

**Term Set**

Document Types

---

### Record Classification

**Purpose**

Identifies the specific record category.

**Type**

Managed Metadata

**Term Set**

Record Classifications

---

### Practice Area

**Purpose**

Identifies the responsible Practice Area.

**Type**

Managed Metadata

**Term Set**

Practice Areas

---

### Corporate Function

**Purpose**

Identifies the responsible Corporate Function.

**Type**

Managed Metadata

**Term Set**

Corporate Functions

---

### Owner

**Purpose**

Identifies the accountable business owner.

**Type**

Person or Group

---

### Lifecycle Status

**Purpose**

Tracks record progression through the lifecycle.

**Type**

Managed Metadata

**Term Set**

Lifecycle Status

---

### Retention Category

**Purpose**

Defines retention requirements.

**Type**

Managed Metadata

**Term Set**

Retention Categories

---

### Review Date

**Purpose**

Identifies the next scheduled review.

**Type**

Date and Time

---

### Effective Date

**Purpose**

Date the record becomes effective.

**Type**

Date and Time

---

### Disposition Date

**Purpose**

Date disposition review becomes due.

**Type**

Date and Time

---

# 6. Specialized Metadata

## Quality Record

Additional metadata:

- Testing Type
- Application Name
- Environment
- Release Version

---

## Media Record

Additional metadata:

- Publication Channel
- Content Language
- Accessibility Level
- Publication Status

---

## Security Record

Additional metadata:

- Risk Level
- Security Domain
- Compliance Framework
- Finding Severity

---

## Conformance Record

Additional metadata:

- Standard
- Certification Body
- Compliance Status
- Protocol Version

---

## Project Record

Additional metadata:

- Project Name
- Client
- Project Status
- Project Manager

---

# 7. Relationship to Enterprise Taxonomy

This Content Type Architecture relies upon the controlled vocabulary defined in:

```text
EnterpriseTaxonomy.md
```

The Enterprise Taxonomy governs:

- Practice Areas
- Corporate Functions
- Document Types
- Record Classifications
- Lifecycle Status
- Retention Categories

No Content Type-specific vocabulary should override Enterprise Taxonomy definitions.

---

# 8. SharePoint Implementation Strategy

## Phase 1

Create:

```text
QualityFirst Core Metadata
```

Site Column Group.

---

## Phase 2

Create:

```text
Business Record
```

Parent Content Type.

---

## Phase 3

Create:

```text
Practice Area Record

Corporate Function Record

Governance Record
```

Intermediate Content Types.

---

## Phase 4

Create:

```text
Quality Record
Media Record
Security Record
Conformance Record
Financial Record
HR Record
Project Record
```

Child Content Types.

---

## Phase 5

Create specialized Content Types.

Examples:

```text
Test Plan
Risk Assessment
Certification Report
Project Charter
Security Policy
Accessibility Assessment
```

---

# 9. Future Enhancements

Potential future enhancements include:

- Microsoft Purview retention labels
- Automated content classification
- Microsoft Graph provisioning
- PnP PowerShell deployment scripts
- AI-generated metadata enrichment
- Copilot grounding optimization
- Enterprise knowledge management integration
- Managed document templates

---

# 10. Related Documents

- Architecture Blueprint
- Enterprise Taxonomy
- Information Architecture
- Metadata Framework
- Records Lifecycle Model
- Retention Schedule
- Permission Model

---

## Document Status

**Status:** Draft  
**Version:** 2.0 Draft  
**Owner:** Information Architecture Team
