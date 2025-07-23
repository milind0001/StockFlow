# 📦 StockFlow — Inventory Management System

**Backend Engineering Intern Case Study Submission**  
**Candidate:** Milind Patil  
**Role:** Backend Engineering Intern  
**Tech Stack:** Python (Flask), MySQL, SQLAlchemy, REST APIs

---

## 🛠️ Overview

**StockFlow** is a B2B SaaS Inventory Management System designed to manage products, warehouses, and supplier relationships while maintaining accurate stock levels. It includes features such as:

- SKU-based product management
- Inventory tracking with historical logs
- Bundle product support
- Supplier linking
- Low-stock alert system

---

## ✅ Part 1: Code Review & Debugging

### 🔍 Original Code Issues

- ❌ No uniqueness check for SKU
- ❌ Missing field validation (e.g., `initial_quantity`)
- ❌ Multiple `commit()` calls (no atomicity)
- ❌ Inaccurate price precision (`float` instead of `Decimal`)
- ❌ Tight coupling of product with warehouse

### ✅ Fixed Version Highlights

- Used `Decimal` for price accuracy
- Enforced SKU uniqueness
- Added proper error handling with rollback
- Ensured atomic DB transaction using `flush()` and single commit
- Separated product creation from warehouse assignment

```python
# See full implementation in /routes/product.py
