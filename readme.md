# 📦 SmartOrder Logistics Solution

## 📌 Project Overview

**SmartOrder Logistics Solution** is an end-to-end digital logistics system developed as part of an academic challenge in a **Mobile Development university course**.

The main objective of this project is to optimize:

* 🧾 order registration
* ⚙️ operational workflows
* 👥 staff performance tracking

using the **Microsoft Power Platform**.

---

## ⚙️ Data Architecture

The solution is built on **Microsoft Dataverse**, ensuring a robust and scalable relational data model. The system is composed of two main tables:

* 🧾 **Orders (`cr299_order`)**
  Stores transactional data such as order status, pricing information, and audit timestamps.

* 👥 **Employers (`cr299_employers`)**
  Manages employee data, enabling accountability, traceability, and productivity analysis.

---

## 📱 Power Apps & Automation

The application was designed with a strong focus on **speed**, **security**, and **error reduction**.

### 🔍 Barcode-Based Registration

All data input is performed exclusively through **barcode scanning**, eliminating manual entry and minimizing human error.

Supported formats include:

* 📎 Code 128
* 📷 QR Code
* 🏷️ EAN
* ➕ Other standard barcode formats

### 🔐 Role-Based Access Control (RBAC)

The system enforces **Role-Based Access Control** to ensure secure operations:

* 👑 **Admin**

  * Full system access
  * User management
  * Permission to delete orders

* 🛠️ **Worker**

  * Operational access only
  * Permission to create orders
  * ❌ No permission to delete records

### ⚡ Power Automate

A background cloud flow named **`createDate`** is used to automatically generate date attributes when a row is created.

The flow derives and stores:

* 📅 **Year**
* 📆 **Month**
* 🗓️ **Day**

based on the record creation date. This structure enables more efficient filtering, grouping, and time-based analysis in **Power BI**.

---

## 📊 Business Intelligence (Power BI)

The **Power BI** dashboard provides real-time operational insights and is organized into four pages:

* 📈 **Summary**
  High-level KPIs and daily order evolution

* 📅 **Overview**
  Monthly trends and order volume distribution

* 🗂️ **Orders**
  Detailed and auditable order records

* 👤 **Users**
  Employee productivity analysis

---

## ⚠️ Connectivity & Setup Notes

After deployment, some manual configuration steps may be required:

* 🔗 **Power BI Data Source**
  Update the Dataverse connection to match your target environment URL.

* 🔑 **Authentication**
  Ensure OAuth2 is used with an **Organizational** privacy level.

---

## 📁 Repository Structure

The project was exported using the **Power Platform CLI (PAC CLI)** to ensure full source code visibility.

```
/src
 ├── 📱 CanvasApps     # Power Apps UI and logic
 ├── 🗄️ Entities       # Dataverse table schemas (XML)
 ├── ⚙️ Workflows      # Power Automate flows (JSON)

📊 SmartOrder_Dashboard.pbix   # Power BI report
🙈 .gitignore                  # Excludes temporary and credential files
```
