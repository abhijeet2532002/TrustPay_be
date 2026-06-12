# 💳 Trustpay - Digital Wallet & Payment Platform

A scalable fintech wallet application built using the MERN Stack that enables users to securely manage wallets, transfer money, track transactions, and receive real-time notifications.

---

## 🚀 Project Overview

FinFlow is a fintech platform inspired by digital payment applications such as Paytm, PhonePe, and Google Pay.

The system is designed to provide secure and reliable financial transactions while demonstrating real-world backend architecture, system design concepts, and scalable application development.

### Key Objectives

- Secure user authentication
- Digital wallet management
- Peer-to-peer money transfer
- Transaction tracking and auditing
- Real-time notifications
- Scalable system architecture
- Event-driven communication

---

## 🏗️ High Level Architecture

```text
                +----------------+
                |   React Client |
                +--------+-------+
                         |
                  HTTPS/REST
                         |
                         ▼
                +----------------+
                | API Gateway    |
                | Express Server |
                +--------+-------+
                         |
      --------------------------------------
      |          |           |             |
      ▼          ▼           ▼             ▼

+-----------+ +----------+ +-----------+ +-------------+
| Auth      | | Wallet   | | Payment   | | Transaction |
| Service   | | Service  | | Service   | | Service     |
+-----------+ +----------+ +-----------+ +-------------+

      |            |            |
      --------------------------------
                     |
                     ▼

             +---------------+
             | MongoDB       |
             +---------------+

                     |
                     ▼

             +---------------+
             | Redis Cache   |
             +---------------+

                     |
                     ▼

             +---------------+
             | BullMQ Queue  |
             +---------------+

                     |
                     ▼

             +---------------+
             | Notification  |
             | Service       |
             +---------------+
```

---

# ✨ Features

## Authentication

- User Registration
- User Login
- JWT Authentication
- Refresh Token Support
- Password Encryption using bcrypt

## Wallet Management

- Create Wallet
- Wallet Balance Check
- Add Money
- Debit Money
- Credit Money

## Payments

- Send Money
- Receive Money
- Beneficiary Management
- Transfer Validation
- Duplicate Transaction Prevention

## Transactions

- Transaction History
- Transfer Records
- Credit Records
- Debit Records
- Refund Records
- Failed Transaction Tracking

## Notifications

- Money Added Alert
- Money Sent Alert
- Money Received Alert
- Failed Transaction Alert

## Administration

- User Monitoring
- Transaction Monitoring
- Audit Logs
- System Analytics

---

# 🛠️ Tech Stack

## Frontend

- React.js
- Redux Toolkit
- Axios
- Tailwind CSS

## Backend

- Node.js
- Express.js

## Database

- MongoDB
- Mongoose

## Authentication

- JWT
- bcrypt

## Caching

- Redis

## Queue Management

- BullMQ

## DevOps

- Docker
- GitHub Actions
- Nginx

---

# 📂 Project Structure

```bash
finflow/
│
├── client/
│   ├── src/
│   ├── public/
│
├── server/
│   ├── src/
│   │
│   ├── modules/
│   │   ├── auth/
│   │   ├── wallet/
│   │   ├── payment/
│   │   ├── transaction/
│   │   ├── beneficiary/
│   │   └── notification/
│   │
│   ├── config/
│   ├── middlewares/
│   ├── utils/
│   ├── jobs/
│   ├── routes/
│   └── app.js
│
├── docs/
│   ├── HLD.md
│   └── LLD.md
│
├── docker-compose.yml
├── README.md
└── .env
```

---

# 🗄️ Database Design

## User Collection

```json
{
  "_id": "ObjectId",
  "name": "Abhijeet Kumar",
  "email": "user@email.com",
  "phone": "9876543210",
  "password": "hashedPassword",
  "role": "USER"
}
```

## Wallet Collection

```json
{
  "_id": "ObjectId",
  "userId": "ObjectId",
  "balance": 5000
}
```

## Transaction Collection

```json
{
  "_id": "ObjectId",
  "senderId": "ObjectId",
  "receiverId": "ObjectId",
  "amount": 1000,
  "type": "TRANSFER",
  "status": "SUCCESS",
  "createdAt": "2026-06-11T12:00:00Z"
}
```

## Beneficiary Collection

```json
{
  "_id": "ObjectId",
  "userId": "ObjectId",
  "beneficiaryId": "ObjectId"
}
```

---

# 🔄 Payment Flow

## Add Money Flow

```text
User
 ↓
Wallet API
 ↓
Wallet Service
 ↓
Update Wallet Balance
 ↓
Create Transaction Entry
 ↓
Push Notification Event
 ↓
Success Response
```

## Transfer Money Flow

```text
User
 ↓
Payment API
 ↓
Validate Sender
 ↓
Validate Receiver
 ↓
Check Balance
 ↓
MongoDB Transaction Session
 ↓
Debit Sender Wallet
 ↓
Credit Receiver Wallet
 ↓
Create Transaction Record
 ↓
Push Notification Event
 ↓
Commit Transaction
 ↓
Success Response
```

---

# ⚡ Redis Caching

Cached Data:

- Wallet Balance
- User Profile
- Beneficiary List
- Recent Transactions

Benefits:

- Faster API Responses
- Reduced Database Load
- Improved User Experience

---

# 📩 BullMQ Queue Events

### Producers

- User Registration
- Money Added
- Money Transferred
- Refund Generated

### Consumers

- Email Notifications
- SMS Notifications
- Audit Logging
- Analytics Processing

---

# 🔐 Security

## Authentication

- JWT Access Token
- Refresh Token Rotation

## Data Protection

- bcrypt Password Hashing
- Secure HTTP Headers
- Input Validation

## API Protection

- Helmet
- CORS
- Rate Limiting

## Financial Safety

- Atomic Transactions
- Duplicate Request Prevention
- Audit Logging
- Transaction Validation

---

# 📈 Scalability Roadmap

## Phase 1

- Single Node.js Instance
- MongoDB
- Redis

Target: 1,000 Users

---

## Phase 2

- Load Balancer
- Multiple Backend Instances
- MongoDB Replica Set
- Redis Cluster

Target: 100,000 Users

---

## Phase 3

- Microservices
- Kafka Event Streaming
- Database Sharding
- Dedicated Payment Service
- Dedicated Notification Service

Target: 1M+ Users

---

# 📊 Non-Functional Requirements

| Requirement | Goal |
|------------|--------|
| Availability | 99.9% |
| Response Time | < 300ms |
| Security | Enterprise Grade |
| Scalability | Horizontal |
| Reliability | High |
| Consistency | Strong |

---

# 🛣️ Future Enhancements

- UPI Integration
- QR Code Payments
- Bank Account Linking
- Cashback Engine
- Reward Points System
- KYC Verification
- Fraud Detection Engine
- Investment Module
- Loan Management
- AI-Powered Financial Insights

---

# 🧠 Learning Outcomes

This project demonstrates:

- High Level Design (HLD)
- Low Level Design (LLD)
- REST API Design
- MongoDB Transactions
- Redis Caching
- BullMQ Queues
- Event Driven Architecture
- Scalable Backend Systems
- Docker Deployment
- Fintech Domain Knowledge

---

# 👨‍💻 Author

**Abhijeet Kumar**

Full Stack Developer

### Skills

- JavaScript
- Node.js
- Express.js
- React.js
- MongoDB
- Redis
- System Design
- Microservices

---

## ⭐ Support

If you find this project useful, consider giving it a star on GitHub.

```
⭐ Star the repository
🍴 Fork the repository
🚀 Build and learn System Design practically
```

**FinFlow — Secure. Scalable. Reliable.**
