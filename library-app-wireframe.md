# Library Management App – Clickable Flow Description

This document converts the proposed wireframe into a practical, screen-by-screen flow that can be used for UI design and implementation.

## 1) Role-Based Login

**Screen:** `LoginScreen`

**Inputs**
- Phone Number
- Password
- Branch Selector (dropdown)
- Role Selector: Admin / Staff

**Actions**
- `Login` → validates role + branch + credentials

**Navigation**
- Admin login → `AdminDashboard`
- Staff login → `BranchSeatMap` (default) or `StudentRegistration` based on permissions

---

## 2) Admin Dashboard

**Screen:** `AdminDashboard`

**Top summary cards**
- Total Students
- Total Seats Used
- Monthly Revenue
- Monthly Expenses

**Controls**
- Branch selector

**Quick actions**
- Add Student
- Add Expense
- Seat Map

**Navigation**
- `Add Student` → `StudentRegistration`
- `Add Expense` → `ExpenseTracking`
- `Seat Map` → `BranchSeatMap`
- Reports tab → `Reports`
- Settings tab → `Settings`

---

## 3) Branch Seat Map

**Screen:** `BranchSeatMap`

**Layout**
- 75-seat grid
- Color legends:
  - Green = Available
  - Red = Booked
  - Yellow = Reserved

**Interactions**
- Tap available seat → assign student
- Tap booked/reserved seat → view student info + membership status

**Navigation**
- Assign flow → `StudentRegistration` (with seat preselected)
- Student info action → `MembershipAndFees`

---

## 4) Student Registration

**Screen:** `StudentRegistration`

**Form fields**
- Capture Photo (camera button)
- Name
- Phone
- Address
- Branch
- Seat

**Automation**
- Generate QR/Barcode automatically after enrollment confirmation

**Actions**
- `Confirm Enrollment`

**Navigation**
- On success → `MembershipAndFees` (new student profile)

---

## 5) Membership & Fees

**Screen:** `MembershipAndFees`

**Sections**
- Student profile summary
- Current plan: Monthly
- Start date / End date
- Payment history timeline

**Actions**
- Renew Membership
- Add Late Fee (optional)

**Navigation**
- Back to seat map
- Back to dashboard

---

## 6) Expense Tracking

**Screen:** `ExpenseTracking`

**Add Expense Form**
- Category
- Amount
- Date
- Note

**Summary widgets**
- Monthly expense total
- Monthly revenue total
- Profit = Income - Expenses

**Navigation**
- Back to dashboard
- Open reports

---

## 7) Reports

**Screen:** `Reports`

**Report types**
- Revenue report (monthly)
- Expense report (monthly)
- Active vs inactive students
- Seats occupied vs empty

**Optional controls**
- Date filter
- Branch filter
- Export PDF/CSV

---

## 8) Settings

**Screen:** `Settings`

**Modules**
- Add/edit branches
- Add/edit staff roles
- Seat layout editor

---

## Primary User Flows

### Admin Flow
1. Login as Admin
2. View dashboard metrics
3. Manage students, expenses, seat map
4. Check reports and update settings

### Staff Flow
1. Login as Staff
2. Open seat map
3. Register student / assign seats
4. Manage renewals and payments

---

## Suggested Implementation Order

1. Authentication and role routing
2. Branch seat map with 75-seat data model
3. Student registration + seat assignment
4. Membership and fee renewal logic
5. Expense tracking and dashboard metrics
6. Reports and exports
7. Settings and role/branch administration

