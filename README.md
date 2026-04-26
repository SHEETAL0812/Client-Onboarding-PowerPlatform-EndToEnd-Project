# 🚀 Client-Onboarding-MicrosoftPowerPlatform-EndToEnd-Project
📌 Project Overview

A full-stack business solution designed to streamline client onboarding data intake and automate reporting. This project replaces fragmented manual processes with a "Single Source of Truth" architecture using the Microsoft Power Platform.

🛠️ The Solution (Architecture)

**Phase 1: Relational Architecture (Dataverse)**
Instead of a flat Excel sheet, I architected a relational database to ensure data scalability and normalization.

- **The Schema:** Created three distinct tables: Parent Group Clients, Client Addresses, and Client Contacts.

- **Relational Logic:** Established One-to-Many (1:N) relationships using Lookup columns. This ensures that every address and contact person is digitally "anchored" to a specific Client ID, preventing orphaned data.

- **Solution Management:** Bundled all assets into a WMS Solution. This follows ALM (Application Lifecycle Management) best practices, allowing for easy deployment across different environments (Dev, Test, Prod).

Entity Relationship Diagram (ERD):

<img width="1920" height="673" alt="Data Model" src="https://github.com/user-attachments/assets/fb8381f5-7329-4bdf-90eb-ef676fc46987" />

**Phase 2: Frontend: Power Apps (Canvas)-** 
The frontend was designed to transform a complex, multi-table data entry process into a seamless user experience.

- **State Management:** Utilized UpdateContext variables to create a "Tabbed" navigation system. This allows users to switch between "Address" and "Contact" views without leaving the screen, maintaining the app's performance and speed.

- **Form Integration:** Integrated three separate EditForm controls. I configured the Item and DataSource properties to ensure that while the user sees one page, the app is communicating with three different database endpoints simultaneously.

- **Dynamic UI:** Configured the Visible properties of containers so that the interface reacts instantly to user clicks, reducing "cognitive load" for the data entry operator.

App Interface Preview:

<img width="1705" height="971" alt="Canvas App View" src="https://github.com/user-attachments/assets/e75cae9c-afbe-4a66-b750-5a42e0547e9a" />

**Phase 3: The "Gatekeeper" Logic (Validation)**
This is the core "Data Hygiene" engine of the app. I wrote custom Power Fx formulas to act as a rigorous gatekeeper.

- **Button DisplayMode Logic:** Instead of allowing users to submit erroneous data, I authored a conditional formula for the DisplayMode property of the Approve button. It evaluates the Len() (length) of the text inputs in real-time.

- **Syntax Example:** If(Len(PAN_Input.Text) = 10 && Len(GST_Input.Text) = 15, DisplayMode.Edit, DisplayMode.Disabled)

- **The Business Benefit:** This eliminates "Human Error" at the source. By the time the data reaches the Dataverse, it is 100% compliant with government formatting standards for PAN and GSTIN, removing the need for manual data cleaning.

**Phase 4: Data Submission & Multi-Table Patching**
Saving data to multiple tables simultaneously requires precise execution to maintain referential integrity.

- **Submission Sequence:** Programmed the OnSelect property to trigger a sequential SubmitForm() for all three forms, ensuring that if any part of the process fails, the user is notified.

- **Referential Linking:** I utilized the .Updates property of the Parent Form to automatically populate the Lookup fields in the Child Forms. This ensures that the moment a client is created, their address and contact records are instantly linked via a GUID (Global Unique Identifier).

- **User Feedback (UX):** Implemented the Notify() function to provide instant visual confirmation upon successful submission, closing the feedback loop for the operator.

Solution & Dependency View:

<img width="1758" height="419" alt="App dependencies in Dataverse" src="https://github.com/user-attachments/assets/7f92faf7-d55e-4373-ae75-7555ec998e7b" />


**Phase 5: Business Intelligence Pipeline & Analytical Modeling: Power BI-**
Finally, I closed the loop by turning raw data into a strategic asset.

- **Direct Connector:** Established a secure connection via the Dataverse Web API.

- **Data Modeling:** In Power BI, I reconstructed the Star Schema by defining relationships between the imported tables.

- **Visualization:** Created measures to track "Total Onboarded Clients" and categorized them by Industry Sector and Region. This provides leadership with a bird's-eye view of regional performance.

Executive Dashboard:

<img width="1087" height="520" alt="Power BI Insights" src="https://github.com/user-attachments/assets/7858cb0a-4c17-4e48-bc31-1b00f77d3d11" />

✨ Key Features

- 100% Data Hygiene: Front-end validation prevents "dirty data" from entering the ecosystem.

- Relational Integrity: Multi-table patching maintains links between Client, Address, and Contact data.

- Automated ETL: Native integration between Dataverse and Power BI eliminates manual data cleaning.



