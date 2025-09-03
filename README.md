# 📦 Export Logistic Management System (ELMS)

## 📖 Project Overview
The **Export Logistic Management System** is a **Database Management System (DBMS) project** designed to model a global logistics platform.  
It focuses on **database design, data insertion, and SQL queries** for sellers, consumers, agencies, shipments, payments, and dockyards.  
The project demonstrates **BCNF normalization**, rich datasets, and analytical SQL queries for real-world logistics scenarios.

---

## 📂 Project Files
| File | Description |
|------|-------------|
| `DDL Script.txt` | Database schema with all table definitions, primary and foreign keys. |
| `ERD_SCHEMA WITH NORMALIZATION PROOF.pdf` | Entity-Relationship Diagram (ERD) and normalization proof up to **BCNF**. |
| `INSERT DATA.txt` | SQL insert statements with realistic sample data. |
| `QUERY.txt` | 24 SQL queries for logistics analytics and reporting. |

---

## 🏗️ Database Design
Key entities in this system:
- **Seller** – Seller details and addresses.  
- **Consumer** – Buyer details and addresses.  
- **Agency** – Logistics service providers with ratings.  
- **Goods** – Product details and per-unit tax.  
- **Invoice** – Order records with status and amounts.  
- **Ship & Shipment_Location** – Shipping data and real-time tracking.  
- **Charges & Have** – Agency pricing and goods mappings.  
- **Dockyard** – Port details for shipment operations.  
- **Payment** – Transaction details.  
- **Ratings** – Feedback from sellers and consumers.

The database is fully normalized to **Boyce-Codd Normal Form (BCNF)**.

---

## ⚙️ Setup Instructions
1. **Create Schema:**
   ```sql
   CREATE SCHEMA "Export Logistic Management System";
   SET SEARCH_PATH TO "Export Logistic Management System";
Run DDL Script:
Execute DDL Script.txt to create tables.

Insert Data:
Run INSERT DATA.txt to populate sample data.

Explore Queries:
Execute QUERY.txt to analyze operations, reports, and insights.
🔍 Example Queries

Agencies and shipment charges by route:

SELECT AID, Name, Charge 
FROM Agency NATURAL JOIN Charges 
WHERE G_Type='Vehicles' 
AND Pickup_Location='Auckland Port' 
AND Delivery_Location='Hamburg Port'
ORDER BY Charge;


Top 3 carriers by delivered orders:

SELECT AID, Name, COUNT(AID) 
FROM Invoice NATURAL JOIN Agency 
WHERE Payment_Status='paid' AND Order_Status='delivered'
GROUP BY AID, Name
ORDER BY COUNT(AID) DESC LIMIT 3;

🚀 Features

✅ BCNF-normalized relational schema

✅ Rich global dataset (sellers, consumers, ports, shipments)

✅ 24 ready-to-use analytical queries

✅ Realistic relationships and foreign keys

✅ Great for DBMS learning, SQL practice, and projects
