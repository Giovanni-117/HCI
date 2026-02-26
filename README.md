# 🎓 ECFCA System — Registry Module & Academic Tracking

![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-HCI%20%2F%20UX-blueviolet?style=for-the-badge)


> A Human-Computer Interaction (HCI) project focused on streamlining academic registration for active professionals.

---

## 📖 Project Overview

The **ECFCA System** is a registry and academic tracking module designed to facilitate the enrollment of graduates and external professionals into diploma courses and continuing education programs.

Built under strict **HCI guidelines**, the system minimizes cognitive load and eliminates navigational friction — ensuring a fast, clear, and frustration-free experience from initial intent to finalized enrollment.

---

## 👥 1. User Group Selection

**Primary Demographic:** Graduates and external professionals seeking diploma courses or continuing education.

This group combines demanding professional careers with academic study, meaning every interaction with the system must be optimized for **speed, clarity, and accessibility**. They don't have time to decipher confusing navigation — the system must adapt to them, not the other way around.

---

##  2. User Persona — Monica

> *"I am motivated to upgrade my skills, but I don't have hours to spend figuring out how to register or checking if my documents were received."*

| Parameter | Detail |
|---|---|
| **Name** | Monica |
| **Age Range** | 30 – 45 years |
| **Profile** | Active professional seeking certification |
| **Tech Level** | Medium – High |
| **Core Need** | Register easily, upload documents without complications, and access content quickly |
| **Main Frustration** | Confusing multi-step processes and lack of immediate confirmation after submission |

**Behavioral context:** Because Monica is accustomed to modern digital tools in her professional life, encountering a bureaucratic or ambiguous academic system creates immediate friction. The system must respect her time constraints and provide transparent, linear workflows.

---

## ⚙️ 3. Functional Requirements

| ID | Description | Actor |
|---|---|---|
| FR-01 | Document upload in **PDF, JPG, or PNG** format | User |
| FR-02 | Automatic validation of uploaded file format | System |
| FR-03 | Immediate notification upon document receipt | System |
| FR-04 | Administrative review and validation of registration | Administrator |
| FR-05 | Final confirmation delivered to user post-validation | System |
| FR-06 | Registration status inquiry at any point | User |
| FR-07 | Group registration of multiple participants | User / Admin |

---

## 📐 4. Non-Functional Requirements

| Type | Constraint | Impact on UX |
|---|---|---|
| **Usability** | Complete registration in < 5 minutes | Reduces abandonment among time-constrained professionals |
| **Availability** | System accessible 24/7 | Supports users registering outside business hours |
| **Security** | Data protection via authentication | Builds trust around sensitive professional data |
| **Performance** | Page load time < 3 seconds | Prevents frustration and perceived instability |
| **Compatibility** | Fully responsive: PC, tablet, and mobile | Allows registration from any device, anywhere |
| **Scalability** | Supports multiple simultaneous users | Ensures stability during peak registration windows |
| **Integrity** | Zero data loss in case of failures | Guarantees no orphaned submissions or documents |

---

##  5. Usability Requirements & Heuristic Alignment

Our usability goals are directly mapped to **Jakob Nielsen's 10 Usability Heuristics** to ensure design decisions are grounded in established HCI theory.

| Usability Goal | Nielsen's Heuristic | Implementation Strategy |
|---|---|---|
| Visibility of process status via clear indicators | **#1 – Visibility of System Status** | Persistent progress steps so the user always knows their stage in the registration pipeline |
| Immediate feedback after each action | **#1 – Visibility of System Status** | Micro-interactions trigger instantly after uploads and form submissions |
| Simple, non-technical language | **#2 – Match Between System and Real World** | All copy uses natural academic-professional vocabulary, avoiding backend jargon |
| Navigation in a maximum of 3 steps | **#7 – Flexibility and Efficiency of Use** | The registration funnel is streamlined to collapse redundant steps into a single cohesive flow |
| Consistent and clean design | **#8 – Aesthetic and Minimalist Design** | Eliminates visual noise; focuses attention on primary CTAs and required inputs |
| Error prevention with validations before submission | **#5 – Error Prevention & #9 – Error Recovery** | Client-side validation intercepts incorrect formats and missing fields before the server request |

###  Accessibility Considerations
- **Cognitive simplicity:** The 3-step limit reduces working memory load, not just time.
- **Feedback clarity:** Success and failure states use multiple visual indicators beyond color alone.

---

## 🤝 6. Assignment of Responsibilities

| Role | Domain | Core Responsibilities |
|---|---|---|
| 🎨 **UX/UI** | User-Centered Design | Visual hierarchy, cognitive load reduction, heuristic compliance |
| 💻 **Frontend** | Interface Implementation | Responsive layouts, real-time client-side validations |
| ⚙️ **Backend** | Logic & File Management | Secure upload endpoints, database integrity, server-side processing |
| 🛡️ **Security** | Data Protection | Authentication layers, privacy of professional credentials |
| 📋 **Administrator** | Registration Validation | Manual document review, triggering confirmation states |
| 🔬 **QA** | Usability Testing | Usability sessions, load time verification, systemic stability checks |

---

##  7. Team Reflections

Throughout this project, our team internalized several core principles about HCI:

- **Digitalization is an exercise in empathy** — understanding the user's reality matters more than executing programming logic.
- **Usability drives adoption** — a flawless backend fails if the frontend creates friction.
- **Design must adapt to the user** — especially for professionals with severely limited time.
- **HCI lets us build systems that are human** — forgiving of errors, transparently communicative, and respectful of context.

---

