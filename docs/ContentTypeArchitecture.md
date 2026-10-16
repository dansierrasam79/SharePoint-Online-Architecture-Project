# Content Type Architecture

**Organization:** QualityFirst Technologies  
**Version:** 1.0 Draft  
**Author:** Daniel Chakraborty  
**Platform:** Microsoft SharePoint Online

---

# 1. Purpose

The Content Type Architecture defines the structure of business records within the QualityFirst Technologies Information Governance Platform.

The architecture enables:

- Standardized document classification
- Consistent metadata application
- Information governance
- Search optimization
- Records management
- Power Automate integration
- Future Copilot readiness

The design follows a hierarchical inheritance model to maximize reusability and consistency.

---

# 2. Content Type Hierarchy

```text
Business Record
│
├── Quality Record
│   ├── Test Plan
│   ├── Test Case
│   ├── Test Report
│   ├── Defect Analysis Report
│   ├── Quality Metrics Report
│   └── Automation Framework Document
│
├── Media Record
│   ├── Content Standard
│   ├── Editorial Guideline
│   ├── Accessibility Assessment
│   ├── Localization Review
│   └── Publishing Approval
│
├── Security Record
│   ├── Risk Assessment
│   ├── Security Policy
│   ├── Vulnerability Report
│   ├── Penetration Test Report
│   ├── Incident Report
│   └── Compliance Evidence
│
├── Conformance Record
│   ├── Certification Report
│   ├── Conformance Test Result
│   ├── Interoperability Assessment
│   ├── Standards Documentation
│   └── Approval Record
│
├── Financial Record
│   ├── Budget
│   ├── Expense Report
│   ├── Invoice
│   └── Financial Statement
│
├── HR Record
│   ├── Training Record
│   ├── Performance Review
│   ├── Recruitment Document
│   └── Policy Acknowledgement
│
└── Project Record
    ├── Project Charter
    ├── Status Report
    ├── Risk Register
    └── Lessons Learned
```

---

# 3. Enterprise Site Columns

The following Site Columns shall be inherited by all business content types.

## Core Site Columns

### Record ID

**Purpose:** Unique identifier assigned to each record.

**Examples:**

```text
QE-TR-0001
SEC-RA-0005
```

**Type:** Single Line of Text

---

### Document Type

**Purpose:** Classifies the content.

**Type:** Managed Metadata

---

### Practice Area

**Purpose:** Identifies the business function responsible for the record.

**Type:** Managed Metadata

---

### Owner

**Purpose:** Accountable individual.

**Type:** Person or Group

---

### Lifecycle Status

**Purpose:** Tracks progression through the records lifecycle.

**Type:** Choice

---

### Retention Category

**Purpose:** Defines retention requirements.

**Type:** Managed Metadata

---

### Review Date

**Purpose:** Scheduled review date.

**Type:** Date and Time

---

### Record Classification

**Purpose:** Identifies the specific record class.

**Type:** Managed Metadata

---

### Record Created Date

**Purpose:** Historical audit reference.

**Type:** Date and Time

---

### Record Owner Department

**Purpose:** Department responsible for the record.

**Type:** Managed Metadata

---

# 4. Content Type Specific Columns

## Quality Record

Additional Columns:

- Testing Type
- Application Name
- Environment
- Release Version

---

## Media Record

Additional Columns:

- Publication Channel
- Content Language
- Accessibility Level
- Publication Status

---

## Security Record

Additional Columns:

- Risk Level
- Security Domain
- Compliance Framework
- Finding Severity

---

## Conformance Record

Additional Columns:

- Standard
- Certification Body
- Compliance Status
- Protocol Version

---

## Project Record

Additional Columns:

- Project Name
- Client
- Project Status
- Project Manager

---

# 5. Column Type Standards

## Managed Metadata

Used when values must remain consistent across the enterprise.

**Examples:**

- Practice Area
- Record Classification
- Retention Category
- Document Type

---

## Choice

Used when values are finite and unlikely to change frequently.

**Examples:**

- Lifecycle Status
- Publication Status
- Compliance Status

---

## Person or Group

Used for accountability assignments.

**Examples:**

- Owner
- Project Manager
- Reviewer

---

## Date and Time

Used for lifecycle and governance requirements.

**Examples:**

- Review Date
- Effective Date
- Disposition Date

---

## Single Line of Text

Used for identifiers and short labels.

**Examples:**

- Record ID
- Application Name
- Protocol Version

---

# 7. SharePoint Implementation Sequence

## Phase 1: Create Site Columns

```text
Record ID
Document Type
Practice Area
Owner
Lifecycle Status
Retention Category
Review Date
```

---

## Phase 2: Create Term Store Structure

```text
QualityFirst Technologies
```

Create all enterprise term sets under this group.

---

## Phase 3: Create Parent Content Type

```text
Business Record
```

---

## Phase 4: Create Child Content Types

```text
Quality Record
Media Record
Security Record
Conformance Record
Project Record
```

---

## Phase 5: Create Specialized Content Types

```text
Test Plan
Risk Assessment
Certification Report
Project Charter
Accessibility Assessment
Security Policy
```

---

# 8. Future Enhancements

Potential future enhancements include:

- Microsoft Purview retention labels
- Automated content classification
- Microsoft Graph provisioning
- PnP PowerShell deployment scripts
- AI-generated metadata enrichment
- Copilot grounding optimization
- Enterprise knowledge management integration

---

## Document Status

**Status:** Draft  
**Related Documents:**

- Architecture Blueprint
- Information Architecture
- Metadata Framework
- Records Lifecycle Model
- Retention Schedule
- Permission Model

**End of Document**
