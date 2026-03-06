# Health Insurance Data Anonymization

Privacy-focused data anonymization of a health insurance dataset using **HIPAA Safe Harbor de-identification standards** and **k-anonymity techniques** to reduce the risk of patient re-identification while preserving analytical utility.

This project demonstrates how sensitive healthcare data can be prepared for **external auditing and analysis** without exposing personally identifiable information (PII).

---

## Project Overview

Healthcare datasets often contain sensitive information such as names, addresses, medical history, and financial details. When sharing this data externally—for example during financial audits—it is critical to protect individual privacy while retaining enough information for meaningful analysis.

The goal of this project was to **anonymize a health insurance dataset** so it could be safely shared with an external accounting firm conducting a financial review.

The project focuses on balancing two competing goals:

- **Privacy protection** for individuals in the dataset
- **Analytical usability** for legitimate auditing purposes

---

## Dataset

The original dataset contained records related to health insurance members, including:

- demographic attributes
- insurance policy details
- healthcare charges
- medical indicators
- behavioral factors such as smoking status

These records included **personally identifiable information (PII)** and **sensitive health data**, which required careful anonymization before external sharing.

Examples of original fields included:

- Name  
- Social Security Number  
- Policy Number  
- Address and location data  
- Age  
- Income  
- Medical conditions  
- Insurance plan details  
- Healthcare charges

---

## Legal and Ethical Framework

The anonymization strategy was guided primarily by **HIPAA (Health Insurance Portability and Accountability Act)**.

Two main approaches exist for HIPAA-compliant de-identification:

1. **Safe Harbor Method**  
   Removal of 18 specific identifiers that could reveal a patient’s identity.

2. **Expert Determination Method**  
   Statistical evaluation of re-identification risk.

This project primarily followed the **Safe Harbor method**, supplemented with additional data transformations to further reduce re-identification risk.

---

## Anonymization Strategy

The anonymization process was performed in several stages.

### 1. Removal of Direct Identifiers

Fields that directly identify individuals were completely removed.

Examples:

- Name
- Social Security Number
- Policy Number
- Address information

These variables provide immediate identity linkage and are not required for auditing.

---

### 2. Generalization of Quasi-Identifiers

Some variables do not directly identify individuals but could still allow identification when combined with other datasets.

Examples include:

- age
- income
- geographic indicators

These were **generalized into ranges**.

Example transformation:

| Original Value | Anonymized Value |
|---|---|
| Age: 29 | Age: 26–35 |
| Income: $63,000 | Income: $40k–$80k |

This reduces uniqueness in the dataset.

---

### 3. Removal of Highly Sensitive Medical Fields

Some medical attributes were removed entirely because they were not necessary for financial auditing.

Examples removed:

- detailed medical conditions
- previous health diagnoses

---

### 4. Retaining Audit-Relevant Fields

Certain variables were retained because they are necessary for financial review.

Examples retained:

- insurance plan type
- healthcare charges
- BMI
- smoking status
- policy duration

These variables allow auditors to analyze billing patterns without identifying individuals.

---

## Privacy Risk Evaluation

After anonymization, the dataset was evaluated for **re-identification risk**.

One method used was **k-anonymity analysis**, which measures how many records share identical combinations of quasi-identifiers.

In most cases the dataset achieved **k ≥ 3**, meaning each combination of attributes appears in at least three records, significantly reducing the risk of identifying an individual.

---

## Tools Used

Python  
pandas  
Data transformation techniques  
Statistical privacy evaluation  

---

## Key Takeaways

This project demonstrates that sensitive healthcare data can be responsibly shared when appropriate anonymization techniques are applied.

Key lessons include:

- Removing direct identifiers is necessary but not sufficient
- Quasi-identifiers can still reveal individuals if not generalized
- Privacy protection must be balanced with data usability
- Regulatory frameworks like HIPAA provide important guidelines for data governance

---

## Author

Richard Wilders

M.S. Data Science (Expected 2026)  
Former U.S. Marine Corps Signals Intelligence Analyst

LinkedIn  
https://linkedin.com/in/richard-wilders-915395106
