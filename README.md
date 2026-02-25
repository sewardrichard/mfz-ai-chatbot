# MFZ AI Chatbot - Automated System

**Client:** MFZ Zambia (Microfinance)  
**Platform:** Botpress (WhatsApp Cloud API & Webchat)  
**Developer:** Seward Mupereri  
**Objective:** To replace manual office-based lead distribution with an automated, 24/7 intelligent routing and support system.

---

## 1. Executive Summary
Previously, MFZ Zambia managed all customer inquiries and loan applications via a manual operator at the head office. This individual was responsible for answering WhatsApp messages, identifying customer needs, and manually assigning loan officers based on location. 

The **MFZ AI Chatbot** fully automates this lifecycle. It qualifies leads, provides instant support via a curated Knowledge Base, and uses a smart distribution algorithm to assign customers to the nearest branch or loan officer without human intervention.

---

## 2. Core Operational Pillars

### ⚡ 24/7 Availability & Speed
Unlike manual processing, the bot is available every second of the year. 
* **Zero Latency:** The bot processes natural language and queries internal databases in milliseconds.
* **Always Online:** Leads generated outside of business hours are captured and routed immediately, ensuring no customer is lost to a competitor due to a delay.

### 🎯 Absolute Accuracy & Compliance
The bot utilizes **Retrieval-Augmented Generation (RAG)** to ensure it only speaks from MFZ’s verified data.
* **Knowledge Base (KB):** Trained on specific MFZ policies and service descriptions.
* **Financial Boundaries:** To maintain compliance and professional standards, the bot is strictly programmed **not** to share interest rates, repayment amounts, or specific loan terms. These sensitive details are reserved for the assigned human loan officer to ensure a professional, personalized closing.

---

## 3. Key Technical Features

### A. Geographic Branch Routing
The bot uses a nested selection flow to guide users to the correct physical location:
1. **Province Selection:** User selects their region from a dynamic menu.
2. **Branch Mapping:** The bot queries a **Botpress Table** to filter and display branches only within that province.
3. **Contact Delivery:** For non-loan services (e.g., account inquiries), the bot provides specific branch contact details and addresses.

### B. Smart Loan Officer Assignment (Load Balancing)
To optimize the workforce and prevent officer burnout, the bot features a **Stateful Distribution System**:
* **Database Tracking:** The bot manages a table of all active loan officers globally.
* **Assignment Counters:** Every assignment is logged; the bot tracks how many leads each officer has received.
* **Fair Distribution Logic:** The system automatically assigns new leads to the officer at the selected branch with the *lowest* current assignment count (Round Robin).
* **Instant Handoff:** The bot generates a direct WhatsApp "click-to-chat" link for the assigned officer, instantly bridging the gap between the lead and the agent.

---

## 4. Business Intelligence & Analytics
The bot acts as a data collector, providing MFZ management with a daily "Pulse Report" including:
* **Traffic Insights:** Total user volume and peak activity times.
* **Service Popularity:** Identification of which loan products or services are most in demand.
* **Resource Monitoring:** Data-driven insights into which branches and loan officers are the busiest, aiding in staffing and performance reviews.

---

## 5. Technical Architecture

| Component | Technology |
| :--- | :--- |
| **Logic Engine** | Botpress Cloud |
| **Channels** | WhatsApp (Meta Cloud API) & Webchat |
| **Data Storage** | Botpress Tables (Provinces, Branches, Officers, & Counters) |
| **AI Model** | Generative LLM with RAG (Knowledge Base) integration |

---

## 6. Project Impact
* **Operational Savings:** Fully removed the manual "switchboard" bottleneck at the head office.
* **Improved Conversion:** Reduced lead-to-officer connection time from hours to under 30 seconds.
* **Standardization:** Ensured every customer receives the exact same high-quality greeting and accurate information regardless of the time of day.

---
