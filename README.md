# 🧪 QA Testing Portfolio — Qtec Website & Bechakena Admin Panel

> Manual QA test cases, bug reports, and functional testing documentation for two real-world staging projects.

---

## 📁 Project Structure

```
├── Task01_Qtec_Website_TestCase.xlsx       # Website testing — 45 test cases
└── Task02_Bechakena_AdminPanel_TestCase.xlsx  # Admin panel testing — 62 test cases
```

---

## 📌 Task 01 — Qtec Solution Website Testing

| Field | Details |
|---|---|
| **Project Name** | Qtec Solution Website Testing |
| **Test URL** | https://staging.qtecsolution.com/ |
| **Tester** | MD Mahedy Hasan Naiem |
| **Test Date** | 28-Mar-2026 |
| **Environment** | Staging \| Web |
| **Total Test Cases** | 45 |

### 🔍 Modules Covered

- **Navigation Bar** — Menu links, dropdown behavior, hamburger menu, keyboard accessibility, active states
- **Contact Form** — Form submission, field validations (name, email, message, budget), Calendly integration
- **Homepage** — CTA buttons, anchor scroll behavior, portfolio links, image rendering
- **Footer** — Internal links, social media icons, newsletter subscribe, Privacy Policy & Terms
- **All Pages** — URL redirections, browser back/forward, search functionality

### 🖥️ Testing Types

| Type | Description |
|---|---|
| Functional Testing | Core feature and link behavior |
| Responsive Testing | Viewports: 320px, 375px, 414px, 768px, 1024px, 1366px, 1920px |
| Browser Compatibility | Chrome, Firefox, Edge, Safari |
| Performance Testing | Lighthouse score, lazy loading, JS console errors, WebP fallback |
| UI Testing | Font consistency, spacing, button hover states, image scaling |

### 📊 Test Results Summary

| Status | Count |
|---|---|
| ✅ Passed | 15 |
| ❌ Failed | 30 |

### 🐛 Key Bugs Found

| Bug ID | Module | Issue | Severity |
|---|---|---|---|
| BUG_01 | Navigation | Services dropdown z-index issue on Safari | Major |
| BUG_03 | Navigation | Hamburger menu does not close on outside tap | Major |
| BUG_04 | Navigation | Keyboard navigation (Tab + Enter) fails on dropdown | Major |
| BUG_06 | Contact Form | No success/failure message after form submission | Critical |
| BUG_07–10 | Contact Form | No validation on blank Name, Email, Message fields | Critical |
| BUG_11 | Footer | "Articles" link returns 404 Not Found | Major |
| BUG_12 | Footer | Newsletter subscribe has no email validation | Minor |
| BUG_13 | Footer | Privacy Policy & Terms & Conditions links missing | Major |
| BUG_19 | Footer | Articles link 404 error | Major |
| BUG_20 | Responsive | Hero text overflow at 320px viewport | Major |
| BUG_25 | Browser | Font rendering issue on Firefox | Minor |
| BUG_27 | Performance | Lighthouse mobile score ~52 (target: 90+), FCP 4.2s | Critical |
| BUG_28 | Performance | No lazy loading — all images load on initial page load | Major |
| BUG_29 | Performance | 3 JS runtime errors on every page load | Major |
| BUG_30 | Performance | WebP images with no JPEG/PNG fallback on Safari iOS 13 | Major |

---

## 📌 Task 02 — Bechakena Admin Panel Functional Testing

| Field | Details |
|---|---|
| **Project Name** | Bechakena Admin Panel — Functional Testing |
| **Admin URL** | https://devcore.bechakeena.com |
| **Tester** | MD Mahedy Hasan Naiem |
| **Test Date** | 27-Mar-2026 |
| **Environment** | Staging \| Admin Panel |
| **Total Test Cases** | 62 |

### 🔍 Modules Covered

- **Login / Authentication** — Credentials validation, blank field handling, rate limiting, forgot password, logout
- **Dashboard** — Overview widgets, sales/revenue chart, recent orders
- **Product Management** — Add, edit, delete, search, image upload, price & stock validation
- **Category Management** — Add, edit, delete, duplicate check, XSS sanitization
- **Order Management** — Order list, detail view, status update, search, date filter, invoice download
- **Customer Management** — Customer list, search, profile, order history, duplicate email, account disable
- **Inventory** — Stock deduction, low stock alerts, out-of-stock display, audit log
- **Coupon Management** — Coupon creation, discount validation, expired coupon enforcement, usage limits
- **Reports** — Sales report, date range filter, CSV export
- **Settings** — General settings persistence, email settings, payment gateway toggle, logo upload
- **User Management** — Add/edit/delete users, duplicate email, role permissions, self-delete prevention

### 📊 Test Results Summary

| Status | Count |
|---|---|
| ✅ Passed | 15 |
| ❌ Failed | 47 |

### 🐛 Key Bugs Found

| Bug ID | Module | Issue | Severity |
|---|---|---|---|
| T2_01–04 | Login | No validation on blank/invalid email and password fields | Critical |
| T2_05 | Login | Forgot Password link broken | Major |
| T2_06 | Login | No rate limiting — unlimited failed login attempts allowed | 🔴 Security |
| T2_07–09 | Dashboard | All widgets show zero/N/A; sales chart blank | Major |
| T2_10–15 | Products | Missing validation: blank name, price, negative/zero price, decimal stock, non-image upload | Critical |
| T2_16 | Products | Edit product does not save updated values | Critical |
| T2_17 | Products | No confirmation dialog before product deletion | Major |
| T2_18 | Products | Product search returns no results for valid product name | Major |
| T2_19 | Categories | Duplicate category name accepted without error | Major |
| T2_20 | Categories | XSS script tag stored and executed — vulnerability confirmed | 🔴 Security |
| T2_22 | Categories | Deleting category with assigned products shows no warning | Major |
| T2_24–25 | Orders | No email notification on status change; status can skip stages | Major |
| T2_28 | Orders | Invoice download returns blank/corrupt PDF | Critical |
| T2_32 | Customers | Disabled customer can still log in and place orders | 🔴 Security |
| T2_33 | Inventory | Stock not deducted after order placement | Critical |
| T2_34 | Inventory | No low stock alert shown in admin | Major |
| T2_38 | Coupons | Expired coupon accepted at checkout | Critical |
| T2_39 | Coupons | Coupon usage count not tracked; limit not enforced | Major |
| T2_42 | Settings | Settings not persisted after page refresh | Critical |
| T2_46 | Users | "View Only" role can still perform create/edit/delete actions | 🔴 Security |
| T2_47 | Users | Admin can delete their own account | 🔴 Security |

---

## 🔴 Security Issues Summary

| # | Module | Issue |
|---|---|---|
| 1 | Login | No brute-force protection / rate limiting |
| 2 | Categories | XSS vulnerability — script tag executed on frontend |
| 3 | Customers | Disabled customer accounts not blocked from login |
| 4 | Users | Role permission bypass — View Only role has full access |
| 5 | Users | Admin self-delete allowed |

---

## 🛠️ Tools & Environment

- **Browsers Tested:** Google Chrome, Mozilla Firefox, Microsoft Edge, Apple Safari
- **Devices/Viewports:** 320px, 375px, 414px, 768px, 1024px, 1366px, 1920px
- **Performance Tool:** Chrome DevTools — Lighthouse
- **Network Tool:** Chrome DevTools — Network Tab
- **Test Management:** Microsoft Excel (.xlsx)
- **Environment:** Staging

---

## 👤 Tester

**MD Mahedy Hasan Naiem**
QA Engineer — Manual Testing

---

## 📄 License

This repository contains QA documentation for internal review and development use only.
