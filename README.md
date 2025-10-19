# 🩺 Liver Transplant Data Processing & ISGLS Calculation

## 📘 Overview
This repository contains a data integration and preprocessing pipeline for **post-liver-transplant patient data** collected from three hospitals — **Hwasun**, **Kosin**, and **Samsung**.  
The goal of this project is to unify heterogeneous clinical datasets into a standardized format, perform data cleaning, and compute **ISGLS (International Study Group of Liver Surgery)** scores for postoperative evaluation.

---

## 🧩 Objectives
- 🏥 **Integrate** multi hospital patient datasets into a single standardized schema  
- 🧹 **Clean & preprocess** raw data with inconsistent or missing entries  
- ⏱️ **Aggregate time-series records** based on POD (Postoperative Day) intervals  
- 🧮 **Compute ISGLS values** automatically from cleaned datasets  

---

## 🧠 Data Processing Pipeline

### 1️⃣ Data Integration
- Combined data from three sources:  
  - Paitent Execl files from Hwasun, Kosin, and Samsung
- Standardized column names, units, and data types across all datasets  
- Merged into a unified table for downstream analysis  

### 2️⃣ Data Cleaning & Validation
- Removed or imputed missing values  
- Handled invalid characters such as `<`, `*`, or text in numeric fields  
- Applied specific rules to fill in empty measurements based on nearby valid records  
- Ensured numeric conversion and data consistency across all hospitals  

### 3️⃣ POD-Based Data Aggregation
- Extracted and aligned measurements by **Postoperative Day (POD)**  
- Targeted POD checkpoints: **Day 1, 3, 4, 7, 10, and 14**  
- Selected the **closest available record** to each POD based on timestamp proximity  
- If multiple values were equally close, applied a defined selection hierarchy (e.g., lab priority)  

### 4️⃣ ISGLS Computation
- Implemented automated calculation of **ISGLS score** for liver function classification  
- Used postoperative lab data (e.g., bilirubin, INR, ALT/AST) to assess liver dysfunction severity  
- Generated structured outputs for further modeling or statistical analysis  

---

## ⚙️ Tech Stack
- **Language:** JAVA 
- **Environment:** Intellij

