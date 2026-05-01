🧪 QA Testing Portfolio — Qtec Website & Bechakena Admin Panel

Manual QA test cases, bug reports, and functional testing documentation for two real-world staging projects.

📁 Project Structure
├── Task01_Qtec_Website_TestCase.xlsx       # Website testing — 45 test cases
└── Task02_Bechakena_AdminPanel_TestCase.xlsx  # Admin panel testing — 62 test cases

📌 Task 01 — Qtec Solution Website Testing
FieldDetailsProject NameQtec Solution Website TestingTest URLhttps://staging.qtecsolution.com/TesterMD Mahedy Hasan NaiemTest Date28-Mar-2026EnvironmentStaging | WebTotal Test Cases45
🔍 Modules Covered

Navigation Bar — Menu links, dropdown behavior, hamburger menu, keyboard accessibility, active states
Contact Form — Form submission, field validations (name, email, message, budget), Calendly integration
Homepage — CTA buttons, anchor scroll behavior, portfolio links, image rendering
Footer — Internal links, social media icons, newsletter subscribe, Privacy Policy & Terms
All Pages — URL redirections, browser back/forward, search functionality

🖥️ Testing Types
TypeDescriptionFunctional TestingCore feature and link behaviorResponsive TestingViewports: 320px, 375px, 414px, 768px, 1024px, 1366px, 1920pxBrowser CompatibilityChrome, Firefox, Edge, SafariPerformance TestingLighthouse score, lazy loading, JS console errors, WebP fallbackUI TestingFont consistency, spacing, button hover states, image scaling
📊 Test Results Summary
StatusCount✅ Passed15❌ Failed30
🐛 Key Bugs Found
Bug IDModuleIssueSeverityBUG_01NavigationServices dropdown z-index issue on SafariMajorBUG_03NavigationHamburger menu does not close on outside tapMajorBUG_04NavigationKeyboard navigation (Tab + Enter) fails on dropdownMajorBUG_06Contact FormNo success/failure message after form submissionCriticalBUG_07–10Contact FormNo validation on blank Name, Email, Message fieldsCriticalBUG_11Footer"Articles" link returns 404 Not FoundMajorBUG_12FooterNewsletter subscribe has no email validationMinorBUG_13FooterPrivacy Policy & Terms & Conditions links missingMajorBUG_19FooterArticles link 404 errorMajorBUG_20ResponsiveHero text overflow at 320px viewportMajorBUG_25BrowserFont rendering issue on FirefoxMinorBUG_27PerformanceLighthouse mobile score ~52 (target: 90+), FCP 4.2sCriticalBUG_28PerformanceNo lazy loading — all images load on initial page loadMajorBUG_29Performance3 JS runtime errors on every page loadMajorBUG_30PerformanceWebP images with no JPEG/PNG fallback on Safari iOS 13Major

📌 Task 02 — Bechakena Admin Panel Functional Testing
FieldDetailsProject NameBechakena Admin Panel — Functional TestingAdmin URLhttps://devcore.bechakeena.comTesterMD Mahedy Hasan NaiemTest Date27-Mar-2026EnvironmentStaging | Admin PanelTotal Test Cases62
🔍 Modules Covered

Login / Authentication — Credentials validation, blank field handling, rate limiting, forgot password, logout
Dashboard — Overview widgets, sales/revenue chart, recent orders
Product Management — Add, edit, delete, search, image upload, price & stock validation
Category Management — Add, edit, delete, duplicate check, XSS sanitization
Order Management — Order list, detail view, status update, search, date filter, invoice download
Customer Management — Customer list, search, profile, order history, duplicate email, account disable
Inventory — Stock deduction, low stock alerts, out-of-stock display, audit log
Coupon Management — Coupon creation, discount validation, expired coupon enforcement, usage limits
Reports — Sales report, date range filter, CSV export
Settings — General settings persistence, email settings, payment gateway toggle, logo upload
User Management — Add/edit/delete users, duplicate email, role permissions, self-delete prevention

📊 Test Results Summary
StatusCount✅ Passed15❌ Failed47
🐛 Key Bugs Found
Bug IDModuleIssueSeverityT2_01–04LoginNo validation on blank/invalid email and password fieldsCriticalT2_05LoginForgot Password link brokenMajorT2_06LoginNo rate limiting — unlimited failed login attempts allowed🔴 SecurityT2_07–09DashboardAll widgets show zero/N/A; sales chart blankMajorT2_10–15ProductsMissing validation: blank name, price, negative/zero price, decimal stock, non-image uploadCriticalT2_16ProductsEdit product does not save updated valuesCriticalT2_17ProductsNo confirmation dialog before product deletionMajorT2_18ProductsProduct search returns no results for valid product nameMajorT2_19CategoriesDuplicate category name accepted without errorMajorT2_20CategoriesXSS script tag stored and executed — vulnerability confirmed🔴 SecurityT2_22CategoriesDeleting category with assigned products shows no warningMajorT2_24–25OrdersNo email notification on status change; status can skip stagesMajorT2_28OrdersInvoice download returns blank/corrupt PDFCriticalT2_32CustomersDisabled customer can still log in and place orders🔴 SecurityT2_33InventoryStock not deducted after order placementCriticalT2_34InventoryNo low stock alert shown in adminMajorT2_38CouponsExpired coupon accepted at checkoutCriticalT2_39CouponsCoupon usage count not tracked; limit not enforcedMajorT2_42SettingsSettings not persisted after page refreshCriticalT2_46Users"View Only" role can still perform create/edit/delete actions🔴 SecurityT2_47UsersAdmin can delete their own account🔴 Security

🔴 Security Issues Summary
#ModuleIssue1LoginNo brute-force protection / rate limiting2CategoriesXSS vulnerability — script tag executed on frontend3CustomersDisabled customer accounts not blocked from login4UsersRole permission bypass — View Only role has full access5UsersAdmin self-delete allowed

🛠️ Tools & Environment

Browsers Tested: Google Chrome, Mozilla Firefox, Microsoft Edge, Apple Safari
Devices/Viewports: 320px, 375px, 414px, 768px, 1024px, 1366px, 1920px
Performance Tool: Chrome DevTools — Lighthouse
Network Tool: Chrome DevTools — Network Tab
Test Management: Microsoft Excel (.xlsx)
Environment: Staging


👤 Tester
MD Mahedy Hasan Naiem
QA Engineer — Manual Testing

📄 License
This repository contains QA documentation for internal review and development use only.
