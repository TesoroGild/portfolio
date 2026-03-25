---
title: MiandabouAccessoires
publishDate: 2026-03-01 00:00:00
img: /portfolio/assets/miandabou/mdb.png
img_alt: Miandabou's Logo
description: |
  E-commerce ERP
tags:
  - Design
  - Dev
  - User Testing
link: https://miandabou.vercel.app/home
---

![Static Badge](https://img.shields.io/badge/Angular-gray?logo=angular)
![Static Badge](https://img.shields.io/badge/Typescript-gray?logo=Typescript)
![Static Badge](https://img.shields.io/badge/Tailwind-gray?logo=Tailwindcss)
![Static Badge](https://img.shields.io/badge/i18n-gray?logo=i18next)
![Static Badge](https://img.shields.io/badge/Symfony-gray?logo=symfony)
![Static Badge](https://img.shields.io/badge/PHP-gray?logo=php)
![Static Badge](https://img.shields.io/badge/Composer-gray?logo=composer)
![Static Badge](https://img.shields.io/badge/Auth-JWT-blue?logo=jsonwebtokens)
![Static Badge](https://img.shields.io/badge/Docker-gray?logo=docker)
![Static Badge](https://img.shields.io/badge/PostgreSQL-gray?logo=PostgreSQL)

### About
Miandabou is a full-stack e-commerce platform designed to demonstrate mastery of the purchasing cycle and inventory management. The goal was to build a modular architecture capable of managing distinct user roles and complex data flows.

### Key Features
##### Connection
<image src="/portfolio/assets/miandabou/login.png" width=400 center>

##### Account creation
<image src="/portfolio/assets/miandabou/signup1.png" width=400 center><image src="/portfolio/assets/miandabou/signup2.png" width=400 center>

##### Articles
- For employees
<image src="/portfolio/assets/miandabou/stock.png" width=500 center>
- For clients<br>
<image src="/portfolio/assets/miandabou/items.png" width=500 center>

##### Cart
<image src="/portfolio/assets/miandabou/cart1.png" width=500 center>
<image src="/portfolio/assets/miandabou/cart2.png" width=500 center>

##### Bill
<image src="/portfolio/assets/miandabou/confirmation.png" width=500 center>
<image src="/portfolio/assets/miandabou/bill.png" width=500 center>

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
<div style="color: #e53e3e; font-weight: 500; font-size: 0.9em; line-height: 1.5; border-left: 2px solid #e53e3e; padding-left: 15px; margin: 20px 0;">
  🔴 <strong>Service initialization</strong><br/>
  This application is hosted on <strong>serverless</strong> infrastructures (Vercel, Render, and Neon). To optimize resources, these services go into “standby” mode after a period of inactivity.<br/><br/>
  When accessing the application for the first time, a “Cold Start” of approximately 60 seconds may occur while:
  <ul style="margin: 5px 0;">
    <li>1. Provisioning the execution containers (Vercel/Render).</li>
    <li>2. Reactivate the PostgreSQL database instance (Neon).</li>
    <li>3. Load dependencies and initialize the runtime.</li>
  </ul><br/>
  Once awakened, the application responds instantly. Thank you for your patience!
</div>

- **Simulated transaction flow:** In order to prioritize the development of business logic (price calculations, tax management, and PDF invoice generation), the payment stage uses a test environment (Mock Payment). The system validates the data structure without processing actual transactions, thus avoiding unnecessary compliance constraints for a portfolio prototype.