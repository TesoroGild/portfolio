---
title: MiandabouAccessoires
publishDate: 2026-03-01 00:00:00
img: /portfolio/assets/mdb.png
img_alt: Miandabou's Logo
description: |
  E-commerce ERP
tags:
  - Design
  - Dev
  - User Testing
link: https://miandabou.vercel.app/home
---

### About
Miandabou is a full-stack e-commerce platform designed to demonstrate mastery of the purchasing cycle and inventory management. The goal was to build a modular architecture capable of managing distinct user roles and complex data flows.

### Key Features
##### Connection
<image src="/portfolio/assets/login.png" width=400 center>

##### Account creation
<image src="/portfolio/assets/signup1.png" width=400 center><image src="/portfolio/assets/signup2.png" width=400 center>

##### Articles
- For employees
<image src="/portfolio/assets/stock.png" width=500 center>
- For clients<br>
<image src="/portfolio/assets/items.png" width=500 center>

##### Cart
<image src="/portfolio/assets/cart1.png" width=500 center>
<image src="/portfolio/assets/cart2.png" width=500 center>

##### Bill
<image src="/portfolio/assets/confirmation.png" width=500 center>
<image src="/portfolio/assets/bill.png" width=500 center>

### Technical highlights
- **Architecture**: Complete decoupling between a SPA (Angular) and a REST API (Symfony).

- **Security**: Session management via JWT in Symfony and route protection by AuthGuards on the Angular side (RBAC).

- **Internationalization & UI/UX**: The application integrates i18n support for a multilingual interface. Emphasis was placed on a smooth user experience, from purchase simulation to PDF invoice generation.

### Challenges & Learning
- **Complex data modeling**: Implementation of advanced relational relationships (Many-to-Many, One-to-Many) in PostgreSQL to manage flexibility between items, coupons, and user reviews.

- **Security & Authentication**: Full implementation of a JWT (JSON Web Tokens) token system to secure exchanges between the Angular frontend and the Symfony API, coupled with AuthGuards for role-based access management (Client vs. Employee).

- **Internationalization (i18n)**: Architecture designed for multilingualism, allowing the interface to be adapted to international markets.

- **DevOps & Deployment**: Orchestration of a distributed environment with Vercel (Frontend), Render (Backend API), and Neon (PostgreSQL Serverless Database), while isolating the data layer via Docker for development.

### Notes
- **Simulated transaction flow:** In order to prioritize the development of business logic (price calculations, tax management, and PDF invoice generation), the payment stage uses a test environment (Mock Payment). The system validates the data structure without processing actual transactions, thus avoiding unnecessary compliance constraints for a portfolio prototype.