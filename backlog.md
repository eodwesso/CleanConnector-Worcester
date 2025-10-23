# 🧹 CleanConnect Worcester – Comprehensive PRD

## 1. Product Overview

**Product Name:** CleanConnect Worcester  
**Objective:** A digital marketplace connecting residents in Worcester, MA (01604) with trusted, verified, and available home cleaners.  
**Platform:** Web + Mobile (iOS/Android via React Native)  
**Launch Target:** Worcester metro area pilot → expand to Central Massachusetts  

---

## 2. Vision Statement

Enable Worcester residents to book a reliable home cleaner in under **3 minutes**, with full visibility into **availability, pricing, and trustworthiness** — supporting local professionals and simplifying home maintenance.

---

## 3. Core Product Goals

| Goal | Description | Success Metric |
|------|--------------|----------------|
| Discoverability | Quickly find local cleaners within 10 miles | ≥ 3 verified cleaners per query |
| Booking Simplicity | Complete booking flow in <5 steps | 90% task completion rate |
| Trust & Safety | Background-verified and rated cleaners | ≥ 4.5 avg. cleaner rating |
| Local Focus | Promote verified Worcester-based cleaners | 60% of bookings from local providers |
| Retention | Encourage repeat cleaning | ≥ 35% repeat bookings per user |

---

## 4. Key Epics and User Stories

---

### **EPIC 1: User Onboarding & Authentication**

**Goal:** Allow users and cleaners to register, log in, and manage their accounts securely.

#### User Stories

| ID | Story | Acceptance Criteria |
|----|--------|---------------------|
| U1 | As a user, I want to sign up via email, Google, or Apple so I can access my account easily. | User can register with OAuth or email/password. Verification email sent. |
| U2 | As a user, I want to input my Worcester address or ZIP (01604) so I can see cleaners nearby. | Address auto-filled via Google Maps API; cleaners displayed within radius. |
| U3 | As a cleaner, I want to create a profile and verify my ID so customers trust me. | Cleaner submits ID via Checkr API; status shows “Verified.” |
| U4 | As a cleaner, I want to upload my service list and hourly rate so I can attract customers. | Cleaner dashboard allows editing service list, pricing, and coverage radius. |

---

### **EPIC 2: Cleaner Discovery & Search**

**Goal:** Enable users to search, filter, and view detailed profiles of local cleaners.

#### User Stories

| ID | Story | Acceptance Criteria |
|----|--------|---------------------|
| S1 | As a user, I want to search for cleaners by ZIP (01604) or location so I see local options. | Search field accepts ZIP or geolocation; results show within 10 miles. |
| S2 | As a user, I want to filter by service type (deep, move-out, standard) so I find specialists. | Filters dynamically narrow results. |
| S3 | As a user, I want to sort cleaners by rating or price so I can compare quality and affordability. | Sort options appear above results and update list in real time. |
| S4 | As a user, I want to view cleaner profiles so I can check experience and reviews. | Clicking a cleaner opens a profile page with details, photos, and ratings. |
| S5 | As a user, I want to see verification badges so I know who is background-checked. | Verified cleaners show “Verified” or “Background Checked” icons. |

---

### **EPIC 3: Booking & Scheduling**

**Goal:** Simplify the process of booking one-time or recurring cleaning sessions.

#### User Stories

| ID | Story | Acceptance Criteria |
|----|--------|---------------------|
| B1 | As a user, I want to view available dates/times for a cleaner so I can choose a slot. | Calendar displays open time slots in real time. |
| B2 | As a user, I want to book a cleaning appointment so I can secure service. | Booking confirmation page summarizes date, time, price, and address. |
| B3 | As a user, I want to schedule recurring cleanings so I don’t have to rebook manually. | Option for weekly, biweekly, or monthly recurrence appears before checkout. |
| B4 | As a user, I want to reschedule or cancel a booking so I stay flexible. | Cancel/reschedule allowed up to 24 hours before appointment. |
| B5 | As a cleaner, I want to manage my availability calendar so I can control my schedule. | Cleaner dashboard syncs with Google Calendar and blocks out personal time. |

---

### **EPIC 4: Payment & Billing**

**Goal:** Ensure secure, transparent, and smooth financial transactions for all users.

#### User Stories

| ID | Story | Acceptance Criteria |
|----|--------|---------------------|
| P1 | As a user, I want to see pricing clearly before booking so there are no surprises. | Service fee, taxes, and tip displayed on summary page. |
| P2 | As a user, I want to pay securely online so I don’t handle cash. | Stripe integration processes credit/debit/Apple Pay transactions. |
| P3 | As a cleaner, I want to receive payouts automatically so I don’t wait long. | Payout via Stripe Connect within 2 business days after job completion. |
| P4 | As an admin, I want to track platform commissions so I can monitor revenue. | Admin dashboard shows total revenue, fees, and transactions per month. |

---

### **EPIC 5: Reviews, Ratings & Trust**

**Goal:** Build community confidence through reviews and transparent feedback.

#### User Stories

| ID | Story | Acceptance Criteria |
|----|--------|---------------------|
| R1 | As a user, I want to leave a star rating after each job so others can assess quality. | Rating (1–5) and optional comment required post-cleaning. |
| R2 | As a user, I want to upload photos of cleaned areas so reviews are more credible. | Up to 3 photos attachable to review. |
| R3 | As a cleaner, I want to view my reviews so I can improve my services. | Cleaner dashboard lists ratings and average performance metrics. |
| R4 | As an admin, I want to moderate reviews to prevent spam or abuse. | Admin portal includes flag/review moderation tools. |

---

### **EPIC 6: Notifications & Communication**

**Goal:** Keep both users and cleaners informed at every step.

#### User Stories

| ID | Story | Acceptance Criteria |
|----|--------|---------------------|
| N1 | As a user, I want to receive booking confirmation by SMS/email. | Confirmation triggered immediately post-payment. |
| N2 | As a user, I want reminders 24 hours and 1 hour before cleaning. | Automatic notifications sent via Twilio API. |
| N3 | As a cleaner, I want to be notified when a booking is confirmed or canceled. | Cleaner receives SMS/email instantly when booking changes. |
| N4 | As a user, I want in-app chat with my cleaner for instructions. | Secure chat available from booking dashboard; messages archived. |

---

### **EPIC 7: Admin & Operations**

**Goal:** Provide tools for admins to manage users, cleaners, and bookings efficiently.

#### User Stories

| ID | Story | Acceptance Criteria |
|----|--------|---------------------|
| A1 | As an admin, I want to verify new cleaner applications so I ensure quality. | Admin approves/rejects applications based on background checks. |
| A2 | As an admin, I want to view all bookings in a dashboard so I can oversee operations. | Admin sees bookings by date, user, and cleaner. |
| A3 | As an admin, I want to view analytics for revenue and user engagement. | Dashboard includes metrics on active users, avg. booking value, repeat rate. |
| A4 | As an admin, I want to handle disputes between users and cleaners. | Admin can view complaint, pause payouts, and issue refunds. |

---

## 5. Technical Design Summary

| Component | Tech Stack |
|------------|------------|
| Frontend | React.js + TailwindCSS (Web), React Native (Mobile) |
| Backend | Node.js + Express |
| Database | PostgreSQL (AWS RDS) |
| Authentication | OAuth (Google, Apple, Email) |
| APIs | Google Maps, Stripe, Checkr (backgrounds), Twilio, Thumbtack/Angi/TaskRabbit integrations |
| Hosting | AWS Lambda (serverless), CloudFront CDN, S3 static storage |
| Monitoring | AWS CloudWatch, Sentry.io for error tracking |

---

## 6. Data Model (Simplified ER Diagram)

**Entities:**

- **User** (user_id, name, email, phone, address, role, created_at)  
- **Cleaner** (cleaner_id, name, bio, price, rating, verified_status, service_radius, photo_url)  
- **Booking** (booking_id, user_id, cleaner_id, date, time, price, status, recurrence, created_at)  
- **Review** (review_id, booking_id, rating, comment, photo_url, created_at)  
- **Payment** (payment_id, booking_id, stripe_txn_id, amount, status, created_at)  

---

## 7. Local Integrations (Worcester 01604)

- **Thumbtack API:** Local service provider listings  
- **Angi API:** Cross-verification of professionals  
- **TaskRabbit API:** Optional fallback sourcing  
- **Worcester Telegram & Gazette Classifieds:** Manual listing integration for independent cleaners  

---

## 8. Security & Compliance

- **Data Protection:** GDPR & CCPA compliant data handling  
- **Encryption:** TLS 1.3, password hashing via bcrypt  
- **Payment Security:** PCI DSS Level 1 compliant (via Stripe)  
- **Background Checks:** Checkr API integration for identity + criminal verification  

---

## 9. Future Enhancements

- **AI Recommendations:** Suggest preferred cleaners based on historical reviews  
- **Voice Booking:** Alexa and Google Assistant commands  
- **Smart Lock Integration:** Optional door access (via August or Yale APIs)  
- **Multi-Property Management:** For landlords and Airbnb hosts  
- **Subscription Model:** Flat monthly plan for recurring cleanings  

---

## 10. Milestones & Timeline

| Phase | Deliverable | Target Date | Owner |
|--------|--------------|--------------|--------|
| Phase 1 | MVP (Search, Profiles, Booking Flow) | Month 1–2 | Dev Team |
| Phase 2 | Payments + Reviews | Month 3 | Backend + QA |
| Phase 3 | Notifications + Cleaner Dashboard | Month 4 | Full Stack |
| Phase 4 | Beta Launch (Worcester 01604) | Month 5 | Product + Marketing |
| Phase 5 | Expansion to Nearby ZIPs (01605, 01545) | Month 6 | Ops Lead |

---

## 11. Success Snapshot

> “A Worcester resident opens the CleanConnect app, finds three nearby cleaners with verified reviews, books one for the weekend, and pays — all within 3 minutes.”

---

## 12. Glossary

| Term | Definition |
|------|-------------|
| **Verified Cleaner** | A cleaner with completed ID + background check |
| **MVP** | Minimum Viable Product |
| **Recurring Booking** | Auto-scheduled cleaning at regular intervals |
| **API Integration** | Real-time data sourcing from 3rd party services |
| **Checkr** | Background verification service API |

---
