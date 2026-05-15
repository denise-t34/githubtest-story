# STORY-1126 — Paste Examples

## New Cases

---

### C36650 — Purely unordered list

Paste into the **story AC area**.

- Define user roles and permissions
- Set up authentication flow
- Design the dashboard layout
- Write API documentation

---

### C36651 — Nested unordered list

Paste into the **story AC area**.

- User management
  - Create new users
  - Edit existing users
  - Deactivate accounts
- Notifications
  - Email alerts
  - In-app notifications
- Reporting
  - Export to CSV
  - Schedule reports

---

### C36652 — Mixed ordered and unordered

Paste into the **story AC area**. Ordered items should become ACs; unordered items should fall back to plain text.

1. Review existing architecture
2. Identify performance bottlenecks
3. Implement caching layer

- Consider Redis or Memcached
- Check CDN configuration

4. Run load tests
5. Deploy to staging

---

### C36653 — Unordered list containing an ordered sublist

Paste into the **story AC area**. The presence of the ordered sublist should cause the entire paste to be treated as mixed.

- Onboarding flow
  - Welcome screen
  1. Enter your name
  2. Select your role
  3. Choose a team

Include a paragraph in between
- Confirmation screen
- Dashboard setup

---

### C36654 — Purely unordered list in the draft editor

Same content as C36650. Paste into the **draft editor AC area**.

- Define user roles and permissions
- Set up authentication flow
- Design the dashboard layout
- Write API documentation

---

## Regression Cases

---

### C35842 — Purely ordered list

Paste into the **story AC area**. Items should become nested sub-ACs.

1. Gather requirements
2. Write technical spec
3. Break into stories
4. Assign to sprint

---

### C35847 — Deeply nested ordered list (depth > 10)

Paste into an AC field **already at nesting level 9**. Items that would exceed depth 10 should be inserted as plain text.

1. Level 1
   1. Level 2
      1. Level 3 — this and anything deeper should flatten to plain text when pasted at level 9

---

### C35846 — Mixed paste (verify unordered plain text format)

Same content as C36652. Verify unordered items are preceded by a newline and the last item is followed by a newline.

1. Review existing architecture
2. Identify performance bottlenecks
3. Implement caching layer

- Consider Redis or Memcached
- Check CDN configuration

4. Run load tests
5. Deploy to staging

---

### C35850 — Purely unordered list in description and additional notes fields

Same content as C36650. Paste into the **description field** and then the **additional notes field**. Should not convert to ACs in either.

- Define user roles and permissions
- Set up authentication flow
- Design the dashboard layout
- Write API documentation

---

### C35841 — Inline formatting preserved across ordered and unordered lists

Paste into the **story AC area**. This is a mixed paste — ordered items should become ACs with formatting intact; unordered items should fall back to plain text with formatting intact.

1. **Define** the scope of the authentication redesign
2. *Review* the findings from the security audit
3. ~~Migrate legacy session tokens~~ — already completed in the previous sprint
4. Implement `validateToken()` with proper error handling
5. <u>Sign off with the security team before shipping</u>

- **Bold** items indicate blockers that need immediate attention
- *Italicised* notes are advisory and can be deferred
- ~~Struck-through~~ items have already been resolved
- Inline `code` references a specific function or value
- <u>Underlined</u> items require a sign-off before the story can be closed
