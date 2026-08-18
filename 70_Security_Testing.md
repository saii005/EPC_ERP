# 70. Security Testing

## 1. Objectives & Scope
Security testing for the EPC ERP platform ensures confidentiality, integrity, and availability of sensitive project data (pricing, proprietary engineering designs, subcontractor financials). Scope includes:
* **Static Application Security Testing (SAST):** Scanning Python, JavaScript, and Jinja templates in the `epc_core` Frappe app.
* **Dynamic Application Security Testing (DAST):** Automated vulnerability scans against running endpoints.
* **Penetration Testing:** Simulated attacks targeting role-based permissions and API authentication tokens.

## 2. Key Testing Areas
* **OWASP Top 10 Compliance:** Mitigation against SQL injection (prevented natively by Frappe ORM), Cross-Site Scripting (XSS), and Cross-Site Request Forgery (CSRF).
* **Role-Based Access Control (RBAC):** Verifying that site engineers cannot access accounting financials and vice-versa.
* **API Rate Limiting & Token Expiry:** Ensuring bearer tokens expire correctly and endpoints are shielded from DoS attacks.