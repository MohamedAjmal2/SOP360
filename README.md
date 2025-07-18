# SOP360: AI-Powered Compliance Training

## Application Overview

SOP360 is a comprehensive, AI-powered platform designed to streamline and automate the management of Standard Operating Procedures (SOPs). It provides a robust solution for organizations to create, assign, and track SOP training, ensuring compliance and enhancing team efficiency. The application features a multi-tenant architecture, catering to both individual organizations (Client Admins) and a system-wide administrator (Super Admin).

---

## Core Features

### 1. Public-Facing Landing Page
A professional and modern homepage that outlines the application's key features, benefits, and pricing tiers. It serves as the primary entry point for new customers and provides a login portal for existing administrators.

### 2. Multi-Tenant Authentication & User Roles
*   **Secure Authentication:** Utilizes Firebase Authentication for robust and secure user login and sign-up.
*   **Super Admin Role:** The first user to sign up automatically becomes a "Super Admin." This user has a global view of all organizations, users, and compliance records. They are responsible for creating new client organizations and inviting their initial administrators.
*   **Client Admin Role:** Administrators who belong to a specific organization. They can only manage SOPs, users, and compliance data within their own organization, ensuring data privacy and segregation between clients.
*   **Invite-Only System:** New admin accounts (after the first Super Admin) can only be created via a secure, single-use invitation link, ensuring controlled access.

### 3. Sophisticated Admin Dashboard
A centralized hub for all administrative tasks, with views and permissions dynamically adjusted based on the user's role (Super Admin vs. Client Admin).

*   **Dashboard Analytics:** An overview page displaying key metrics like total training completions, overall pass rates, and average quiz scores. It features an interactive bar chart visualizing compliance data (Passed vs. Failed) for each SOP.
*   **SOP Library:**
    *   **AI-Powered Document Ingestion:** Admins can upload a PDF document. A Genkit AI flow automatically parses the document, extracts the title and content, and creates a new SOP, saving significant manual effort.
    *   **Manual Creation:** Admins can also create and edit SOPs manually using a rich text editor.
    *   **Full CRUD:** Complete Create, Read, Update, and Delete functionality for all SOPs.
*   **Training Assignment:** Admins can assign any SOP to a user by entering their email address. This generates a unique, secure training link that can be sent to the user. The number of quiz questions can be customized for each assignment.
*   **Compliance Search:** A powerful search tool to find all training records for a specific user by their email address.
*   **User Directory:** A comprehensive list of all personnel, including registered Admins and Trainees (users who have completed at least one training). It provides a quick way to view a user's history.
*   **Settings & Account Management:**
    *   Admins can manage their own account details and change their password.
    *   Client Admins can invite new administrators to their organization and manage pending invitations.
    *   Super Admins can create new client organizations and manage the system at a high level.

### 4. AI-Powered Training & Compliance Flow
The end-user (trainee) experience is designed to be seamless and effective.

1.  **Secure Access:** The user receives a unique link to access their assigned SOP training. These links are single-use and expire upon completion.
2.  **SOP Reading:** The user is presented with the full SOP document in a clean, readable format. Their reading time is tracked to ensure engagement.
3.  **AI Quiz Generation:** After reading, the user initiates a quiz. A Genkit AI flow generates a unique, multiple-choice quiz in real-time based on the content of the SOP, ensuring the questions are relevant and test true comprehension.
4.  **Digital Signature & Reporting:** Upon completing the quiz, the results are saved as a permanent compliance record, serving as a digital signature of acknowledgment. The user sees a final report with their score, status (Passed/Failed), and a review of their answers.

---

## Technology Stack

*   **Framework:** Next.js (with App Router)
*   **Language:** TypeScript
*   **Styling:** Tailwind CSS with ShadCN UI for a professional and consistent component library.
*   **Backend & Database:** Firebase (Authentication for users, Firestore for data storage).
*   **AI & Server-Side Logic:** Google's Genkit, integrated into Next.js, powers all generative AI features
