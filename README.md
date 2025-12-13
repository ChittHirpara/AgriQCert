# AgriQCert - Agricultural Quality Certification Portal

[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-19+-blue.svg)](https://reactjs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-8+-brightgreen.svg)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)

**AgriQCert** is a comprehensive web-based platform designed to streamline agricultural product certification, inspection, and verification. The platform digitizes the entire process, enabling exporters to submit batches for quality assessment, QA agencies to conduct inspections and issue certificates, and importers to instantly verify product authenticity.

![AgriQCert Portal Dashboard](https://res.cloudinary.com/dprcvoo9b/image/upload/v1765475320/Screenshot_2025-12-11_231700_fxssub.png)

---

## 🌐 Quick Links

- **Frontend Portal**: https://agri-q-cert.vercel.app/
- **Backend API**: https://agriqcert-1.onrender.com/

---

## 💡 Solution Overview

AgriQCert replaces manual, paper-based certification with a secure, digital ecosystem:

- **Digitized Certification**: Eliminates 7-10 day delays by streamlining the entire inspection workflow into a centralized platform with standardized quality parameters and instant verification
- **Tamper-Proof Credentials**: Issues cryptographically signed digital certificates with QR codes, preventing fraud while enabling real-time traceability from farm to destination

---

## 🚀 Key Features & User Workflows

### Exporters
**Workflow**: Register as an exporter → Create and submit agricultural batches with product details and documentation → Track real-time certification status (Submitted → Under Inspection → Certified → Rejected) → Download digital certificates with QR codes → Manage purchase orders received from importers → Update order status (Pending → Shipped → Completed).

**What Exporters Can Do**:
- Submit multiple batches with product type, quantity, origin location, and export destination
- Upload lab reports, certifications, quality test documents, and product photographs
- Monitor batch progress in real-time with status notifications
- Access inspection results and quality assessment reports
- Download cryptographically signed digital certificates
- Generate and share QR codes with international partners
- Receive purchase orders from importers and manage order fulfillment
- View order history and export analytics

### QA Agencies
**Workflow**: Register as a QA agency → Receive batch inspection requests from exporters → Review pending inspections in queue → Conduct comprehensive quality assessments → Record standardized quality parameters (moisture content, pesticide residue levels, organic certification status, ISO compliance codes) → Make pass/fail decisions → Issue digital certificates with cryptographic signatures and timestamps → Maintain complete audit trails for compliance and accountability.

**What QA Agencies Can Do**:
- Access all pending batches requiring inspection with exporter details
- Schedule and manage inspection timelines
- Record detailed quality measurements and test results
- Input standardized parameters ensuring consistency across agencies
- Review historical inspection data and trends
- Issue official digital certificates upon batch approval
- Reject batches with detailed reason documentation
- Maintain audit logs of all actions with timestamps
- View inspection analytics and certificate issuance reports

### Importers & Customs
**Workflow**: Register as an importer → Access public certificate verification portal → Scan QR codes or enter certificate IDs for instant authentication → View complete product information, quality parameters, and issuer credentials → Verify batch authenticity and compliance status → Browse available certified batches from different exporters → Place purchase orders with specific quantity and delivery requirements → Track shipment status in real-time → Confirm delivery and maintain purchase history.

**What Importers Can Do**:
- Instantly verify any certificate by scanning QR code without manual intervention
- View complete batch details including product type, quantity, origin, and destination
- Access quality assessment results from QA agencies
- Verify issuer authenticity and check certificate validity status
- Search and filter certified batches by product type or exporter
- Place purchase orders directly from the platform
- Communicate with exporters regarding orders
- Track shipment progress from warehouse to destination
- Maintain complete transaction history and documentation
- Generate compliance reports for customs authorities

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
