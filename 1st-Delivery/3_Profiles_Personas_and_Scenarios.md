## 3. PROFILES, PERSONAS, AND SCENARIOS

### 3.1 Methodological Note

The behavioral design of the system is based on an understanding of the limitations and pressures faced by our primary demographic group when integrating new academic responsibilities into their daily routines. All interaction decisions are informed by the following persona archetype.

### 3.2 General Profile of the Public User

The user base is primarily composed of economically active professionals seeking education at the diploma or postgraduate level. This assumes productive, focused users who conceive digital tools as an expedient means and not as an end in themselves.

Their main interaction involves document flows; they need to know the status of their procedures the instant they upload or process a document, they abhor redundancy, and they drastically penalize systems that act as opaque "black boxes" or that use administrative jargon in alerts.

### 3.3 Primary Persona: Monica, the Busy Professional

**Estimated Demographic Profile**
Monica is an archetype representing a professional in an age range between 30 and 45. She possesses a genuine motivation to update and enhance her skills but balances this with the demanding pace of her professional profile.

**Technological Context**
The technological proficiency of this archetype is Medium-High. In her daily corporate work, she employs optimized and fast SaaS tools. This generates a high expectation for any institutional platform with which she must interact.

**Identified Needs**
Monica primarily needs the platform to abide by rules of fluidity and efficiency: register swiftly, have obvious facilities to upload her academic paperwork without operational complexities, and visually confirm immediately if her actions or payments were processed correctly.

**Main Frustration**
For Monica, the main breaking point occurs when facing multi-stage processes that are vague in their progression status. She hates spending time sending documentation through different channels and internally wondering if those documents were successfully received. Anything that adds friction to an already extremely scarce amount of time represents a structural failure for her.

**Typical Use Scenario**

After a workday, Monica logs in from her tablet or computer to the link provided to enroll in a diploma course. In a highly focused environment, she wants to complete this procedure in less than 5 minutes before attending to family responsibilities.

The system welcomes her with a minimalist interface. It skips internal academic jargon and offers a concise form, strictly limited to 3 distinct progression stages. Upon selecting the documents that accredit her resume and identity (PDF or JPG, for example), the platform instantly validates the format on her browser's side.

Monica clicks the submit button, and the ECFCA system reacts immediately at a micro-interaction level. The persistent project status indicator updates to "Sent for Administrative Review," and it specifies with full legibility that the corresponding team will evaluate and soon confirm her access.

Hours later, in front of an office computer, or even in transit via her mobile device—taking advantage of the architecture's 24/7 responsive feature—she logs in again. This time, through her logged-in account, the same indicator already shows her the official confirmation. Her registration is finalized in the shortest possible operational time.

### 3.4 Consequences for Inclusive Design (Amplifier Effect)

By molding the product around strict respect for Monica's time and cognitive level, the platform subsidiarily accommodates the needs of young entry-level professionals and even students with unstable connections.

For less consolidated profiles of a younger age range, a clear flow simplifies any learning curve. Furthermore, by forcing technical information to have a "match with the real world," generational barriers of understanding are broken down. Every user, whether a corporate novice or an area director, values cognitive simplification equally. By being accommodating to their stress and limited time, the system democratizes its facilities.

### 3.5 Simplified Journey Map - 3-Stage Oriented Flow

**Common Current State (Base Problem)**
Access to an opaque, multi-screen system. The user sends information or receipts after multiple confusing clicks. Finally, they press the submit button and receive a blank status. They must rely on sending an institutional email the next day to ensure the server actually saved their attachments, while the system logs them out.

**Desired State in the ECFCA System**
Simplified access to the funnel. Agile capture with direct error prevention. The design displays indicators showing what stage of the application the user is in ("Visibility of system status"). Submission of information with ultra-fast transactional feedback on screen, delivering unconditional and autonomous certainty to the professional.

---

## 4. PRELIMINARY CONCLUSIONS

Academic registration, under HCI scrutiny, is not simply a data exchange between client and server. It is a service with human implications marked by respect for the interested individual's schedule and transparent ("human") communication.

Guaranteeing aggressive non-functional metrics, such as < 5 minutes resolution time, alongside assimilation of heuristic theory, directly prevents prospect abandonment, translating into a higher acquisition rate for the institution.

Beyond the Database schema and secured APIs, optimal integration lies in the Frontend, which bears the total responsibility of softening the load and making errors forgivable. Building this Registry Module based on "Monica" ensures that our final validation will be a rapid, fluid product adoption with zero administrative support fatigue.
