---
title: MyUAAcademia
publishDate: 2026-03-25 00:00:00
img: /portfolio/assets/myua/logo.png
img_alt: MYUA's Logo
description: |
  Multi-role academic management platform (student, faculty, staff)
tags:
  - Design
  - Dev
link: https://
---

![Static Badge](https://img.shields.io/badge/React-gray?logo=react)
![Static Badge](https://img.shields.io/badge/Tailwind-gray?logo=Tailwindcss)
![Static Badge](https://img.shields.io/badge/Flowbite-gray?logo=react)
![Static Badge](https://img.shields.io/badge/React--Hook--Form-gray?logo=react)
[<img src="https://img.shields.io/badge/My SQl Server-yellow.svg">]()

### About
MyUA Academia is a full-stack school management platform designed to centralize the operations of a higher education institution. The platform covers the entire academic lifecycle—from student admission to grade entry—by providing three distinct interfaces tailored to the role of the logged-in user.

### Key Features
##### Admission & Onboarding
<image src="/portfolio/assets/myua/admission1.png" width=400 center>
<image src="/portfolio/assets/myua/admission2.png" width=400 center>
<image src="/portfolio/assets/myua/admission3.png" width=400 center>
<image src="/portfolio/assets/myua/admission4.png" width=400 center>
<image src="/portfolio/assets/myua/admission5.png" width=400 center>
<image src="/portfolio/assets/myua/admission6.png" width=400 center>
<image src="/portfolio/assets/myua/admission7.png" width=400 center>

Public application form with program selection (up to 2), password complexity requirements, and document upload. The full process includes application review, payment of the application fee ($120), and email confirmation. 

##### Student sspace
<image src="/portfolio/assets/myua/sspace1.png" width=400 center><image src="/portfolio/assets/myua/sspace2.png" width=400 center>
<image src="/portfolio/assets/myua/sspace4.png" width=400 center><image src="/portfolio/assets/myua/sspace5.png" width=400 center>
<image src="/portfolio/assets/myua/sspace6.png" width=400 center>

* Course registration with schedule conflict detection and shopping cart management
* Billing by session with dynamic calculation (course fees + fixed costs)
* Academic progress tracking (courses completed / in progress / remaining)
* Transcript with color-coded honors badges

##### Professeur space
<image src="/portfolio/assets/myua/pspace1.png" width=500 center>
<image src="/portfolio/assets/myua/pspace2.png" width=500 center>
<image src="/portfolio/assets/myua/pspace3.png" width=500 center>

* Drill-down navigation: Level → Program → Course → Enrolled Students
* Grade entry by grade level (A+… E) with CSV import and progress bar
* Weekly academic schedule and room availability check

##### Admin space
<image src="/portfolio/assets/myua/aspace1.png" width=500 center>
<image src="/portfolio/assets/myua/aspace2.png" width=500 center>
<image src="/portfolio/assets/myua/aspace3.png" width=500 center>
<image src="/portfolio/assets/myua/aspace4.png" width=500 center>

* Comprehensive employee management: creating and approving records, activating accounts
* Contract system (open positions) with auto-fill when creating an employee
* Assigning teachers to class sessions
* School schedule filtered by teacher or room


### Technical highlights
- **RBAC Architecture**: Four roles (student, professor, employee, admin) with React-side routing and conditional components, and JWT on the API side.
- **Contract Modeling**: Separation between the job template (Contracts) and the individual instance (EmployeesContracts) — negotiated salary, actual dates — reflecting realistic HR logic.
- **Asynchronous state management**: Solves the N+1 problem (calculating subtotals, grades) by returning data directly from async calls rather than reading the React state after a set operation.
- **Multi-role UX**: A single Sidebar component and a single contextual 404 page adapt to the logged-in role without code duplication.

### Challenges & Learning
- **Nested data flows**: Managing tightly coupled entities (programs → courses → sessions → students → grades) required careful consideration of endpoints and SQL joins to avoid cascading calls on the front end.
- **Separation of concerns**: The distinction between `isValidated` and `isActivated` for employees illustrates a concrete case where two closely related business states require separate fields to remain semantically correct.
- **Large-scale visual consistency**: Over 30 pages with reusable patterns (drill-down, list + sidebar, filter pills) designed to remain consistent without a formal design system.

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

<div style="color: #3b82f6; font-weight: 500; font-size: 0.9em; line-height: 1.5; border-left: 2px solid #3b82f6; padding-left: 15px; margin: 20px 0;">
  🔵 <strong>Demo Data<br/>
  The application is populated with sample data to allow users to fully explore the three areas without creating an account.<br/><br/>

  Administrators :
  <ul style="margin: 5px 0;">
    <li>Emma : emp1 Emma1234-</li>
  </ul><br/>
  Professors :
  <ul style="margin: 5px 0;">
    <li>Curry : CURS14151988RN0 curry.</li>
    <li>Rihanna : FENR20351988PF0 Rihanna1234-</li>
  </ul><br/>
  Students :
  <ul style="margin: 5px 0;">
    <li>Koffi : ABAK1628199914 ABAKbienvenido29.</li>
    <li>Wei : CHEW7758200122 Wei1234-.</li>
  </ul><br/>
</div>