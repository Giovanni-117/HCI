# Test Plan — Non-Functional Requirements: User Interface

**System:** UADY Postgraduate and Continuing Education Portal
**Version:** 1.0
**Classification:** QA Verification Document

---

## What is this document and what is it for?

When we develop software, it is not enough for the system to simply *work*. It must also be **usable, accessible, consistent, and adaptable**. Those qualities are captured in **Non-Functional Requirements (NFRs)**, and this document describes **how to verify that each one is met**.

Every section answers three questions:
1. **What is being tested?** — The requirement.
2. **How is it tested?** — The verification method.
3. **How do I know it passed?** — The acceptance criterion.

>  **Reading note:** Identifiers like `NFR-UI-001` are the keys that link each test back to the original requirements document. Use them for traceability.

---

## Section 1 — Usability

Usability measures how easy the system is to use for someone who has never seen it before. It is tested with **real users**, not just code inspection.

---

### NFR-UI-001 · Intuitiveness on First Use

**What is being tested?**
That a new user can complete critical tasks (such as creating an account) without any explanation, on their very first encounter with the system.

**How is it tested?**

1. Recruit 5 to 8 participants matching the target profile (busy professionals) who have never seen the system.
2. Ask them to complete a specific task, for example: *"Create a new account and submit an enrollment request."*
3. Provide no guidance and do not intervene during the session.
4. Record whether each participant completed the task or not.
5. At the end, apply the **SUS (System Usability Scale)** questionnaire — 10 standard questions on a Likert scale.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Average SUS score | ≥ 70 points (out of 100) |
| First-session task completion rate | > 70% of users complete the task |

>  **Reference:** A SUS score of 68 is considered "average." Exceeding 70 without assistance indicates the interface is intuitive for first-time users.

---

### NFR-UI-002 · Learning Curve

**What is being tested?**
That the second time someone uses the system, they complete tasks significantly faster and with fewer errors than the first time.

**How is it tested?**

1. Schedule a second session with the same participants from NFR-UI-001, 1 to 3 days later.
2. Ask them to complete the same task flow.
3. Measure **Time-on-Task (ToT)** in both sessions.
4. Record any hesitations, backtracking, or errors.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Behavior in the 2nd session | User completes the flow without hesitation or backtracking |
| Time reduction | ≥ 30% less time than in the 1st session |

---

### NFR-UI-003 · Error Prevention

**What is being tested?**
That the system prevents users from making errors before they happen — for example, by disabling the "Submit" button while the form is still incomplete.

**How is it tested?**
Use the **Think-Aloud Protocol**: the user verbalizes their thoughts out loud while using the system. The evaluator observes and records every error made.

Errors are classified as:
- **Recoverable:** the user notices the mistake and corrects it on their own.
- **Fatal (non-recoverable):** the user gets stuck and requires external help.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Fatal errors per user | < 2 fatal errors across the complete flow |

---

### NFR-UI-004 · Quality of Error Messages

**What is being tested?**
That every error message shown by the system: (a) states what went wrong, (b) explains how to fix it, and (c) is written in plain, non-technical language.

**How is it tested?**
**Heuristic evaluation** based on Jakob Nielsen's usability principles. A UX evaluator reviews every visible error message in the system using the following checklist.

**Checklist per error message:**

```
[ ] Does it clearly indicate what happened?
[ ] Does it tell the user how to fix it?
[ ] Does it avoid technical terms or administrative jargon?
```

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Error messages meeting all 3 criteria | 100% |

---

### NFR-UI-005 · Error Recovery

**What is being tested?**
That before executing any irreversible action (submitting a request, paying, deleting data), the system asks the user for explicit confirmation.

**How is it tested?**
Functional verification: a tester walks through all critical flows and confirms that each one includes a confirmation step (modal dialog, summary screen, etc.).

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Critical actions with a confirmation step | 100% of identified actions |

---

## Section 2 — Accessibility

Accessibility ensures that the system can be used by people with different abilities. The international reference standard is **WCAG 2.1**.

>  **Quick context:** WCAG defines three levels: A (mandatory minimum), AA (recommended), AAA (advanced). This system targets Level A across all flows and Level AA for text contrast.

---

### NFR-UI-006 · WCAG 2.1 Level A Compliance

**What is being tested?**
That the main system flows have no Level A accessibility errors (the most severe category).

**How is it tested?**

1. Install the **WAVE** extension (Web Accessibility Evaluation Tool) in Chrome.
2. Navigate through the main flows: login, registration, enrollment form, and payment.
3. Run the analysis and review the WAVE results panel.
4. Document all Level A errors found.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Critical Level A errors in main flows | 0 errors |

---

### NFR-UI-007 · Color Contrast

**What is being tested?**
That text is readable for people with low vision or color blindness, through adequate contrast ratios.

**How is it tested?**

1. Open [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/).
2. Enter the text color and background color for each combination used in the system.
3. Verify that the calculated ratio meets the minimums.

**How do I know it passed?**

| Text Type | Minimum Required Ratio |
|---|---|
| Normal text (< 18pt) | 4.5 : 1 |
| Large text (≥ 18pt or 14pt bold) | 3 : 1 |
| Percentage of texts that comply | 100% |

---

### NFR-UI-008 · Keyboard Navigation

**What is being tested?**
That a user who cannot use a mouse can operate the entire system using only the keyboard.

**How is it tested?**
Manual testing: the tester sets aside the mouse and navigates the entire system exclusively using `Tab`, `Shift+Tab`, `Enter`, `Space`, and arrow keys.

**Verification checklist:**

```
[ ] Are all form fields reachable with Tab?
[ ] Is the focus order (Tab order) logical and predictable?
[ ] Can modals and menus be closed with Escape?
[ ] Does focus ever get trapped in an element with no way out?
[ ] Are buttons activated with Enter or Space?
```

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Functionalities accessible via keyboard | 100% |

---

### NFR-UI-009 · Touch Target Size (Mobile)

**What is being tested?**
That buttons, links, and form fields on mobile are large enough to be tapped with a finger without accidentally hitting the wrong element.

**How is it tested?**

1. Open the system in responsive mode (Chrome DevTools → 375px wide screen).
2. Select each interactive element with the inspector.
3. Verify `width` and `height` in the computed styles panel.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Minimum area of each interactive element | ≥ 44 × 44 px |
| Separation between adjacent elements | ≥ 8 px |

---

## Section 3 — Responsive Design

A responsive system does not simply "shrink" on mobile — it **reorganizes** itself so that the experience is optimal on every device.

---

### NFR-UI-010 · Supported Breakpoints

**What is being tested?**
That the system looks and functions correctly across the three defined screen size ranges.

**How is it tested?**

Use Chrome DevTools (F12 → device icon) to test at the following widths:

| Device | Test Widths |
|---|---|
| Mobile | 320px, 375px, 428px |
| Tablet | 768px, 1024px |
| Desktop | 1280px, 1440px |

At each resolution, verify:

```
[ ] Is the layout functional and legible?
[ ] Is there any unintended horizontal scrolling?
[ ] Is text not cut off or overlapping?
[ ] Do forms and tables retain full functionality?
```

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Functional layout at all breakpoints | No horizontal scroll and no loss of functionality |

---

### NFR-UI-011 · Content Adaptation

**What is being tested?**
That elements *reorganize* when the screen size changes — not just shrink.

**How is it tested?**
Manual visual review: compare the layout on desktop vs. mobile for the main components: navbar, forms, and data tables. Verify that they change structure rather than simply resizing.

**How do I know it passed?**

| Component | Expected Behavior on Mobile |
|---|---|
| Navbar | Collapses into a hamburger menu |
| Multi-part forms | Columns stack vertically |
| Data tables | Transform into a card view or controlled horizontal scroll |

---

### NFR-UI-012 · Responsive Images

**What is being tested?**
That images load at the appropriate resolution for each device, rather than serving a large desktop image to a mobile screen.

**How is it tested?**
Inspect the HTML of each image in the system. Verify that they use the `srcset` attribute or the `<picture>` element.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Content images using srcset or `<picture>` | 100% |
---
### NFR-UI-013 · Touch Spacing on Mobile

**What is being tested?**
That interactive elements on mobile have enough spacing between them to prevent accidental taps on the wrong element.

**How is it tested?**
Open the system in responsive mode (Chrome DevTools → 375px wide screen). Visually inspect the spacing between adjacent interactive elements — buttons, links, and form fields — and measure the gap using the DevTools box model panel.

**How do I know it passed?**
| Metric | Acceptance Criterion |
|---|---|
| Separation between adjacent interactive elements | ≥ 8 px on all mobile views |


---

## Section 4 — Visual Consistency

Visual consistency ensures the system feels like a genuine UADY institutional product, not a generic project.

---

### NFR-UI-014 · UADY Brand Identity

**What is being tested?**
That the institutional signature (shield + UADY name) always appears in the top-left corner of the navigation bar, and that the "Arcos 2023" texture is applied correctly.

**How is it tested?**
Walk through all system views using the UADY Visual Conformity Checklist (Section 12 of the Identity Manual).

**How do I know it passed?**

| Element | Criterion |
|---|---|
| UADY signature | Present in the navbar on 100% of views |
| Arcos 2023 texture | Applied exclusively and without overlapping content |

---

### NFR-UI-015 · Institutional Typography

**What is being tested?**
That the entire interface uses exclusively the **Lucida Bright** font (with `Georgia` as a fallback), and that no more than 3 typographic levels are mixed per view.

**How is it tested?**

1. In Chrome DevTools, select any text element.
2. In the **Computed** tab of the inspector, look for the `font-family` property.
3. Verify that it reads `Lucida Bright` or `Georgia`.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Texts using the institutional font | 100% |
| Typographic levels per view | Maximum 3 (H1, H2/H3, body) |

---

### NFR-UI-016 · UADY Color Palette

**What is being tested?**
That institutional colors are used with exact HEX values, and that gold text never appears on a white background.

**Institutional palette:**

| Color | Use | HEX |
|---|---|---|
| UADY Blue | Backgrounds, structure, headers | `#192E4C` |
| UADY Gold | Emphasis, icons, primary actions | `#C89211` |

**How is it tested?**

1. Use the **ColorZilla** Chrome extension to inspect the color of any element.
2. Verify that primary colors match the defined HEX values exactly.
3. Specifically search for any instances of gold text on a white background (prohibited).

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Elements using the exact HEX codes | 100% |
| Gold text (#C89211) on white background | 0 instances |

---
### NFR-UI-017 · Consistent Iconography

**What is being tested?**
That all icons across the system come from the same library and share a consistent visual weight and style — no mixing of outlined icons with filled ones, or flat icons with 3D ones.

**How is it tested?**
Visual review of every screen in the system. The tester identifies the icon library in use (e.g., Material Icons, Heroicons, Font Awesome) and flags any icon that visually differs in style or weight from the rest.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Icons from a single library with consistent style | 100% |
| Icons that deviate in style or visual weight | 0 instances |

---

## Section 5 — Feedback and Interaction

The system must clearly communicate to the user what is happening at all times.

---

### NFR-UI-018 · Critical Action Confirmation

**What is being tested?**
That actions such as "Submit Application," "Make Payment," and "Delete Information" always request explicit user confirmation before executing.

**How is it tested?**
The tester triggers each critical action and verifies that a modal dialog or confirmation screen appears before the action is carried out.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Destructive/critical actions with a confirmation modal | 100% |

---

### NFR-UI-019 · Visual States of Interactive Elements

**What is being tested?**
That every button and link in the system has the 5 required distinct visual states.

**How is it tested?**
Component-by-component visual inspection:

| State | How to Force It in the Inspector |
|---|---|
| Default | Normal state of the element |
| Hover | Move the cursor over the element |
| Focus | Navigate to the element using Tab |
| Active | Click and hold the element |
| Disabled | Toggle the element's disabled attribute in DevTools |

>  In Chrome DevTools, states can also be forced via **Elements → :hov**.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Buttons and links with all 5 states implemented | 100% |

---

### NFR-UI-020 · Real-Time Form Validation

**What is being tested?**
That form fields validate their content as the user types — not only when the form is submitted.

**How is it tested?**

1. Navigate to any form in the system.
2. Enter invalid data in a restricted field (for example, an email address without `@`).
3. Move focus to the next field without submitting.
4. Verify that an inline error message appears immediately.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Restricted fields with inline validation | 100% |

---

### NFR-UI-021 · Success Messages

**What is being tested?**
That every successful action in the system — submitting a form, saving data, uploading a file — produces a clearly visible confirmation message.

**How is it tested?**
Walk through every complete flow in the system and trigger the successful outcome of each one. Verify that a success message appears and remains visible until the user explicitly dismisses it or the interface transitions automatically to the next state.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Successful actions followed by a visible confirmation message | 100% |
| Messages that disappear before the user can read them | 0 instances |

---

### NFR-UI-022 · Progress Indicator in Multi-Step Flows

**What is being tested?**
That in multi-step processes (such as registration), the user always knows which step they are on and how many steps remain.

**How is it tested?**
The most direct test: during a user session, ask out loud — *"How much is left to finish?"* The user must be able to answer correctly without scrolling or guessing.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Users who correctly answer "how much is left?" | 100%, without scrolling or guessing |

---

### NFR-UI-023 · Loading Indicators for Background Tasks

**What is being tested?**
That whenever the system is processing something (saving data, uploading files, querying records), it displays a visual indicator to let the user know something is happening.

**How is it tested?**
Simulate slow network conditions using Chrome DevTools → Network → `Slow 3G`. Trigger operations such as uploading a document or submitting a form, and verify that a spinner, progress bar, or skeleton screen appears during the wait.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Background operations with a visual indicator | 100% |

---

## Section 6 — Navigation

---

### NFR-UI-024 · Maximum Navigation Depth

**What is being tested?**
That any system functionality is reachable within a maximum of 3 clicks from the main dashboard.

**How is it tested?**
Map the complete sitemap of the system and count the clicks required to reach each functionality from the dashboard. Document the results in a traceability table.

**Example traceability table:**

| Functionality | Path | # Clicks |
|---|---|---|
| View application status | Dashboard → My Applications → Detail | 2 |
| Download certificate | Dashboard → My Events → Event → Certificate | 3 |
| Change password | Dashboard → Profile → Security | 2 |

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Functionalities reachable in ≤ 3 clicks | 100% |

---

### NFR-UI-025 · Breadcrumbs on Deep Pages

**What is being tested?**
That pages at level 3 or deeper display a breadcrumb trail that shows the current location and allows quick navigation back to higher levels.

**How is it tested?**
Navigate to each level-3+ view and visually inspect for the presence of a breadcrumb. Additionally, click each breadcrumb element to confirm it navigates correctly.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Level 3+ views with a functional breadcrumb | 100% |

---
### NFR-UI-026 · Consistent Navigation

**What is being tested?**
That the main navigation menu appears in the same position and with the same structure on every page of the system — users should never have to search for the navigation bar.

**How is it tested?**
Navigate through at least 10 different views across different sections of the system. On each view, verify that the navigation bar is in the same position and contains the same elements as on the dashboard.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Views where the navbar is in the same position and has the same elements | 100% |

---

### NFR-UI-027 · Current Location Indicator

**What is being tested?**
That the navigation element corresponding to the page the user is currently on is visually differentiated from the rest — commonly referred to as the "active state" in navigation.

**How is it tested?**
Navigate to each main section of the system. On each page, verify that the corresponding navigation item has a distinct visual treatment (different color, underline, bold weight, or background) compared to the inactive items.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Pages where the active navigation item is visually differentiated | 100% |

---


## Section 7 — Content and Readability

---

### NFR-UI-028 · Maximum Text Line Length

**What is being tested?**
That text blocks are not so wide that they become uncomfortable to read (lines exceeding 80 characters are considered difficult to follow).

**How is it tested?**

1. In Chrome DevTools, select the container of the main text block.
2. In the **Computed** tab, check the value of `max-width`.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| `max-width` of the main text container | Between 600px and 800px |

---

### NFR-UI-029 · Text Line Spacing

**What is being tested?**
That the space between lines is sufficient to make reading comfortable.

**How is it tested?**
In Chrome DevTools → Computed → verify the `line-height` property on `<p>` elements throughout the system.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| `line-height` on paragraphs | ≥ 1.5 (relative to font-size) |

---
### NFR-UI-030 · Visual Hierarchy

**What is being tested?**
That the system uses text size, weight, and color to establish a clear and consistent information hierarchy across all views, so users can immediately distinguish headings from subheadings and body text.

**How is it tested?**
Heuristic evaluation: a UX evaluator reviews each view and verifies that H1, H2, H3, and body text are visually distinct from one another using size, weight, or color — and that this hierarchy is applied consistently across all pages.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Views with clear visual differentiation between H1, H2, H3, and body | 100% |
| Views where hierarchy is inconsistent or ambiguous | 0 instances |

---

### NFR-UI-031 · Plain Language

**What is being tested?**
That the instructions and labels in the system are understandable by non-technical users.

**How is it tested?**

1. Ask a participant with no technical background to read the instructions on the main forms.
2. Ask them: *"Did you understand what you need to do here?"* — without providing any hints.
3. Record whether they needed to re-read more than twice.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Users who understand instructions without more than 2 re-reads | ≥ 90% |

---

## Section 8 — Specific Use Cases

---

### NFR-UI-032 · Document Upload Component

**What is being tested?**
That the file upload component shows a preview, clearly indicates accepted formats, and confirms a successful upload.

**How is it tested?**

```
[ ] When a PDF is selected, does a preview or filename appear?
[ ] Does the component indicate accepted formats before the user selects a file?
[ ] After a successful upload, does a visual success indicator (icon or message) appear?
[ ] If an unsupported format is uploaded, is there a clear error message?
```

---

### NFR-UI-033 · Enrollment Request Form

**What is being tested?**
That the form visually groups related fields, marks required fields, shows character counters, and allows the user to save progress.

**Verification checklist:**

```
[ ] Are fields grouped visually by category (personal data, academic data, etc.)?
[ ] Are required fields marked with an asterisk (*)?
[ ] Do fields with character limits display a counter (e.g., "150/300")?
[ ] Is there a "Save Draft" button or equivalent?
[ ] During user testing, did no participant abandon the form mid-way?
```

---

### NFR-UI-034 · Personal Dashboard — "My Events" View

**What is being tested?**
That event cards display key information clearly and present obvious primary actions.

**How is it tested?**
**5-second test:** show the screen to the user for 5 seconds, then hide it and ask:
- What is the name of the event?
- What is its status (upcoming / in progress / finished)?
- What is the date?
- What action can you take from here?

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Users who correctly answer all 4 questions | ≥ 90% |

---

### NFR-UI-035 · Payment Flow

**What is being tested?**
That the payment process builds user confidence and does not cause abandonments due to confusion.

**Flow checklist:**

```
[ ] Is a purchase summary displayed before payment is processed?
[ ] Are payment methods shown with recognizable icons (Visa, Mastercard, etc.)?
[ ] Is there a visible security indicator (SSL padlock, encryption text)?
[ ] After a successful payment, is there a dedicated confirmation screen?
```

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Abandonments due to confusion in tests with 10 users | 0 abandonments |

---

## Section 9 — Notifications and Alerts

---

### NFR-UI-036 and NFR-UI-037 · Notification System

**What is being tested?**
That notifications use the correct color for their type, always appear in the same position, and do not cover important content.

**Types and expected colors:**

| Type | Color | Example |
|---|---|---|
| Success | Green | "Your application was submitted successfully" |
| Warning | Yellow / Orange | "Your session will expire in 5 minutes" |
| Error | Red | "The payment could not be processed" |
| Information | Blue | "The enrollment period closes on January 30" |

**How is it tested?**

1. Intentionally trigger each type of notification during functional testing.
2. Verify color, position, and that no notification covers active buttons or form fields.

**How do I know it passed?**

| Metric | Acceptance Criterion |
|---|---|
| Notifications with the correct color for their type | 100% |
| Consistent position across views | 100% |
| Notifications that block interactive content | 0 instances |

---

## Consolidated Test Summary

| ID | Category | Test Method | Tool / Technique | Acceptance Criterion |
|----|---|---|---|---|
| NFR-UI-001 | Usability | User testing | SUS + Task Success Rate | Score ≥ 70, rate > 70% |
| NFR-UI-002 | Usability | Comparative testing | Time-on-Task (sessions 1 and 2) | ≥ 30% time reduction |
| NFR-UI-003 | Usability | Think-Aloud | Moderated observation | < 2 fatal errors |
| NFR-UI-004 | Usability | Heuristic evaluation | Nielsen checklist | 100% messages meet 3 criteria |
| NFR-UI-005 | Usability | Functional verification | Flow walkthrough | 100% actions with confirmation |
| NFR-UI-006 | Accessibility | Automated audit | WAVE (Chrome) | 0 Level A errors |
| NFR-UI-007 | Accessibility | Contrast measurement | WebAIM Checker | 4.5:1 normal text / 3:1 large |
| NFR-UI-008 | Accessibility | Manual testing | Keyboard (Tab, Enter, Esc) | 100% functionalities accessible |
| NFR-UI-009 | Accessibility | Element inspection | DevTools (px) | ≥ 44×44px, separation ≥ 8px |
| NFR-UI-010 | Responsive | Visual testing | DevTools / BrowserStack | No horizontal scroll or errors |
| NFR-UI-011 | Responsive | Visual review | Desktop vs. mobile comparison | Components reorganize |
| NFR-UI-014 | Brand | Checklist | UADY Identity Manual | Signature and texture correct |
| NFR-UI-015 | Typography | CSS inspection | DevTools → font-family | 100% Lucida Bright / Georgia |
| NFR-UI-016 | Color | HEX audit | ColorZilla + DevTools | 100% exact HEX codes |
| NFR-UI-018 | Interaction | Functional verification | Flow walkthrough | 100% critical actions with modal |
| NFR-UI-019 | Interaction | Visual inspection | DevTools → :hov | 5 states on 100% of elements |
| NFR-UI-020 | Interaction | Functional testing | Manual form testing | 100% fields with inline validation |
| NFR-UI-022 | Interaction | User testing | Direct question in session | 100% answer without scrolling |
| NFR-UI-024 | Navigation | Sitemap mapping | Click count | 100% functionalities in ≤ 3 clicks |
| NFR-UI-025 | Navigation | Visual inspection | Review of deep views | 100% level 3+ views with breadcrumb |
| NFR-UI-028 | Readability | CSS inspection | DevTools → max-width | Between 600px and 800px |
| NFR-UI-036 | Notifications | Visual review | Trigger each type | 100% correct color and fixed position |

---

## Test Implementation Priority Guide

If testing resources are limited, execute in this order:

**Priority 1 — Critical (blocks release):**
NFR-UI-001, NFR-UI-006, NFR-UI-007, NFR-UI-015, NFR-UI-033, NFR-UI-035

**Priority 2 — Important (next iteration):**
NFR-UI-009, NFR-UI-011, NFR-UI-019, NFR-UI-023, NFR-UI-037

**Priority 3 — Desirable (refinement):**
NFR-UI-016, NFR-UI-017, NFR-UI-029, NFR-UI-030

