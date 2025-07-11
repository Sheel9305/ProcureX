<p align="center">
  <img src="Logo File.png" alt="Tender Management System Logo" width="500">
</p>

<h1 align="center">Tender Management System 📈</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Database-PostgreSQL-336791?style=for-the-badge&logo=postgresql" alt="PostgreSQL Badge">
  <img src="https://img.shields.io/badge/Language-SQL-4285F4?style=for-the-badge&logo=sql" alt="SQL Badge">
  <img src="https://img.shields.io/badge/Normalization-BCNF%2F3NF-FFC107?style=for-the-badge" alt="Normalization Badge">
</p>

---

## 🌟 Project Overview

This **Tender Management System** is a comprehensive database project built as part of our DBMS(IT-214) coursework at **Dhirubhai Ambani University**. It offers an end-to-end solution for managing the tender lifecycle — from creation and bidding to contract awarding and payment tracking. The system emphasizes automation, vendor risk mitigation, and detailed reporting using well-designed relational schemas.

---

## ✨ Key Features

- **End-to-End Tender Lifecycle:** Covers creation, bidding, evaluation, contract allocation, and payments.
- **Automated Vendor Risk Management:** A trigger (`trg_redflag_check`) red-flags vendors with ≥2 abandoned contracts and deletes their bids.
- **Smart Bid Evaluation:** Trigger (`trg_auto_eval_bid`) auto-evaluates new bids and assigns audit committee oversight.
- **Normalized Schema (BCNF/3NF):** Ensures minimal redundancy and referential integrity.
- **Advanced Reporting:** Pre-built SQL queries offer insights into vendor stats, tender savings, and payment status.

---

## 📊 Database Design

The project follows an ER-to-relational mapping approach, producing a normalized schema using functional dependencies.

### 🔗 Relational Schema Highlights

- **Tender:** `TenderID` (PK), `T_Name`, `Description`, `Status`, `Budget`, `Deadline`
- **Vendor:** `VendorID` (PK), `V_Name`, `Contact`, `CompletedContracts`, `AbandonedContracts`, `IsRedFlagged`
- **Bids:** `BidID` (PK), `BidAmount`, `TenderID` (FK), `VendorID` (FK), `EvalID` (FK)
- **Contract:** `ContractID` (PK), `TenderID` (FK), `VendorID` (FK), `Status`, `Amount`
- **Payments:** `{ContractID, PaymentID}` (Composite PK), `AmountPaid`, `PaymentDate`
- **AuditCommittee:** `UserID` (PK), `Role`, `Name`, `EmailID`
- **BidEval:** `EvalID` (PK), `ApprovalStatus`, `ApprovalDate`, `UserID` (FK)

📄 For full schema, refer to [`G5_T12_DBMSProject.pdf`](G5_T12_DBMSProject.pdf)

---

## 🛠️ Implementation Overview

- **Database Used:** PostgreSQL
- **Scripts:** DDL (table creation, constraints), DML (sample inserts)
- **Triggers:**
  - `trg_redflag_check` – flags risky vendors, deletes bids
  - `trg_auto_eval_bid` – auto-evaluates incoming bids

---

## 🔍 Sample Query Output

### 📋 Tender Summary Report

Summarizes tenders, evaluations, and awarded contracts.

![Tender Summary Query Output](Summary%20Output.png)

*(More examples available in the full project report.)*

---

## 🚀 Future Enhancements

- 🔐 **Role-Based Access Control (RBAC):** Secure login for admin, vendors, auditors
- 📊 **Dashboards:** Real-time performance charts using vendor & contract data
- 📬 **Notifications:** SMS/email alerts for bid deadlines, tender results, contract milestones

---

## 👥 Team Members

- **Tirth Gandhi** 
- **Sheel Shah**   
- **Manit Shah** 
