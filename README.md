# Smart-Campus-Management-n8n-Prototypes-


# 🎓 Smart Campus Multi-Agent Automation System (n8n)

A modular, scalable automation system built using **n8n** to streamline student registration, communication, and campus operations.

This project transforms manual administrative processes into **intelligent, automated workflows** using event-driven architecture and AI-ready pipelines.

---

## 🚀 Project Overview

This system is designed as a **multi-agent workflow architecture**, where each workflow (agent) handles a specific responsibility.

Instead of one monolithic process, the system is divided into independent yet connected workflows:

* 🧾 Registration & Validation Agent
* 📢 Communication Agent
* ⏰ Reminder Agent *(planned)*
* 🧠 AI Feedback Analysis Agent *(planned)*
* 📊 Admin Reporting Agent *(planned)*

---

## ⚙️ Workflows Implemented

### 🔹 Workflow 1: Student Registration & Validation

Handles secure and structured student onboarding.

#### Features:

* Webhook-based form submission
* Input validation (email & phone)
* Duplicate detection (Google Sheets lookup)
* Dynamic Registration ID (RegID) generation
* Structured data storage with timestamp & status
* Triggers next workflow upon success

#### Flow:

```
Webhook → Validate → Check Duplicate → Generate RegID → Store Data → Trigger Communication
```

---

### 🔹 Workflow 2: Automated Communication System

Handles real-time communication after successful registration.

#### Features:

* Triggered from Workflow 1
* Sends confirmation email (Gmail)
* Sends SMS/WhatsApp notification (Twilio)
* Personalized messages with RegID
* Tracks delivery status (sent/failed)
* Logs communication data

#### Flow:

```
Trigger → Email + SMS → Merge → Status → Store Logs
```

---

## 🏗️ System Architecture

```
[Student Form]
      ↓
[Workflow 1: Registration Agent]
      ↓
[Workflow 2: Communication Agent]
      ↓
[Google Sheets / Database]
      ↓
[Future Agents: Reminder | AI Analysis | Reporting]
```

---

## 🧠 Key Concepts Used

* Event-driven architecture
* Modular workflow design
* Multi-agent system (via n8n workflows)
* Data validation & integrity checks
* API integrations (Gmail, Twilio, Google Sheets)
* Scalable automation pipelines

---

## 🛠️ Tech Stack

* **n8n** – Workflow automation
* **Google Sheets** – Data storage
* **Gmail API** – Email notifications
* **Twilio API** – SMS/WhatsApp messaging
* **OpenAI (planned)** – AI analysis

---

## 📂 Project Structure

```
/workflows
  ├── workflow1-registration.json
  ├── workflow2-communication.json
README.md
```

---

## ⚡ Setup Instructions

### 1. Import Workflows into n8n

* Open n8n
* Import JSON files from `/workflows`

### 2. Configure Credentials

* Google Sheets
* Gmail
* Twilio

### 3. Prepare Google Sheets

#### Registration Sheet:

```
name | email | phone | RegID | timestamp | status
```

#### Communication Logs Sheet:

```
name | email | phone | RegID | email_status | sms_status | timestamp
```

---

## 🔗 Workflow Connection

* Workflow 1 triggers Workflow 2 using:

  * **Execute Workflow Node**

---

## 📌 Future Enhancements

* ⏰ Automated Event Reminders
* 🧠 AI-based Feedback Analysis
* 📊 Admin Dashboard & Reports
* 📱 Multi-channel notifications

---

## 🎯 Use Cases

* College event registrations
* Campus communication systems
* Student onboarding automation
* Workshop / seminar management

---

## 💡 Key Learning

This project demonstrates how **simple workflows can evolve into intelligent automation systems** by applying modular design and agent-based architecture.

---

## 👤 Author

**Anish Choudhary**

---

## ⭐ If you found this useful

Give it a star ⭐ and feel free to contribute!
