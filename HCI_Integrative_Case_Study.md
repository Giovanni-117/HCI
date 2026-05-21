# Integrative Document — HCI Project: ECFCA System (Extensive Technical Case Study)

This document presents a comprehensive and detailed synthesis of the development of the Academic Registration and Tracking System (ECFCA), structured specifically according to the evaluation metrics of the course.

---

## 1. Summary of progress made between deliveries. Most significant changes, readjustments.

The project evolved significantly from its conceptualization to the final product, highlighting the following key readjustments:
*   **Foundation Phase:** It began with a functional prototype (v0) focused on the technical viability of registration, but it presented high friction for new users, forcing them to log in before viewing the available courses.
*   **Significant Readjustments (Visual Identity):** The UADY Visual Design Guide was integrated to provide the system with institutional authority, replacing the initial generic tone with institutional palettes (Blue and Gold) and typography (Lucida Bright).
*   **Critical Structural Change:** After initial evaluations, the most significant change was the implementation of the **"Lazy Registration"** pattern. This allowed opening the course catalog to unregistered users, eliminating the initial barrier and drastically improving retention.
*   **Refinement (Web Development):** The visibility of the "Calls to Action" (CTAs) was readjusted by drastically increasing contrast to avoid operational confusion. Based on the technical development (`HCIdemo` repository), larger navigation buttons, a new featured card for courses, and a dynamic *Hero* were implemented to improve the first impression and correct session flows.

---

## 2. Product Summary in terms of development phases based on the User-Centered Design Methodology

The product was conceived by placing the target user at the center of all architectural decisions.
*   **User Research:** Focused on professionals aged 30-45, characterized by having little time and a low tolerance for technological friction.
*   **Cognitive Architecture:** Guided by the methodology, interface patterns were implemented to alleviate mental load:
    *   *Breadcrumbs:* To orient the user at all times.
    *   *Clear Primary Actions:* Use of high-contrast institutional colors to highlight the main action on each screen.
*   **Theoretical Validation:** It was understood that direct interviews are useful, but it is vital to contrast what the user *says* with what they actually *do* in the system.

---

## 3. Presentation of each stage with implementation details

The project flowed through dedicated branches in Git, reflecting clear transitions between stages and prototypes:

*   **Stage 1 (Conceptualization):**
    *   *Process:* Clear definition of the application, project plan, and user profiles.
    *   *Products:* First functional prototype (v0).
    *   *Results:* Viable technical structure but with poor visual design and navigation blocks.
*   **Stage 2 (Visual Structuring and Requirements):**
    *   *Process:* Definition of participant methodology and Non-Functional Requirements (NFR).
    *   *Products:* Integration of UADY visual guidelines.
    *   *Transition:* From a generic prototype (v0) to an interface projecting institutional seriousness.
*   **Stage 3 (Logical Implementation and Technical Development):**
    *   *Process:* Front-End development and integration with asynchronous logic.
    *   *Products:* Web application built with **Next.js 16**, **React 19**, **Tailwind CSS v4**, and accessible components from **Radix UI**. Strict form validations were implemented using **Zod** and **React Hook Form**.
    *   *Results:* A robust technical ecosystem, with file upload components, dynamic interfaces (featured cards and animated Hero), and fast, accessible navigation.
*   **Stages 4 and 5 (Testing and Consolidation):**
    *   *Process:* Empirical test execution and refinement.
    *   *Products:* Extensive NFR Testing Document.
    *   *Results:* Final system corrected and optimized for the professional user.

---

## 4. Usability Testing

The team developed a testing plan to empirically measure system usability using specific validation matrices.

**Materials and Metrics Used:**
*   **SUS Scale (System Usability Scale):** Target > 70 points and > 70% success in the first session without help.
*   **WAVE (Accessibility):** Target of zero Level A critical errors.

**Analysis and Results (Critical Findings based on Real Participants):**
The usability test included a demographically diverse group (ages between 23 and 58, from highly technical to casual/moderate profiles).

Below is the consolidated matrix of results and qualitative observations obtained during the execution of the 4 main tasks:

### Consolidated Results by Task

| ID | Task | Quantitative Summary (Times and Errors) | Qualitative Observations and Friction (Think Aloud) |
| :--- | :--- | :--- | :--- |
| **T1** | User Registration | **Completion:** High (some with help).<br>**Time:** 48s (Min) to 160s (Max).<br>**Common errors:** ID format and passwords. | • The registration button was difficult to locate initially for several users.<br>• Lack of clarity in the expected format for the "Student ID".<br>• Confusion between using personal or institutional email.<br>• Lack of visual *feedback* (animation/message) upon successful registration completion. |
| **T2** | Login | **Completion:** 100% (Very high).<br>**Time:** 12s (Min) to 60s (Max).<br>**Common errors:** Credential confusion (email). | • Smooth task without serious hesitation.<br>• The layout was perceived as clean and correct.<br>• Some users expected direct redirection to a dashboard or "My Profile" after logging in. |
| **T3** | Course Enrollment | **Completion:** Moderate (abandonments and help occurred).<br>**Time:** 55s (Min) to 280s (Max).<br>**Common errors:** Clicks on dead zones of the card. | • Saturated visual hierarchy on the course card; the "Enroll" button did not stand out enough.<br>• Demand for search tools by name, date or category filters.<br>• Confusion about the meaning of status colors (green = available or enrolled?). |
| **T4** | Status Visualization | **Completion:** High to Partial.<br>**Time:** 12s (Min) to 88s (Max).<br>**Common errors:** Navigation to incorrect tabs. | • Difficult initial location of the area to consult enrollments.<br>• Ambiguity in interpreting icons (clock was confused; green and gray were similar).<br>• More technical users requested options to export history or filter status. |

**Testing Conclusions:**
Data showed that while the "Happy Path" works adequately for technical users (like Carlos), the interface lacks sufficient cognitive supports (success messages, guided formats, search filters, and color differentiation), which severely penalized older users or those with a less technological profile (Candy, Sofía, Martha). This confirms the need to integrate real-time validations and progressive disclosure.

---

## 5. Lessons Learned (Conclusions)

**Theoretical Contrast vs. Implementation:**
*   It was proven that Nielsen's heuristic rule "Less is More" can be counterproductive if not based on user research. An excessively minimalist interface without clarity generates massive barriers for non-technological users.
*   Design must prioritize "Greater Clarity" over pure minimalism.

**Errors Made and Improvements:**
*   *Initial error:* Forcing registration before providing value (login block). Solved by opening the catalog. Future implementations should always prioritize the *Progressive Disclosure* pattern.
*   *Future improvement:* Incorporate more descriptive *hover* controls to reduce cognitive load when navigating the catalog.

**Learnings and Skill Acquisition:**
*   The course objective was met by understanding that the developer's role is not just to "build screens," but to intervene, contextualize, and provide accessibility and empathy to the interface for an institutional context. Solid practical skills were acquired in testing methodologies (SUS, Think Aloud) and accessibility tools (WAVE).

---

## 6. Presentation of Progress

Throughout the project, the presentation of information evolved to reflect the technical maturity of the team:
*   **Material and Format:** Navigable prototypes deployed live were used, complemented with requirements documentation hosted directly in Markdown within the repository. Multimedia support existed (such as creating presentation videos in initial deliveries).
*   **Time Usage and Attention:** Demonstrations focused on evidencing the user flow (*Happy Path*) in front of the audience, ensuring a structured presentation that contrasted previous friction with current interactive solutions.

---

## 7. Teamwork

Monitoring and work processes were rigorously managed through the Git repository, using a structured workflow of branches per delivery (`1st-Delivery` to `5th-Delivery`) that guaranteed parallel development and effective reviews.

**Roles and Objective Contribution Percentages:**

*   **Samuel Blanco (~40%):** Leadership in web development. Responsible for the technical execution of prototypes (v0 and final), environment configuration, and English translations.
*   **Adriel Yerbes (~25%):** Delivery management, bitacora consolidation, methodological documentation handling, and NFR synchronization.
*   **Aldo (~20%):** Testing architecture. Main author of the extended Non-Functional Requirements testing document and theoretical analysis of interface patterns.
*   **Sebastián Leal (~10%):** Methodological bases. In charge of early theoretical definition, participant methodology, and heuristics.
*   **José Blanco (~5%):** Initial conceptual contribution and user scenario definition.
