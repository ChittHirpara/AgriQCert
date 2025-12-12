# AgriQCert - Agricultural Quality Certification Portal

[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-19+-blue.svg)](https://reactjs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-8+-brightgreen.svg)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)

**AgriQCert** is a comprehensive web-based platform designed to streamline agricultural product certification, inspection, and verification. The platform digitizes the entire process, enabling exporters to submit batches for quality assessment, QA agencies to conduct inspections and issue certificates, and importers to instantly verify product authenticity.

![AgriQCert Portal Dashboard](https://res.cloudinary.com/dprcvoo9b/image/upload/v1765475320/Screenshot_2025-12-11_231700_fxssub.png)

---

## 💡 Solution Overview

AgriQCert replaces manual, paper-based certification with a secure, digital ecosystem:

- **Digitized Certification**: Eliminates 7-10 day delays by streamlining the entire inspection workflow into a centralized platform with standardized quality parameters and instant verification
- **Tamper-Proof Credentials**: Issues cryptographically signed digital certificates with QR codes, preventing fraud while enabling real-time traceability from farm to destination

---

## 🚀 Key Features

### Exporters
Submit agricultural batches with documentation, track certification status (Submitted → Under Inspection → Certified → Rejected), download digital certificates with QR codes, and manage purchase orders from importers.

### QA Agencies
Review pending inspections, record standardized quality parameters (moisture, pesticide residue, organic status, ISO compliance), issue digital certificates with timestamps, and maintain audit trails of all actions for compliance.

### Importers & Customs
Instantly verify certificates via QR code scanning or ID lookup, access complete product information and quality parameters, place purchase orders with exporters, and track shipment status in real-time.

---

## 🛠️ Technology Stack

| Component | Technology |
|-----------|------------|
| **Frontend** | React 19 with Vite |
| **Backend** | Node.js & Express.js |
| **Database** | MongoDB with Mongoose |
| **Authentication** | JWT & Bcrypt |
| **Styling** | Tailwind CSS |

---

## 📁 Frontend Structure

### Pages

- **Landing.jsx** - Public homepage with platform overview and feature highlights
- **Login.jsx** - User authentication and registration with role selection
- **Dashboard.jsx** - Role-based portal routing to appropriate dashboards
- **Verify.jsx** - Public certificate verification interface

### Components

- **ExporterDashboard** - Batch submission, document upload, status tracking, certificate download
- **QADashboard** - Inspection queue, quality assessment recording, digital certification
- **ImporterDashboard** - Certified batch browsing, order placement, shipment tracking
- **BlockchainAudit** - Audit trail visualization with action history
- **DigitalPassport** - Product and quality information display
- **Documentation** - In-app user guide and system information
- **LiveTracker** - Real-time batch status and delivery timeline
- **MarketAnalysis** - Analytics dashboard with trends and statistics
- **GlobalNetwork** - 3D globe visualization of export distribution

---

## 🔌 API Endpoints

### Base URL: `http://localhost:5000/api`

### Authentication

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/auth/register` | Register new user | No |
| POST | `/auth/login` | Authenticate user | No |
| GET | `/auth/me` | Get current user | Yes |

### Batch Management

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/batches` | Create new batch | Yes |
| GET | `/batches` | Get all batches | Yes |
| GET | `/batches/:id` | Get batch details | Yes |
| PUT | `/batches/:id` | Update batch | Yes |

### Inspections

| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/inspections/start/:batchId` | Begin inspection | Yes |
| PUT | `/inspections/:id` | Submit inspection results | Yes |
| GET | `/inspections/pending` | Get pending inspections | Yes |

---

## 📜 License

This project is licensed under the ISC License.

---

**Last Updated**: December 2025  
**Status**: Active Development
