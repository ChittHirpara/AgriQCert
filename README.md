# AgriQCert - Agricultural Quality Certification Portal

[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-19+-blue.svg)](https://reactjs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-8+-brightgreen.svg)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)

**AgriQCert** is a comprehensive web-based platform designed to streamline the agricultural product certification, inspection, and verification process. The platform enables exporters to submit product batches for quality assessment, QA agencies to conduct inspections and issue digital certificates, and importers/customs authorities to instantly verify product authenticity through QR codes.

![AgriQCert Portal Dashboard](https://res.cloudinary.com/dprcvoo9b/image/upload/v1765475320/Screenshot_2025-12-11_231700_fxssub.png)


---

## 📋 Table of Contents

- [Problem Statement](#problem-statement)
- [Solution Overview](#solution-overview)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [Project Architecture](#project-architecture)
- [Installation & Setup](#installation--setup)
- [Configuration](#configuration)
- [Project Structure](#project-structure)
- [API Endpoints](#api-endpoints)
- [User Roles & Workflows](#user-roles--workflows)
- [Database Schema](#database-schema)
- [Frontend Components](#frontend-components)
- [Running the Application](#running-the-application)
- [Development Guidelines](#development-guidelines)
- [Troubleshooting](#troubleshooting)
- [Support & Contact](#support--contact)

---

## 🎯 Problem Statement

The agricultural export sector faces critical operational and administrative challenges:

- **Manual Process Inefficiency**: Paper-based certification processes require 7-10 business days, creating bottlenecks
- **Quality Control Inconsistency**: Multiple inspection agencies lack standardized quality parameters and documentation
- **Certificate Fraud Risk**: Paper certificates are susceptible to forgery and duplication
- **Verification Delays**: Importers and customs authorities spend significant time verifying legitimacy
- **Data Fragmentation**: No centralized platform for tracking product journey from farm to destination
- **Compliance Documentation**: Exporters struggle to maintain consistent documentation across different markets

## 💡 Solution Overview

AgriQCert provides an **end-to-end digital certification ecosystem** that:

- ✅ **Digitizes** the entire inspection and certification workflow
- ✅ **Standardizes** quality parameters and documentation across all agencies
- ✅ **Secures** certificates with cryptographic authentication and QR codes
- ✅ **Enables** instant verification without manual intervention
- ✅ **Centralizes** all batch information and certification history
- ✅ **Tracks** complete product traceability from submission to delivery
- ✅ **Reduces** certification turnaround time from 7-10 days to 24-48 hours

---

## 🚀 Key Features

### For Exporters
- **Batch Submission**: Submit agricultural product batches with comprehensive details
- **Document Management**: Upload lab reports, certifications, and supporting documents
- **Real-Time Tracking**: Monitor batch status throughout the certification lifecycle (Submitted → Under Inspection → Certified → Rejected)
- **Certificate Access**: Download digital certificates and generate QR codes for distribution
- **Historical Records**: View past certifications and inspection reports
- **Order Management**: Receive purchase orders from importers and manage order status

### For QA Agencies
- **Inspection Queue**: View and manage all pending inspection requests
- **Quality Assessment**: Record standardized quality parameters:
  - Moisture content measurements
  - Pesticide residue detection
  - Organic certification status
  - ISO compliance codes
- **Digital Certification**: Issue official digital certificates with digital signatures
- **Inspection Reports**: Generate detailed inspection reports with timestamp records
- **Agency Accountability**: All actions are logged with digital signatures for compliance

### For Importers & Customs Authorities
- **Instant Verification**: Scan QR codes or enter certificate IDs for immediate authentication
- **Certificate Validation**: Verify issuer authenticity and certificate legitimacy
- **Product Information**: Access complete batch details and quality parameters
- **Status Monitoring**: Check shipment status in real-time
- **Place Orders**: Send purchase orders to exporters with quantity and terms

### For Administrators
- **User Management**: Manage user accounts across all roles
- **Agency Verification**: Verify and approve QA agencies
- **System Analytics**: Monitor platform usage and certification trends
- **Data Integrity**: Ensure compliance and audit trails

---

## 🛠️ Technology Stack

| Layer | Technology | Version | Purpose |
|-------|-----------|---------|---------|
| **Frontend Framework** | React | 19.2.0 | Dynamic UI and interactive components |
| **Frontend Router** | React Router DOM | 7.9.6 | Client-side routing and navigation |
| **Frontend Build Tool** | Vite | 7.2.5 | Fast build and development server |
| **Styling Framework** | Tailwind CSS | 3.4.17 | Utility-first CSS framework |
| **Animation Library** | Framer Motion | 12.23.24 | Smooth animations and transitions |
| **HTTP Client** | Axios | 1.13.2 | API communication and requests |
| **QR Code Generation** | QRCode.react | 4.2.0 | QR code creation for certificates |
| **Data Visualization** | Recharts | 3.4.1 | Interactive charts and graphs |
| **Toast Notifications** | React Hot Toast | 2.6.0 | User feedback notifications |
| **Icon Library** | Lucide React | 0.554.0 | Lightweight SVG icons |
| **3D Visualization** | React Globe.gl | 2.37.0 | Interactive global network map |
| **Canvas Processing** | HTML2Canvas | 1.4.1 | Screenshot and PDF generation |
| **Encryption** | CryptoJS | 4.2.0 | Client-side encryption utilities |
| **Animation Effects** | Canvas Confetti | 1.9.4 | Celebration animations |
| **Backend Runtime** | Node.js | 18+ | Server-side JavaScript execution |
| **Backend Framework** | Express.js | 5.1.0 | RESTful API server |
| **Database** | MongoDB | 8.0+ | NoSQL document database |
| **ODM** | Mongoose | 8.20.1 | MongoDB object data modeling |
| **Authentication** | JWT & Bcrypt | 9.0.2 & 3.0.3 | Secure user authentication |
| **File Upload** | Multer | 2.0.2 | Multipart form data handling |
| **CORS** | CORS | 2.8.5 | Cross-origin resource sharing |
| **Environment Config** | Dotenv | 17.2.3 | Environment variable management |
| **Development Monitor** | Nodemon | 3.1.11 | Auto-restart on file changes |

---

## 🏗️ Project Architecture

```
AgriQCert/
│
├── client/                          # React Frontend Application
│   ├── src/
│   │   ├── pages/                   # Main route pages
│   │   │   ├── Landing.jsx          # Public landing page
│   │   │   ├── Login.jsx            # User authentication
│   │   │   ├── Dashboard.jsx        # Role-based main dashboard
│   │   │   └── Verify.jsx           # Certificate verification (public)
│   │   │
│   │   ├── components/              # Reusable React components
│   │   │   ├── ExporterDashboard.jsx    # Batch submission & tracking
│   │   │   ├── QADashboard.jsx          # Inspection management
│   │   │   ├── ImporterDashboard.jsx    # Order management & verification
│   │   │   ├── BlockchainAudit.jsx      # Audit trail visualization
│   │   │   ├── DigitalPassport.jsx      # Certificate details display
│   │   │   ├── Documentation.jsx        # System documentation
│   │   │   ├── LiveTracker.jsx          # Real-time batch tracking
│   │   │   ├── MarketAnalysis.jsx       # Analytics dashboard
│   │   │   └── GlobalNetwork.jsx        # Network visualization
│   │   │
│   │   ├── assets/                  # Images, icons, static files
│   │   ├── App.jsx                  # Main application component
│   │   ├── App.css                  # Global application styles
│   │   ├── index.css                # Base CSS styles
│   │   └── main.jsx                 # Application entry point
│   │
│   ├── public/                      # Static public files
│   ├── index.html                   # HTML template
│   ├── vite.config.js               # Vite configuration
│   ├── tailwind.config.js            # Tailwind CSS configuration
│   ├── postcss.config.js            # PostCSS configuration
│   ├── eslint.config.js             # ESLint rules
│   └── package.json                 # Frontend dependencies
│
├── server/                          # Node.js Express Backend
│   ├── models/                      # MongoDB data schemas
│   │   ├── User.js                  # User account schema
│   │   ├── Batch.js                 # Product batch schema
│   │   ├── Inspection.js            # Quality inspection schema
│   │   └── Certificate.js           # Digital certificate schema
│   │
│   ├── routes/                      # API route handlers
│   │   ├── auth.js                  # Authentication endpoints
│   │   ├── batches.js               # Batch management endpoints
│   │   └── inspections.js           # Inspection endpoints
│   │
│   ├── uploads/                     # File storage directory
│   ├── index.js                     # Server entry point
│   ├── package.json                 # Backend dependencies
│   ├── .env                         # Environment variables
│   ├── seed.js                      # Database seed script
│   └── reset.js                     # Database reset script
│
└── README.md                        # This file

```

---

## 📦 Installation & Setup

### Prerequisites

Ensure you have the following installed on your system:

- **Node.js**: Version 18 or higher ([Download](https://nodejs.org/))
- **npm**: Comes with Node.js (verify with `npm -v`)
- **MongoDB**: Local installation or MongoDB Atlas account ([Setup Guide](https://www.mongodb.com/docs/manual/installation/))
- **Git**: For version control (optional, [Download](https://git-scm.com/))

### Step 1: Clone or Extract Project

```bash
# If cloned from Git
git clone https://github.com/your-organization/agriqcert.git
cd agriqcert

# If downloaded as zip
unzip agriqcert.zip
cd agriqcert
```

### Step 2: Backend Setup

```bash
cd server

# Install dependencies
npm install

# Create .env file (see Configuration section below)
copy .env.example .env
# OR manually create .env with required variables

# Optional: Seed database with sample data
npm run seed

# Start development server
npm run dev

# Server should start at http://localhost:5000
```

### Step 3: Frontend Setup (New Terminal)

```bash
cd client

# Install dependencies
npm install

# Start development server
npm run dev

# Frontend should start at http://localhost:5173
```

### Step 4: Access the Application

- **Frontend**: Navigate to `http://localhost:5173`
- **Backend API**: `http://localhost:5000`
- **Landing Page**: `http://localhost:5173/`
- **Portal/Login**: `http://localhost:5173/portal`
- **Verification**: `http://localhost:5173/verify/[certificate-id]`

---

## ⚙️ Configuration

### Server Environment Variables

Create a `.env` file in the `server/` directory with the following variables:

```env
# Server Configuration
PORT=5000
NODE_ENV=development

# MongoDB Configuration
MONGO_URI=mongodb://localhost:27017/agriqcert
# OR for MongoDB Atlas:
# MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/agriqcert

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_here_change_this_in_production
JWT_EXPIRES_IN=7d

# Frontend Configuration
FRONTEND_URL=http://localhost:5173

# File Upload Configuration
MAX_FILE_SIZE=5242880  # 5MB in bytes
UPLOAD_DIR=./uploads
```

### Frontend Configuration

Create a `.env` file in the `client/` directory if needed:

```env
VITE_API_URL=http://localhost:5000/api
VITE_APP_NAME=AgriQCert
VITE_APP_VERSION=1.0.0
```

---

## 📁 Project Structure - Detailed Explanation

### Backend Models

#### User Model (`server/models/User.js`)
Stores user account information with role-based access control.

```javascript
{
  username: String,           // Unique username for login
  email: String,              // User email address
  password: String,           // Hashed password
  role: String,               // 'exporter' | 'qa' | 'admin' | 'importer'
  walletAddress: String,      // Decentralized identity
  createdAt: Date             // Account creation timestamp
}
```

#### Batch Model (`server/models/Batch.js`)
Represents agricultural product batches submitted for certification.

```javascript
{
  exporter: ObjectId,         // Reference to exporting user
  productType: String,        // Type of agricultural product
  quantity: String,           // Batch quantity
  location: String,           // Origin location
  destination: String,        // Export destination
  status: String,             // 'Submitted' | 'Under Inspection' | 'Certified' | 'Rejected'
  orderedBy: ObjectId,        // Importer who ordered (if any)
  orderStatus: String,        // 'None' | 'Pending' | 'Shipped' | 'Declined'
  attachments: Array,         // Document files array
  createdAt: Date             // Submission timestamp
}
```

#### Inspection Model (`server/models/Inspection.js`)
Records quality assessment details performed by QA agencies.

```javascript
{
  batch: ObjectId,            // Reference to batch being inspected
  qaAgency: ObjectId,         // QA agency conducting inspection
  moisture: String,           // Moisture content measurement
  pesticide: String,          // Pesticide residue status
  organicStatus: String,      // Organic certification status
  isoCode: String,            // ISO compliance code
  result: String,             // 'Pass' | 'Fail'
  inspectionDate: Date        // Inspection timestamp
}
```

#### Certificate Model (`server/models/Certificate.js`)
Stores issued digital certificates for verified batches.

```javascript
{
  batch: ObjectId,            // Reference to certified batch
  vcData: Object,             // Verifiable credential data
  issuedAt: Date,             // Certificate issuance timestamp
  isRevoked: Boolean          // Revocation status
}
```

### Frontend Pages

#### Landing Page (`client/src/pages/Landing.jsx`)
- Public homepage with platform overview
- Feature highlights and benefits
- Call-to-action for portal access
- System information display

#### Login Page (`client/src/pages/login.jsx`)
- User authentication interface
- Role selection during registration
- JWT token management
- Automatic user session restoration

#### Dashboard (`client/src/pages/Dashboard.jsx`)
- Role-based routing to appropriate dashboard
- User information display
- Logout functionality
- Navigation and session management

#### Verification Page (`client/src/pages/Verify.jsx`)
- Public certificate verification
- QR code scanner integration
- Certificate authenticity confirmation
- Product and quality details display

### Frontend Components

#### ExporterDashboard (`client/src/components/ExporterDashboard.jsx`)
**Purpose**: Batch submission and tracking interface for exporters

**Features**:
- Create new batch submissions
- Upload supporting documentation
- Track batch certification status
- View inspection results
- Download certificates and QR codes
- Receive and manage purchase orders from importers

#### QADashboard (`client/src/components/QADashboard.jsx`)
**Purpose**: Quality inspection management for QA agencies

**Features**:
- View pending inspection queue
- Record quality measurements
- Input inspection parameters (moisture, pesticides, organic status)
- Pass/fail decision making
- Issue digital certificates
- View inspection history

#### ImporterDashboard (`client/src/components/ImporterDashboard.jsx`)
**Purpose**: Purchase management and certificate verification for importers

**Features**:
- Browse available certified batches
- Place purchase orders with exporters
- Track order status
- Verify certificate authenticity
- View product quality parameters
- Access shipment information

#### BlockchainAudit (`client/src/components/BlockchainAudit.jsx`)
- Displays audit trail of all certification actions
- Shows who performed each action and when
- Immutable transaction history visualization

#### DigitalPassport (`client/src/components/DigitalPassport.jsx`)
- Displays complete product information
- Shows certification and inspection details
- Quality parameters summary
- Exporter and QA agency credentials

#### Documentation (`client/src/components/Documentation.jsx`)
- In-app user guide
- API documentation
- Feature explanations
- Troubleshooting assistance

#### LiveTracker (`client/src/components/LiveTracker.jsx`)
- Real-time batch status updates
- Current location and destination tracking
- Inspection progress monitoring
- Estimated delivery timeline

#### MarketAnalysis (`client/src/components/MarketAnalysis.jsx`)
- Statistical dashboards
- Certification trends and analytics
- Product type analysis
- Geographic export distribution

#### GlobalNetwork (`client/src/components/GlobalNetwork.jsx`)
- Interactive 3D globe visualization
- Export destination mapping
- Network connectivity display
- International trade flow visualization

---

## 🔌 API Endpoints

### Base URL
```
http://localhost:5000/api
```

### Authentication Endpoints

| Method | Endpoint | Description | Auth Required | Payload |
|--------|----------|-------------|---|---------|
| POST | `/auth/register` | Register new user | No | `{ username, email, password, role }` |
| POST | `/auth/login` | Authenticate user | No | `{ email, password }` |
| GET | `/auth/me` | Get current user | Yes | - |

**Example Registration:**
```bash
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{
    "username": "farmer_john",
    "email": "john@farm.com",
    "password": "SecurePass123",
    "role": "exporter"
  }'
```

**Example Login:**
```bash
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{
    "email": "john@farm.com",
    "password": "SecurePass123"
  }'
```

### Batch Management Endpoints

| Method | Endpoint | Description | Auth | Payload |
|--------|----------|-------------|------|---------|
| POST | `/batches` | Create new batch | Yes | `{ productType, quantity, location, destination }` |
| GET | `/batches` | Get all user batches | Yes | - |
| GET | `/batches/:id` | Get batch details | Yes | - |
| PUT | `/batches/:id` | Update batch | Yes | `{ status, attachment, etc }` |
| DELETE | `/batches/:id` | Delete batch | Yes | - |

**Example Create Batch:**
```bash
curl -X POST http://localhost:5000/api/batches \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_JWT_TOKEN" \
  -d '{
    "productType": "Basmati Rice",
    "quantity": "1000 kg",
    "location": "Punjab, India",
    "destination": "USA"
  }'
```

### Inspection Endpoints

| Method | Endpoint | Description | Auth | Payload |
|--------|----------|-------------|------|---------|
| POST | `/inspections/start/:batchId` | Begin inspection | Yes | - |
| PUT | `/inspections/:id` | Submit inspection results | Yes | `{ moisture, pesticide, organicStatus, isoCode, result }` |
| GET | `/inspections/pending` | Get pending inspections | Yes | - |
| GET | `/inspections/:batchId` | Get batch inspection | Yes | - |

**Example Submit Inspection:**
```bash
curl -X PUT http://localhost:5000/api/inspections/INSPECTION_ID \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_JWT_TOKEN" \
  -d '{
    "moisture": "12.5%",
    "pesticide": "Not Detected",
    "organicStatus": "Certified Organic",
    "isoCode": "ISO-9001",
    "result": "Pass"
  }'
```

---

## 👥 User Roles & Workflows

### 1. Exporter Workflow

**Role**: Agricultural product exporter/farmer

**Primary Workflow**:
```
Login → Create Batch → Upload Documents → Wait for Inspection 
→ Receive Inspection Results → Download Certificate → Place QR Code
→ Send to Importer → Track Order Status
```

**Key Actions**:
- Submit product batches with detailed specifications
- Upload lab reports, certifications, and photographs
- Monitor inspection progress in real-time
- Download and share digital certificates
- Receive purchase orders from importers
- Update order status (Pending → Shipped → Completed)

**Required Information**:
- Product type and quantity
- Batch origin location
- Export destination country
- Supporting documentation files

### 2. QA Agency Workflow

**Role**: Quality assurance and inspection authority

**Primary Workflow**:
```
Login → View Pending Inspections → Conduct Assessment → Record Parameters
→ Make Pass/Fail Decision → Issue Digital Certificate → Maintain Records
```

**Key Actions**:
- Review submitted batches requiring inspection
- Conduct laboratory quality assessments
- Record standardized quality parameters
- Issue digital certificates upon passing
- Maintain audit trails of all inspections
- View historical inspection records

**Quality Parameters**:
- Moisture content percentage
- Pesticide residue levels
- Organic certification status
- ISO compliance codes
- Overall pass/fail determination

### 3. Importer/Customs Workflow

**Role**: Product purchaser and customs authority

**Primary Workflow**:
```
Login → Browse Certified Products → Verify Certificate → Place Order
→ Track Shipment → Receive Delivery Confirmation
```

**Key Actions**:
- Search and view available certified batches
- Verify certificate authenticity via QR code
- Review product quality parameters
- Place purchase orders with exporters
- Monitor order and shipment status
- Confirm delivery upon arrival

**Verification Process**:
- Scan QR code or enter certificate ID
- View certificate details and issuer information
- Confirm certificate validity and authenticity
- Access complete batch traceability

### 4. Administrator Workflow

**Role**: System administrator and platform manager

**Primary Workflow**:
```
Login → Manage Users → Monitor System → Review Analytics
→ Handle Disputes → Maintain Database Integrity
```

**Key Actions**:
- Create and manage user accounts
- Verify QA agency credentials
- Monitor platform metrics and usage
- Handle user disputes and issues
- Maintain system integrity and backups
- Generate compliance reports

---

## 🗄️ Database Schema

### User Collection

```javascript
db.users.findOne()
{
  _id: ObjectId,
  username: "farmer_john",
  email: "john@farm.com",
  password: "$2a$10$...", // bcrypt hashed
  role: "exporter",
  walletAddress: "did:ethr:0x...",
  createdAt: ISODate("2024-01-15T10:30:00Z")
}
```

### Batches Collection

```javascript
db.batches.findOne()
{
  _id: ObjectId,
  exporter: ObjectId("user_id"),
  productType: "Basmati Rice Premium Grade",
  quantity: "1000 kg",
  location: "Punjab, India",
  destination: "USA",
  status: "Under Inspection",
  orderedBy: ObjectId("importer_id") || null,
  orderStatus: "Pending",
  attachments: [
    {
      fileUrl: "/uploads/lab_report_001.pdf",
      fileType: "lab_report"
    },
    {
      fileUrl: "/uploads/batch_photo.jpg",
      fileType: "photo"
    }
  ],
  createdAt: ISODate("2024-01-15T11:00:00Z")
}
```

### Inspections Collection

```javascript
db.inspections.findOne()
{
  _id: ObjectId,
  batch: ObjectId("batch_id"),
  qaAgency: ObjectId("qa_user_id"),
  moisture: "12.5%",
  pesticide: "Not Detected",
  organicStatus: "Certified Organic",
  isoCode: "ISO-9001:2015",
  result: "Pass",
  inspectionDate: ISODate("2024-01-16T14:30:00Z")
}
```

### Certificates Collection

```javascript
db.certificates.findOne()
{
  _id: ObjectId,
  batch: ObjectId("batch_id"),
  vcData: {
    "@context": ["https://www.w3.org/2018/credentials/v1"],
    "type": ["VerifiableCredential", "AgriculturalCertificate"],
    "issuer": {
      "id": "did:certifarm:qa-lab-001",
      "name": "Certified QA Laboratory"
    },
    "credentialSubject": {
      "product": {
        "name": "Basmati Rice",
        "batchId": "BATCH-2024-001"
      },
      "qualityCertification": {
        "grade": "A",
        "moisture": "12.5%",
        "pesticideStatus": "Not Detected"
      }
    },
    "proof": {
      "type": "RsaSignature2018",
      "created": ISODate("2024-01-16T15:00:00Z"),
      "signatureValue": "signature_hash_here"
    }
  },
  issuedAt: ISODate("2024-01-16T15:00:00Z"),
  isRevoked: false
}
```

---

## 🎨 Frontend Components - Detailed Reference

### Component Hierarchy

```
App.jsx (Main Router)
├── Landing.jsx (Public Route: /)
├── Login.jsx (Public Route: /portal)
│   └── User Authentication
│       ├── Register New User
│       └── Login Existing User
├── Dashboard.jsx (Protected Route: /portal)
│   ├── ExporterDashboard (Role: exporter)
│   ├── QADashboard (Role: qa)
│   ├── ImporterDashboard (Role: importer)
│   └── AdminDashboard (Role: admin - Coming Soon)
└── Verify.jsx (Public Route: /verify/:id)
    └── Certificate Verification
```

### Component Features Summary

| Component | Purpose | Users | Key Features |
|-----------|---------|-------|--------------|
| ExporterDashboard | Batch management | Exporters | Submit, track, download certificates |
| QADashboard | Inspection management | QA Agencies | Review, assess, issue certificates |
| ImporterDashboard | Order management | Importers | Browse, order, verify products |
| BlockchainAudit | Audit trails | All roles | View action history |
| DigitalPassport | Certificate display | All roles | Product and quality info |
| LiveTracker | Status tracking | All roles | Real-time batch updates |
| MarketAnalysis | Analytics | Admins | Trends and statistics |
| GlobalNetwork | Network map | All roles | Geographic distribution |

---

## ▶️ Running the Application

### Development Mode

#### Terminal 1 - Start Backend Server
```bash
cd server
npm run dev

# Output:
# ✅ MongoDB Connected
# Server running on port 5000
```

#### Terminal 2 - Start Frontend Development Server
```bash
cd client
npm run dev

# Output:
# VITE v7.2.5 running at:
# ➜ Local: http://localhost:5173/
```

### Production Build

#### Build Frontend
```bash
cd client
npm run build

# Output:
# built in 45.23s
# dist/ folder contains optimized files
```

#### Production Server Start
```bash
cd server
NODE_ENV=production npm start

# Server runs without auto-reload (nodemon not used)
```

---

## 🔧 Development Guidelines

### Code Style & Standards

#### JavaScript/Node.js Conventions
- Use `const` and `let` instead of `var`
- Follow ES6+ features
- Use async/await for asynchronous operations
- Add JSDoc comments for functions

```javascript
/**
 * Creates a new batch submission
 * @param {string} productType - Type of agricultural product
 * @param {string} quantity - Batch quantity
 * @returns {Promise<Object>} - Created batch object
 */
async function createBatch(productType, quantity) {
  // Implementation
}
```

#### React Best Practices
- Use functional components with hooks
- Keep components modular and reusable
- Lift state up when needed
- Use proper key props in lists

```jsx
function BatchList({ batches }) {
  return (
    <div>
      {batches.map(batch => (
        <BatchCard key={batch._id} batch={batch} />
      ))}
    </div>
  );
}
```

#### CSS with Tailwind
- Use utility classes instead of custom CSS
- Follow mobile-first approach
- Use consistent spacing and colors
- Leverage Tailwind's responsive prefixes

```jsx
<div className="w-full md:w-1/2 lg:w-1/3 p-4 md:p-6">
  <h1 className="text-lg md:text-2xl font-bold">Heading</h1>
</div>
```

### Environment Management
- Never commit `.env` files
- Use `.env.example` as template
- Keep sensitive keys in environment variables
- Rotate JWT secrets in production

### Database Best Practices
- Index frequently queried fields
- Use relationships via ObjectId references
- Implement schema validation
- Maintain data consistency

### API Development
- Use consistent HTTP status codes
- Return meaningful error messages
- Implement proper validation
- Use middleware for cross-cutting concerns

### Testing Recommendations
- Test API endpoints with tools like Postman
- Test frontend components in isolation
- Implement unit tests for critical functions
- Perform integration testing before deployment

---

## 🐛 Troubleshooting

### Common Issues & Solutions

#### Issue: MongoDB Connection Error
**Symptoms**: Error connecting to MongoDB in server logs

**Solutions**:
```bash
# 1. Check if MongoDB is running
mongod --version

# 2. Start MongoDB service (Windows)
net start MongoDB

# 3. Verify MONGO_URI in .env file
MONGO_URI=mongodb://localhost:27017/agriqcert

# 4. For MongoDB Atlas
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/agriqcert?retryWrites=true&w=majority
```

#### Issue: Port Already in Use
**Symptoms**: `Error: listen EADDRINUSE :::5000`

**Solutions**:
```bash
# Find process using port 5000
# Windows
netstat -ano | findstr :5000

# Kill process
taskkill /PID <PID_NUMBER> /F

# Or change port in .env
PORT=5001
```

#### Issue: CORS Errors in Frontend
**Symptoms**: Frontend cannot reach backend API

**Solutions**:
```javascript
// server/index.js - Verify CORS configuration
app.use(cors({
  origin: process.env.FRONTEND_URL || 'http://localhost:5173',
  credentials: true
}));
```

#### Issue: Authentication Token Expired
**Symptoms**: Automatic logout during session

**Solutions**:
```bash
# Increase JWT expiration in .env
JWT_EXPIRES_IN=30d

# Or implement refresh token mechanism
```

#### Issue: File Upload Failures
**Symptoms**: Documents fail to upload

**Solutions**:
```javascript
// Check multer configuration
const maxFileSize = 5242880; // 5MB

// Ensure uploads directory exists
const uploadDir = path.join(__dirname, 'uploads');
if (!fs.existsSync(uploadDir)) {
  fs.mkdirSync(uploadDir);
}
```

#### Issue: Blank Frontend Page
**Symptoms**: Frontend loads but no content displayed

**Solutions**:
```bash
# 1. Clear browser cache (Ctrl+Shift+Delete)
# 2. Check console for errors (F12)
# 3. Ensure Vite server is running
# 4. Verify API URL configuration
```

---

## 📝 Database Initialization

### Seed Sample Data

The project includes a seed script to populate sample data:

```bash
cd server
npm run seed
```

This creates:
- Sample users (exporter, QA agency, importer, admin)
- Example batches
- Test inspection records

### Reset Database

To clear all data and start fresh:

```bash
cd server
npm run reset
```

**Warning**: This action is irreversible. Use only in development environment.

---

## 🔐 Security Considerations

### Authentication & Authorization
- All API endpoints (except `/auth/register`, `/auth/login`, and `/verify/:id`) require JWT authentication
- JWT tokens are stored in localStorage
- Passwords are hashed using bcryptjs before storage
- Implement token refresh mechanism for long sessions

### Data Protection
- Validate all user inputs on both frontend and backend
- Sanitize file uploads to prevent malicious code
- Use HTTPS in production
- Implement rate limiting on API endpoints

### Best Practices
- Change `JWT_SECRET` in production
- Use strong, unique passwords
- Implement audit logging for critical operations
- Regular database backups
- Use MongoDB Atlas for managed security

---

## 📊 Performance Optimization

### Frontend
- Code splitting with React.lazy()
- Image optimization and lazy loading
- Minification in production build
- Browser caching strategies

### Backend
- Database indexing on frequently queried fields
- Pagination for large data sets
- Caching frequently accessed data
- Connection pooling for MongoDB

### Build & Deployment
```bash
# Production frontend build
cd client
npm run build
# Creates optimized dist/ folder

# Verify build size
npm run build --report

# Production backend
NODE_ENV=production npm start
```

---

## 📞 Support & Contact

### Getting Help

**For Technical Issues**:
1. Check the Troubleshooting section above
2. Review browser console (F12) and server logs
3. Check MongoDB connection and data
4. Verify environment variables

**For Feature Requests**:
- Document the feature with use case
- Provide implementation suggestions
- Include affected user roles

**For Bug Reports**:
- Describe the issue clearly
- Provide steps to reproduce
- Include error messages and logs
- Note the user role and action taken

### Development Team Communication

- **Documentation**: Refer to this README
- **Code Updates**: Use version control commits
- **Deployment**: Notify team before production deployment

---

## 📜 License

This project is licensed under the ISC License.

---

## 🙏 Acknowledgments

- Built with modern web technologies
- Inspired by agricultural export requirements
- Designed for seamless quality certification workflows

---

## 📋 Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | 2025-11-26 | Initial release with core features |

---

## ✅ Deployment Checklist

Before deploying to production:

- [ ] Update `JWT_SECRET` with strong random key
- [ ] Configure MongoDB Atlas or production database
- [ ] Set `FRONTEND_URL` to production domain
- [ ] Enable HTTPS on all endpoints
- [ ] Implement rate limiting
- [ ] Set up error logging/monitoring
- [ ] Configure automated backups
- [ ] Test all user workflows
- [ ] Document deployment process
- [ ] Set up monitoring and alerts

---

**Last Updated**: December 2025  
**Maintained By**: Development Team  
**Status**: Active Development

For questions or support, please refer to the troubleshooting section or contact the development team.