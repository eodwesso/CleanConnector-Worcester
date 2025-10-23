# 🧹 CleanConnect Worcester – PRD

## 1. Overview

**Product Name:** CleanConnect Worcester  
**Objective:** To create a web and mobile platform that sources, compares, and books professional cleaners in the Worcester, MA (01604) area based on user preferences, location, and availability.  
**Primary User:** Residents and property owners in Worcester looking for reliable, vetted cleaning professionals.  

---

## 2. Problem Statement

In Worcester, MA, residents rely on word-of-mouth, Facebook groups, or general service apps to find home cleaners. These sources lack transparency, consistency, and trust. CleanConnect Worcester solves this by aggregating local cleaners, ratings, and prices into a single, verified marketplace.

---

## 3. Goals & Success Metrics

| Goal | Metric |
|------|--------|
| Simplify cleaner discovery | 3+ verified local cleaners shown within 2 minutes |
| Improve booking convenience | 90% of bookings completed in under 5 clicks |
| Build community trust | Maintain cleaner average rating ≥ 4.5 stars |
| Encourage retention | ≥ 35% repeat bookings within 90 days |

---

## 4. User Personas

### 👩 Worcester Resident – “Erica”
- Location: Near Lake Quinsigamond (01604)  
- Busy healthcare professional  
- Needs weekly or biweekly cleaning  
- Prefers local, background-checked cleaners  

### 👨 Property Owner – “Luis”
- Owns multiple rental units in downtown Worcester  
- Needs turnover cleaning between tenants  
- Requires invoices and reliable recurring scheduling  

---

## 5. Key Features

### 🧭 Local Discovery
- Cleaners sourced from:
  - **Thumbtack API**
  - **Angi (Angie’s List) API**
  - **TaskRabbit API**
  - Local independent cleaners (direct onboarding)
- Search by ZIP code (01604) or geolocation  
- Filter by:
  - Service type (standard, deep, move-out, Airbnb turnover)
  - Availability
  - Price range
  - Reviews and verification badges

### 🗓️ Booking & Scheduling
- Instant or scheduled booking with calendar sync  
- Repeat booking options (weekly, biweekly, monthly)  
- Auto-reminder system (SMS + push notifications)  

### 💳 Payments
- Secure checkout via **Stripe**  
- Transparent pricing with optional tip line  
- Automated receipts and invoices  

### 🧼 Service Customization
- Custom task checklist per room  
- Add-ons: carpet cleaning, oven cleaning, fridge, windows  
- Post-clean feedback form with optional photos  

### ⭐ Trust & Safety
- Background verification via **Checkr API**  
- Verified photo ID and local business license (if applicable)  
- Insurance verification for professional cleaners  

---

## 6. Technical Requirements

| Category | Requirement |
|-----------|--------------|
| Frontend | React.js (web) + React Native (mobile) |
| Backend | Node.js + Express |
| Database | PostgreSQL (AWS RDS) |
| Location Services | Google Maps API (Worcester area focus) |
| Payments | Stripe API |
| Integrations | Thumbtack, TaskRabbit, Angi APIs |
| Authentication | OAuth (Google, Apple, Email) |
| Hosting | AWS Lambda + S3 or Firebase |

---

## 7. Data Model Overview

**Entities:**
- **User:** name, address (01604, etc.), contact info, preferences  
- **Cleaner:** name, rating, service types, location radius, verified status  
- **Booking:** user_id, cleaner_id, service_date, tasks, payment_status  
- **Review:** booking_id, rating, comment, photo  

---

## 8. Local User Flow

1. **User enters ZIP 01604** or enables location access  
2. System fetches available cleaners via APIs and CleanConnect database  
3. User filters by service type and availability  
4. Reviews cleaner profiles → selects one → books appointment  
5. Payment processed securely  
6. Notifications sent to both user and cleaner  
7. After completion → user leaves rating/review  

---

## 9. Local Enhancements

- Highlight **“Local Worcester Professionals”** badge  
- Include cleaner coverage for:
  - Lake Quinsigamond
  - Shrewsbury Street
  - Vernon Hill
  - Greendale  
- Integrate with **Worcester Telegram & Gazette classifieds** for onboarding local independent cleaners  

---

## 10. Future Additions

- AI-based cleaner matching (“Your ideal cleaner, based on your reviews & habits”)  
- Integration with Worcester’s local Facebook business pages  
- Multi-unit property management dashboard  
- Loyalty and referral system for repeat clients  

---

## 11. Open Questions

- Should Worcester cleaners be manually verified before listing?  
- Should pricing be dynamic (based on demand/time slots)?  
- Should we allow cleaners to set travel limits (e.g., 10-mile radius)?  

---

## 12. Milestones

| Phase | Deliverable | Target Date |
|--------|--------------|-------------|
| Phase 1 | MVP (local cleaner search + booking) | Month 1–2 |
| Phase 2 | Payments, verification, and reviews | Month 3 |
| Phase 3 | Local marketing launch (Worcester area) | Month 4 |
| Phase 4 | Expansion to surrounding ZIPs (01605, 01545, 01583) | Month 5 |

---

## 13. Stakeholders

- **Product Owner:** You (Requester)  
- **Dev Team:** Full-stack web + mobile engineers  
- **UX/UI Designer:** Worcester market focus  
- **Local Ops Lead:** Manage onboarding and verification of Worcester-area cleaners  

---

## 14. Success Statement

> “In Worcester, MA (01604), a homeowner should be able to find, verify, and book a trusted cleaner within 3 minutes — and know they’re supporting a local professional.”

---
