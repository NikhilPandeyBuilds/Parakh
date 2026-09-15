# 🔎 PARAKH

> **AI-powered compliance verification for packaged commodities under India's Legal Metrology regulations.**

PARAKH is an intelligent compliance-verification system designed to help identify and evaluate compliance issues in packaged commodities under the **Legal Metrology (Packaged Commodities) Rules, 2011**.

The system aims to transform packaged-commodity compliance from a largely manual verification process into a structured, technology-assisted workflow using **document/image analysis, OCR, rule-based validation, and automated compliance reporting**.

---

## 🎯 Overview

Compliance information on packaged commodities is distributed across product packaging, labels, declarations, and regulatory requirements.

Manually checking every required declaration can be:

- Time-consuming
- Error-prone
- Difficult to scale
- Dependent on human interpretation
- Difficult to maintain consistently across large volumes of products

PARAKH addresses this problem by providing a structured workflow for analysing packaged-commodity information and checking it against applicable regulatory requirements.

### Core idea

text
Product / Package
       ↓
Data Extraction
       ↓
Information Structuring
       ↓
Regulatory Rule Mapping
       ↓
Compliance Verification
       ↓
Violation / Risk Identification
       ↓
Compliance Report
🧩 The Problem

Packaged commodities sold in the Indian market are required to carry specific declarations and information prescribed by applicable Legal Metrology regulations.

A compliance reviewer may need to verify multiple attributes, including information relating to:

Product identity
Manufacturer / packer / importer information
Net quantity
MRP
Consumer-related declarations
Dates and other mandatory declarations
Required labelling information
Presentation and formatting requirements

When this verification is performed manually, the process becomes increasingly difficult as the number of products increases.

The fundamental problem

How can packaged-commodity declarations be systematically analysed and checked against applicable regulatory requirements?

PARAKH approaches this as a combination of:

Computer Vision + OCR + Structured Data Extraction + Regulatory Rule Evaluation

💡 The PARAKH Approach

PARAKH converts an unstructured package into a structured compliance assessment.

┌──────────────────────┐
│   Product Packaging  │
│   Image / Information│
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│   OCR / Extraction   │
│   Identify relevant  │
│   declarations       │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│  Data Structuring    │
│  Convert information │
│  into fields         │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Regulatory Rule      │
│ Evaluation Engine    │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Compliance Analysis  │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Report / Findings    │
└──────────────────────┘
⚙️ Core Workflow
1. 📸 Input

PARAKH receives information about a packaged commodity.

The input can represent the information that a compliance officer would normally inspect manually.

2. 🔤 Information Extraction

Relevant information is extracted from the package.

OCR and document/image analysis can be used to identify textual declarations and convert them into machine-readable information.

Example:

PACKAGE
│
├── Product Name
├── Manufacturer
├── Address
├── Net Quantity
├── MRP
├── Date Information
└── Other Declarations
3. 🧱 Structured Representation

Extracted information is converted into structured fields.

Example:

{
  "product_name": "...",
  "manufacturer": "...",
  "net_quantity": "...",
  "mrp": "...",
  "address": "...",
  "declarations": []
}

This allows the information to be evaluated systematically rather than relying only on raw OCR output.

⚖️ Regulatory Compliance Engine

The central intelligence of PARAKH is the regulatory verification layer.

The extracted product information is evaluated against the applicable compliance requirements.

Conceptually:

Extracted Product Data
          +
Applicable Regulations
          ↓
    Rule Evaluation
          ↓
 ┌───────────────────┐
 │ COMPLIANT         │
 │ PARTIALLY COMPLIANT│
 │ NON-COMPLIANT     │
 └───────────────────┘

The system can identify information that is:

Present
Missing
Potentially incorrect
Requiring further verification
🔍 Compliance Analysis

Instead of simply returning raw extracted text, PARAKH is designed to produce an interpretable compliance assessment.

Example conceptual output:

Product: Example Commodity

✓ Product declaration       Present
✓ Net quantity              Present
✓ MRP declaration           Present
✓ Manufacturer information  Present
⚠ Required declaration      Requires verification

Overall Assessment:
REQUIRES REVIEW

This allows a reviewer to understand why a product was flagged.

🧠 Intelligent Compliance Pipeline

PARAKH can be understood as a layered pipeline:

                PACKAGE
                   │
                   ▼
          ┌─────────────────┐
          │ Image / Document │
          │    Processing   │
          └────────┬────────┘
                   │
                   ▼
          ┌─────────────────┐
          │      OCR        │
          └────────┬────────┘
                   │
                   ▼
          ┌─────────────────┐
          │ Data Extraction │
          └────────┬────────┘
                   │
                   ▼
          ┌─────────────────┐
          │ Data Validation │
          └────────┬────────┘
                   │
                   ▼
          ┌─────────────────┐
          │ Regulatory Rule │
          │     Engine      │
          └────────┬────────┘
                   │
                   ▼
          ┌─────────────────┐
          │   Compliance    │
          │    Analysis     │
          └────────┬────────┘
                   │
                   ▼
          ┌─────────────────┐
          │ Findings / Risk │
          │     Report      │
          └─────────────────┘
🏗️ System Architecture

The application is organised into major layers:

┌─────────────────────────────────────────────┐
│                  FRONTEND                   │
│                                             │
│  Product Input • Analysis • Results        │
└──────────────────────┬──────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────┐
│                  BACKEND                    │
│                                             │
│ API • Processing • Validation • Logic       │
└──────────────────────┬──────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────┐
│              INTELLIGENCE LAYER             │
│                                             │
│ OCR • Extraction • Compliance Engine        │
└──────────────────────┬──────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────┐
│             REGULATORY KNOWLEDGE            │
│                                             │
│ Legal Metrology Rules & Requirements        │
└─────────────────────────────────────────────┘
🧮 Compliance as a Structured Decision Problem

PARAKH treats compliance verification as a structured decision problem.

For a product P:

P → Extract declarations
  → Map declarations to requirements
  → Evaluate each requirement
  → Identify deviations
  → Generate compliance assessment

Conceptually:

Compliance(P) =
    Evaluate(
        Extract(P),
        ApplicableRules(P)
    )

This separation between extraction and regulatory evaluation is important because OCR alone cannot determine whether a product is legally compliant.

🧾 Explainable Results

A compliance system should not simply output:

❌ NON-COMPLIANT

It should help the reviewer understand:

WHAT was detected
        ↓
WHAT was expected
        ↓
WHETHER it matched
        ↓
WHAT requires attention

Therefore, PARAKH's intended output is structured around interpretable findings rather than opaque predictions.

🎯 Key Objectives

PARAKH is designed around the following objectives:

1. Automate repetitive verification

Reduce the amount of manual checking required for routine package-level verification.

2. Standardise compliance analysis

Provide a consistent evaluation workflow rather than relying entirely on individual manual processes.

3. Improve scalability

Enable the same verification workflow to be applied across a larger number of packaged commodities.

4. Assist compliance professionals

The system is intended to assist human reviewers, not replace regulatory authority or professional judgement.

5. Make findings understandable

Present detected issues in a structured and interpretable manner.

👥 Intended Users

PARAKH can be relevant to stakeholders involved in packaged-commodity compliance, including:

Regulatory / enforcement personnel
Compliance teams
Manufacturers
Packers
Importers
Retail and supply-chain organisations
Legal / regulatory professionals
Auditors and inspection teams
🛠️ Technology

The project combines software engineering with AI-assisted analysis.

Core technology areas include:

Area	Technology / Approach
Frontend	Web application
Backend	Python-based backend
AI	Artificial Intelligence / Machine Learning
Computer Vision	Package / image analysis
OCR	Text extraction
Compliance	Regulatory rule evaluation
Data	Structured compliance information
Deployment	Web deployment

The exact implementation stack may evolve as PARAKH develops.

🔐 Security & Privacy

Because packaged-product analysis can involve commercial information, security is an important consideration.

The system should follow principles such as:

Avoid exposing API credentials
Keep secrets in environment variables
Never commit .env files
Validate uploaded inputs
Restrict sensitive data access
Avoid unnecessary storage of uploaded product information
Protect backend endpoints
Separate public configuration from secrets

Example:

.env.example     → repository
.env             → local / deployment environment
📊 Example Compliance Flow

Consider a hypothetical packaged commodity.

STEP 1
Upload / provide package information
        ↓

STEP 2
Extract visible declarations
        ↓

STEP 3
Structure the extracted information
        ↓

STEP 4
Identify applicable compliance requirements
        ↓

STEP 5
Evaluate each requirement
        ↓

STEP 6
Generate findings
        ↓

STEP 7
Display overall compliance status

Example:

┌──────────────────────────────────┐
│        COMPLIANCE REPORT         │
├──────────────────────────────────┤
│ Product Name          ✓          │
│ Net Quantity          ✓          │
│ MRP                   ✓          │
│ Manufacturer Details  ✓          │
│ Declaration           ⚠          │
├──────────────────────────────────┤
│ Overall Status: REVIEW REQUIRED  │
└──────────────────────────────────┘
🧪 Validation Philosophy

PARAKH separates three different problems:

Extraction

"What does the package say?"

Interpretation

"What does the extracted information represent?"

Compliance

"Does that information satisfy the applicable requirement?"

This distinction is critical.

OCR ≠ Compliance

OCR
 ↓
Extract Information
 ↓
Structure Information
 ↓
Apply Rules
 ↓
Compliance Assessment
🚧 Limitations

PARAKH is a technology-assisted compliance system.

It should not be interpreted as a replacement for:

Statutory authorities
Official legal interpretation
Professional legal advice
Human inspection where required
Final regulatory decisions

OCR and AI systems may also encounter difficulties with:

Poor image quality
Occluded text
Unusual packaging
Stylised fonts
Multilingual labels
Damaged packaging
Ambiguous declarations

Therefore, results should be treated as decision support and verification assistance, with human review where appropriate.

🌐 Deployment

PARAKH has a web deployment for demonstration and testing.

Live Demo:

https://parakh-ruddy.vercel.app

📂 Project Structure

The project is organised into frontend and backend components:

PARAKH/
│
├── backend/
│   ├── ...
│   └── ...
│
├── frontend/
│   ├── ...
│   └── ...
│
├── parakh.db
│
└── README.md

The exact implementation structure may evolve during development.

🚀 Getting Started
Prerequisites

Depending on the current implementation, you may need:

Python
Node.js
npm
Git
Clone the Repository
git clone https://github.com/NikhilPandeyBuilds/Parakh.git
cd Parakh
Backend

Navigate to the backend:

cd backend

Create and activate a virtual environment:

python -m venv venv
Windows
venv\Scripts\activate
macOS / Linux
source venv/bin/activate

Install dependencies:

pip install -r requirements.txt

Start the backend according to the project's configured entry point.

Frontend

Open another terminal:

cd frontend
npm install

Start the development server:

npm run dev

The exact commands may change as the project evolves.

🧭 Future Scope

PARAKH can be extended toward a broader compliance intelligence platform.

Potential directions include:

More comprehensive regulatory rule coverage
Improved OCR robustness
Better multilingual label understanding
Advanced computer-vision analysis
Automated regulatory knowledge updates
Product-category classification
Historical compliance tracking
Batch product verification
Compliance dashboards
Audit trails
Regulatory change monitoring
Enterprise integrations
Large-scale product databases
🏛️ Regulatory Context

PARAKH is focused on compliance verification associated with India's Legal Metrology (Packaged Commodities) Rules, 2011.

The system's purpose is to assist in analysing packaged-commodity declarations against relevant regulatory requirements.

Regulations can change, and therefore regulatory information used by the system must be maintained and verified against authoritative sources.

🎯 Why PARAKH?

Traditional compliance workflows often require people to manually inspect information, interpret requirements, and document findings.

PARAKH proposes a different workflow:

Manual Inspection
      ↓
   PARAKH
      ↓
Extraction
      ↓
Structured Analysis
      ↓
Rule Evaluation
      ↓
Explainable Findings

The objective is not merely to "use AI".

The objective is to use technology where it can make regulatory verification faster, more structured, and more scalable.

👥 Team
Team PARAKH

PARAKH was collaboratively developed by:

Member
Nikhil Pandey
Aaryan
Jitendra
Akshay
Tanushree
Sudha
🏆 Project

PARAKH

Intelligent Compliance Verification for Packaged Commodities

Developed as a technology solution addressing compliance verification under India's Legal Metrology framework.

📜 Disclaimer

PARAKH is a technology-assisted compliance verification system and should not be treated as an authoritative legal interpretation or substitute for decisions made by competent regulatory authorities.

Regulatory requirements may change over time. Users should verify compliance findings against the latest applicable legislation, rules, notifications, and official guidance.
