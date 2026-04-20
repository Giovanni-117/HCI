# Non-Functional Requirements
## User Interface and HCI - Graduates and External Professionals

> **Target Demographic Context:** Graduates and external professionals seeking diploma courses or continuing education. This group combines demanding professional careers with academic study, meaning every interaction with the system must be optimized for **speed, clarity, and accessibility**. They don't have time to decipher confusing navigation — the system must adapt to them, not the other way around.

---

## 1. USABILITY

### NFR-UI-001: Intuitiveness (First-Time Use)
The interface must be designed so that the target demographic (professionals with limited time) can navigate the system and complete critical tasks (e.g., account creation) immediately upon their first encounter without prior training or guidance.
**Verification Metric:** Initial Task Success Rate.
**Acceptance Criteria:** Completion rate > 80% on the first attempt, without moderator intervention or manual consultation.

### NFR-UI-002: Learnability (Efficiency Gain)
The system must exhibit a shallow learning curve, where users who have completed a task once can perform the same or similar tasks significantly faster and with fewer errors in subsequent sessions.
**Verification Metric:** Time-on-Task (ToT) comparison between the 1st and 3rd attempts.
**Acceptance Criteria:** A minimum 30% reduction in average time-on-task by the third repetition of a specific workflow.

### NFR-UI-003: Error Prevention
The interface must prevent common user errors before form submission through preventive validations (Poka-Yoke) and visual constraints (e.g., disabling buttons until the form is valid).

**Verification Metric:** Number of errors committed during moderated testing sessions (Think-Aloud Protocol).
**Acceptance Criteria:** Users commit fewer than 2 non-recoverable (fatal) errors in the complete flow.

### NFR-UI-004: Clarity of Error Messages
All error messages must:
- Clearly indicate what is wrong
- Explain how to fix it
- Be written in non-technical language

**Verification Metric:** Heuristic evaluation according to Nielsen's principles.
**Acceptance Criteria:** 100% of error messages meet all three criteria.

### NFR-UI-005: Error Recovery
The user must be able to undo or correct any action before final confirmation.

**Verification Metric:** Functional verification of flows.
**Acceptance Criteria:** All critical actions have prior confirmation.

---

## 2. ACCESSIBILITY

### NFR-UI-006: Pragmatic WCAG 2.1 Conformity
The interface must comply with the principles of perceivability and operability in the main flows (happy path).

**Verification Metric:** Audit using automated tools (Chrome WAVE).
**Acceptance Criteria:** 0 critical Level A errors in the audited flows. Level AA will be applied primarily to text contrast.

### NFR-UI-007: Color Contrast
All texts must have a minimum contrast ratio of:
- 4.5:1 for normal text
- 3:1 for large text (18pt or 14pt bold)

**Verification Metric:** Analysis with contrast tools (WebAIM Contrast Checker).
**Acceptance Criteria:** 100% of texts meet minimum ratios.

### NFR-UI-008: Keyboard Navigation
All system functionalities must be accessible using only the keyboard, without requiring a mouse.

**Verification Metric:** Manual testing of complete keyboard navigation.
**Acceptance Criteria:** 100% of functionalities accessible via keyboard with logical tab order.

### NFR-UI-009: Touch Target Size
Interactive elements (buttons, links, form fields) must have a minimum area of 44x44 pixels on mobile devices.

**Verification Metric:** Measurement of elements in browser inspector.
**Acceptance Criteria:** 100% of interactive elements meet the minimum size.

---

## 3. RESPONSIVE DESIGN

### NFR-UI-10: Supported Breakpoints
The system must provide optimized experiences for the following viewport ranges:
- Mobile: 320px - 767px
- Tablet: 768px - 1023px
- Desktop: 1024px and above

**Verification Metric:** Visual testing on real devices and emulators.
**Acceptance Criteria:** Functional and legible layout across all breakpoints without horizontal scrolling.

### NFR-UI-011: Content Adaptation
Interface elements must reorganize (not just resize) appropriately according to screen size.

**Verification Metric:** Visual review across different devices.
**Acceptance Criteria:** Navigation, forms, and tables adapt without loss of functionality.

### NFR-UI-012: Responsive Images
Images must load in appropriate resolutions according to the device.

**Verification Metric:** Verification of srcset/picture implementation.
**Acceptance Criteria:** Images use srcset or picture element.

### NFR-UI-013: Touch-Friendly on Mobile
Interactive elements on mobile must have sufficient spacing to prevent accidental clicks (minimum 8px separation).

**Verification Metric:** Visual review and testing on touch devices.
**Acceptance Criteria:** Minimum 8px separation between adjacent interactive elements.

---

## 4. VISUAL CONSISTENCY

### NFR-UI-014: UADY Design System and Brand
The system must feel like a digital extension of UADY, strictly complying with the Visual Design Guide and the University Identity Manual. The institutional signature (Shield + UADY) must always appear in the top-left quadrant (navbar).

**Verification Metric:** UADY Visual Conformity Checklist (Section 12 of the guide).
**Acceptance Criteria:** Immovable presence of the UADY signature and exclusive implementation of the "Arcos 2023" texture without overlapping content.

### NFR-UI-015: Institutional Typography
The system will exclusively use the **Lucida Bright** (institutional) font to establish academic seriousness and visual hierarchy.

**Verification Metric:** CSS inspection.
**Acceptance Criteria:** 100% of visible text uses `Lucida Bright` (or `Georgia` as fallback), respecting the restriction of a maximum of 3 typographic levels per view.

### NFR-UI-016: UADY Color Palette
The interface will be governed by the institutional colors: **Blue (#192E4C)** as structure/backgrounds and **Gold (#C89211)** as emphasis/focus. Gold will never be used as text on a white background.

**Verification Metric:** Audit of CSS tokens and contrast.
**Acceptance Criteria:** 100% of primary, secondary, and warning notifications use the exact HEX codes defined in the UADY guide.

### NFR-UI-017: Consistent Iconography
Icons must come from a single library and maintain consistent visual weight and style.

**Verification Metric:** Visual review of all icons.
**Acceptance Criteria:** 100% of icons from the same library with a consistent style.

---

## 5. FEEDBACK AND INTERACTION

### NFR-UI-018: Action Confirmation
All critical actions (submit application, make payment, delete information) must require explicit user confirmation.

**Verification Metric:** Review of user flows.
**Acceptance Criteria:** 100% of destructive or critical actions have a confirmation modal.

### NFR-UI-019: Visual States of Interactive Elements
All interactive elements must have distinct visual states for:
- Default
- Hover
- Focus
- Active
- Disabled

**Verification Metric:** Visual inspection of components.
**Acceptance Criteria:** All buttons and links implement the 5 states.

### NFR-UI-020: Form Feedback
Form fields must provide real-time (inline) validation in addition to validation upon submission.

**Verification Metric:** Functional testing of forms.
**Acceptance Criteria:** Inline validation on 100% of restricted fields.

### NFR-UI-021: Success Messages
All successful actions must show a clearly identifiable visual confirmation message.

**Verification Metric:** Review of complete flows.
**Acceptance Criteria:** Success message visible until explicitly dismissed by the user or managed by automatic state transitions.

### NFR-UI-022: Progress Indicators
Multi-step processes (like registration) must show a visual progress indicator displaying the current step and remaining steps.

**Verification Metric:** Review of multi-step flows.
**Acceptance Criteria:** Progress bar or stepper visible in all flows with more than 2 steps.

### NFR-UI-023: Background Task Indicators
Any operation that processes in the background must show a visual progress or loading indicator.

**Verification Metric:** Manual review of background flows.
**Acceptance Criteria:** All processing operations display a visual indicator until complete.

---

## 6. NAVIGATION

### NFR-UI-024: Navigation Depth
Any system functionality must be accessible in a maximum of 3 clicks from the main dashboard.

**Verification Metric:** Sitemap mapping and click count.
**Acceptance Criteria:** 100% of functionalities accessible in ≤ 3 clicks.

### NFR-UI-025: Breadcrumbs
Deep content pages must include breadcrumbs indicating the current location and allowing quick navigation to higher levels.

**Verification Metric:** Review of level-3 or deeper views.
**Acceptance Criteria:** Breadcrumbs present in all level 3+ views.

### NFR-UI-026: Consistent Navigation
The main navigation menu must maintain the same position and structure across all pages of the system.

**Verification Metric:** Visual review of navigation across different views.
**Acceptance Criteria:** Navigation in the same position and with the same elements in 100% of views.

### NFR-UI-027: Current Location Indicator
The navigation element corresponding to the current page must be visually differentiated (active state).

**Verification Metric:** Visual inspection of navigation.
**Acceptance Criteria:** Active state visible in 100% of pages.

---

## 7. CONTENT AND READABILITY

### NFR-UI-028: Line Length
Text lines should not exceed 80 characters (approximately 600px) for optimal readability.

**Verification Metric:** Measurement of text container width.
**Acceptance Criteria:** Main text blocks have a max-width of 600-800px.

### NFR-UI-029: Line Spacing
The line-height for body text must be at least 1.5 times the font size.

**Verification Metric:** CSS inspection.
**Acceptance Criteria:** line-height ≥ 1.5 in all paragraphs.

### NFR-UI-030: Visual Hierarchy
The system must use text size, weight, and color to establish a clear hierarchy of information.

**Verification Metric:** Heuristic evaluation of hierarchy.
**Acceptance Criteria:** Clear differentiation between H1, H2, H3, and body text in all views.

### NFR-UI-031: Clear Language
Instructions and labels must be written in simple language, avoiding technical or administrative jargon.

**Verification Metric:** Content review with non-technical users.
**Acceptance Criteria:** 90% of users understand instructions without needing clarification.

---

## 8. USE CASE SPECIFICS

### NFR-UI-032: Document Upload (CU-PG-006)
The file upload component must:
- Show a preview of files before uploading
- Clearly indicate accepted formats
- Confirm successful upload with a visual mark

**Verification Metric:** Functional testing of the component.
**Acceptance Criteria:** Meets all criteria in tests.

### NFR-UI-033: Registration Form (CU-PG-004)
The registration request form must:
- Visually group related fields
- Indicate mandatory fields with an asterisk (*)
- Show a character counter on limits
- Allow saving progress

**Verification Metric:** Heuristic evaluation and user testing.
**Acceptance Criteria:** Meets all 4 requirements and users complete the form without abandoning.

### NFR-UI-034: Personal Dashboard (CU-PG-009)
The "My Events" view must present information in a card format with:
- Clearly visible event title
- Visual state (upcoming/in progress/finished)
- Highlighted dates
- Obvious primary action (access/download certificate)

**Verification Metric:** Visual evaluation and user tests.
**Acceptance Criteria:** Users successfully identify key information without errors.

### NFR-UI-035: Payment Process (CU-PG-005)
The payment flow must:
- Show a purchase summary before paying
- Indicate accepted payment methods with recognizable icons
- Show security indicators (SSL padlock)
- Confirm successful payment with a dedicated screen

**Verification Metric:** User testing in a staging environment.
**Acceptance Criteria:** 0 abandonments due to confusion in testing with 10 users.

---

## 9. NOTIFICATIONS AND ALERTS

### NFR-UI-036: Notification Hierarchy
The system must visually differentiate between:
- Success (green)
- Warning (yellow/orange)
- Error (red)
- Information (blue)

**Verification Metric:** Review of notification system.
**Acceptance Criteria:** Consistent colors by type in 100% of notifications.

### NFR-UI-037: Notification Position
Notifications must appear in a consistent location (e.g., top right) without blocking critical content.

**Verification Metric:** Visual testing of notifications.
**Acceptance Criteria:** Notifications in the same position and do not block interactive elements.

---

## 10. VERIFICATION SUMMARY TABLE

| ID | Category | Requirement | Verification Method | Quantifiable Criteria |
|----|----------|-------------|---------------------|-----------------------|
| NFR-UI-001 | Usability | Intuitiveness | Task Success Rate | ≥ 80% success (1st try) |
| NFR-UI-002 | Usability | Learnability | Comparee each attemp | 30% reducction in time-on-task  |
| NFR-UI-003 | Usability | Error Prevention | Think-Aloud Observation | < 2 fatal errors |
| NFR-UI-006 | Accessibility | Pragmatic WCAG A | WAVE Audit | 0 Level A errors (Main) |
| NFR-UI-007 | Accessibility | Color Contrast | WebAIM Checker | 4.5:1 (text) |
| NFR-UI-009 | Accessibility | Touch Target | px Measurement | ≥ 44x44px |
| NFR-UI-010 | Responsive | Breakpoints | Visual Testing | 320-767-1024px |
| NFR-UI-014 | UADY Brand | Identity Check | Conformity Checklist | Meets signature/texture |
| NFR-UI-015 | Typography | Lucida Bright | CSS Inspection | 100% inst. font |
| NFR-UI-016 | Colors | UADY Blue/Gold | HEX Audit | 100% strict compliance |
| NFR-UI-024 | Navigation | Depth | Click count | ≤ 3 clicks |
| NFR-UI-032 | Specific | Visual Tracking | User testing | 95% identify status |

---

## IMPLEMENTATION NOTES

**Suggested Prioritization:**
- Critical (implement first): NFR-UI-001, 006, 007, 015, 025, 033
- Important (next phase): NFR-UI-009, 011, 019, 023, 037
- Desirable (refinement): NFR-UI-016, 017, 029, 030

**Recommended Verification Tools:**
- WAVE (Accessibility)
- WebAIM Contrast Checker (Contrast)
- BrowserStack (Responsive)
- UserTesting / Think-Aloud Sessions
