# RideSphere

> A clean‑architecture, MERN‑stack ride‑sharing platform built with Next.js and TypeScript, designed for rapid monolithic delivery and seamless migration to microservices.

---

## 🚀 Project Overview

RideSphere connects **Riders** and **Drivers** in real time, offering secure authentication, dynamic ride matching, live tracking, and robust payment & analytics features.  
Built first as a monolith for MVP speed, then refactored into microservices following Uncle Bob’s Clean Architecture principles.

---

## 🎯 Key Features

1. **User Management**  
   - **Roles**: Rider & Driver  
   - Secure signup/login (email, phone, OTP)  
   - Profile & payment preferences  
   - KYC/driver verification workflow  

2. **Ride Matching & Booking**  
   - Geolocation‑powered ride requests  
   - Real‑time driver matching  
   - Scheduled & on‑demand rides  
   - Fare estimation  

3. **Live Tracking & Navigation**  
   - Real‑time driver location on map  
   - Route optimization (Google Maps API)  
   - Dynamic ETA updates  

4. **Payment & Fare Management**  
   - In‑app payments (cards, wallets, UPI)  
   - Detailed trip receipts & history  

5. **Notifications & Alerts**  
   - Push, SMS (optional), and email updates  
   - Trip summaries & promotions  

6. **Ratings & Reviews**  
   - Bidirectional feedback (riders ↔ drivers)  
   - Issue reporting  

7. **Ride History & Analytics**  
   - Complete trip logs  
   - Driver earnings dashboard  
   - Rider usage stats  

---

## 🏗️ Architecture & Folder Structure

**Phase 1: Monolithic Clean Architecture**  

```
ridesphere/
├── backend/
│   ├── src/
│   │   ├── domain/                # Core business entities & interfaces
│   │   ├── application/           # Use‑cases, services, DTOs (TypeScript)
│   │   ├── infrastructure/        # Database, third‑party API adapters
│   │   └── interfaces/            # Express controllers, routes
│   ├── tests/                     # Unit & integration tests
│   └── package.json
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── pages/                 # Next.js pages & API routes
│   │   ├── components/            # UI components
│   │   ├── hooks/                 # Custom React hooks
│   │   ├── context/               # State management (React Context / Redux)
│   │   └── styles/
│   ├── tsconfig.json
│   └── package.json
│
├── prisma/                        # Prisma schema & migrations (or Mongoose models)
├── docker-compose.yml
└── README.md

```



**Phase 2: Microservices Migration**  
- Split `backend/src` into services:  
  - **auth-service**, **rides-service**, **payments-service**, **notifications-service**, etc.  
- Each service retains the Clean Architecture layers.  
- Use a lightweight API gateway (e.g., Next.js API routes or Express gateway).  
- Communicate via REST or message broker (e.g., RabbitMQ).

---

## 🛠️ Tech Stack

- **Frontend:** Next.js, React, TypeScript, Tailwind CSS (or Chakra UI)  
- **Backend:** Node.js, TypeScript, Express.js  
- **Database:** MongoDB (via Mongoose) or PostgreSQL (via Prisma)  
- **Maps & Geolocation:** Google Maps API  
- **Auth & Payments:** JWT, Stripe, Razorpay/UPI SDKs  
- **Deployment:** Docker Compose → Kubernetes + Helm  
- **CI/CD:** GitHub Actions  
- **Monitoring:** Prometheus, Grafana  

---

