# 🚀 Client-Onboarding-MicrosoftPowerPlatform-EndToEnd-Project
📌 Project Overview

A full-stack business solution designed to streamline client onboarding data intake and automate reporting. This project replaces fragmented manual processes with a "Single Source of Truth" architecture using the Microsoft Power Platform.

🛠️ The Solution (Architecture)

**1. Frontend: Power Apps (Canvas)-** A high-fidelity interface with dynamic navigation and strict data hygiene logic.
- Hard Validation: The "Approve" button remains disabled until PAN (10-char) and GST (15-char) requirements are met.

App Interface Preview:

<img width="1705" height="971" alt="Canvas App View" src="https://github.com/user-attachments/assets/e75cae9c-afbe-4a66-b750-5a42e0547e9a" />


**2. Database: Microsoft Dataverse-** A relational backend that ensures referential integrity.
- Solution Management: Built within a dedicated WMS Solution for professional lifecycle management and dependency tracking.

Solution & Dependency View:

<img width="1758" height="419" alt="App dependencies in Dataverse" src="https://github.com/user-attachments/assets/7f92faf7-d55e-4373-ae75-7555ec998e7b" />

**3. Data Modeling & Relationships-** 
- I architected a One-to-Many relational model to link parent client records with multiple addresses and contact persons.

Entity Relationship Diagram (ERD):

<img width="1920" height="673" alt="Data Model" src="https://github.com/user-attachments/assets/fb8381f5-7329-4bdf-90eb-ef676fc46987" />

**4. Business Intelligence: Power BI-**
- Real-time insights generated through a native Dataverse connection.

Executive Dashboard:

<img width="1087" height="520" alt="Power BI Insights" src="https://github.com/user-attachments/assets/7858cb0a-4c17-4e48-bc31-1b00f77d3d11" />

✨ Key Features
- 100% Data Hygiene: Front-end validation prevents "dirty data" from entering the ecosystem.

- Relational Integrity: Multi-table patching maintains links between Client, Address, and Contact data.

- Automated ETL: Native integration between Dataverse and Power BI eliminates manual data cleaning.



