# 🐞 SQL Injection (SQLi) - PortSwigger Labs

## 📌 Introduction

SQL Injection (SQLi) is a web vulnerability that allows attackers to interfere with the queries an application makes to its database. This can lead to unauthorized access, data breaches, or even full system compromise.

---

## 🧩 Problem Statement

The goal of these labs was to simulate and exploit SQL Injection vulnerabilities in intentionally insecure applications to understand how attackers can manipulate SQL queries, extract data, and gain unauthorized access.

---

## 🚀 Approach

1. Identified vulnerable input points such as login forms and search fields.
2. Used `ORDER BY` and `UNION SELECT NULL` to determine the number of query columns.
3. Discovered which columns accepted string data.
4. Extracted sensitive data like usernames and passwords.
5. Used concatenation techniques for single-column outputs.
6. Captured screenshots and documented all findings.

---

## 🛠 Tools Used

- **Burp Suite** – Intercept and modify HTTP requests.
- **PortSwigger Web Security Academy** – Hands-on SQLi practice labs.
- **Web Browser** – Interaction with lab environments.
- **Markdown Editor** – Documentation and reporting.

---

## 🧪 Techniques Practiced

### ✅ Types of SQL Injection

1. **In-Band SQLi**
   - **Union-based**: Uses `UNION` to retrieve additional data.
   - **Error-based**: Leverages database error messages.
2. **Blind SQLi**
   - **Boolean-based**: Infers logic from true/false responses.
   - **Time-based**: Uses delays to extract data.
3. **Out-of-Band SQLi**
   - Sends data to an external system via DNS or HTTP.

---

## 🔍 Exploiting SQL Injection with UNION

### How UNION Attacks Work

The `UNION` operator allows an attacker to append a malicious query to the original query if the number and data type of columns match.

```sql
SELECT a, b FROM table1 
UNION 
SELECT c, d FROM table2;
