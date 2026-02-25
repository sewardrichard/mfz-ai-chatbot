# Project Documentation: MFZ Zambia AI Chatbot (Automation System)
**Platform:** Botpress (WhatsApp & Web Integration)  
**Developer:** Seward Mupereri  
**Objective:** Automate lead qualification, geographic routing, and load-balanced loan officer assignment for MFZ Zambia.

---

## 1. Project Overview
Before this implementation, MFZ Zambia managed all incoming WhatsApp inquiries via a manual operator at the head office. This created significant bottlenecks in response times and inconsistent lead distribution. 

The **MFZ AI Bot** replaces this manual process with an automated, data-driven system that handles customer support, identifies user needs, and routes them to the nearest physical branch or a specific loan officer in real-time.

---

## 2. Core Features

### A. Intelligent Knowledge Base (Q&A)
The bot acts as an automated consultant. Using **Retrieval-Augmented Generation (RAG)**, it answers customer questions based on a curated knowledge base of MFZ policies, including:
* Loan eligibility and requirements.
* Interest rates and repayment terms.
* General branch information.

### B. Geographic Branch Routing
To ensure customers get localized help, the bot uses a nested selection flow:
1. **Province Selection:** The user selects their province from a menu.
2. **Branch Filtering:** The bot queries a internal table to show only branches within that province.
3. **Information Delivery:** For general services, the bot provides the specific contact details and location of the closest branch.

### C. Smart Loan Officer Assignment (Load Balancing)
This is a high-level operational feature designed to ensure a fair distribution of work:
* **Stateful Tracking:** The bot maintains a **Botpress Table** containing a list of all active loan officers.
* **Assignment Counters:** Every time an officer is assigned a lead, the bot increments a "count" column in the database for that specific officer.
* **Fair Distribution Logic:** New leads are automatically assigned to the officer at the selected branch with the *lowest* assignment count.
* **Direct Handoff:** The bot generates a direct WhatsApp click-to-chat link for the assigned officer, bridging the gap between the customer and the agent instantly.

---

## 3. Business Intelligence & Analytics
The system goes beyond chat by providing MFZ management with actionable data via daily reports:
* **Traffic Summaries:** Daily volume of bot interactions.
* **Service Insights:** Identification of the most requested loan products.
* **Resource Optimization:** Analytics on which branches are the busiest and which loan officers are handling the most leads.

---

## 4. Technical Architecture

| Component | Technology |
| :--- | :--- |
| **Logic Engine** | Botpress Cloud |
| **Messaging Channels** | WhatsApp (Cloud API) & Webchat |
| **Database/Storage** | Botpress Tables (Provinces, Branches, Officers, & Counters) |
| **Model** | Generative AI with Knowledge Base integration |

---

## 5. Key Impact
* **Operational Efficiency:** Fully eliminated the manual "switchboard" role at the head office.
* **Response Speed:** Reduced lead-to-officer connection time from several minutes/hours to under 30 seconds.
* **Scalability:** The system can now handle hundreds of concurrent inquiries across all Zambian provinces simultaneously without increasing overhead.

---
