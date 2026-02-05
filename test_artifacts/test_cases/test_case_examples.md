# Test Cases

## Summary

| ID    | Name                                                     | Priority | Tags              | Requirements                                                                                                                                  |
| :---- | :------------------------------------------------------- | :------- | :---------------- | :-------------------------------------------------------------------------------------------------------------------------------------------- |
| WT-29 | Verify Theme toggle interaction speed                    | high     | Functional,Header | [FR-HEADER-002.3 Theme Toggle Interaction](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)  |
| WT-32 | Verify Theme Persistence Across Page Navigation          | high     | Functional,Header | [FR-HEADER-002.4 Theme Persistence](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)         |
| WT-34 | Theme persists across logout and subsequent return       | high     | Functional,Header | [FR-HEADER-002.4 Theme Persistence](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)         |
| WT-35 | Invalid theme value in localStorage is handled correctly | high     | Functional,Header | [FR-HEADER-002.2.2 Default Theme Selection](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md) |
| WT-66 | Default theme when no saved preference                   | high     | Functional,Header | [FR-HEADER-002.2.1 Default Theme Selection](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md) |
| WT-67 | Verify Theme Toggle Interaction                          | high     | Functional,Header | [FR-HEADER-002.3 Theme Toggle Interaction](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)  |
| WT-84 | Apply saved theme from localStorage                      | high     | Functional,Header | [FR-HEADER-002.2.2 Default Theme Selection](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md) |

## Detailed Test Case Specifications

### WT-29: Verify Theme toggle interaction speed

- **Priority:** high
- **Tags:** Functional,Header
- **Requirement:** [FR-HEADER-002.3 Theme Toggle Interaction](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)

#### Precondition

Application is open with Light theme active.

#### Steps

Click the Theme Toggle rapidly 5–10 times.<br>Double-click the toggle.<br>Click and hold.

#### Expected Results

Theme switches.<br>localStorage is updated with theme preference.

---

### WT-32: Verify Theme Persistence Across Page Navigation

- **Priority:** high
- **Tags:** Functional,Header
- **Requirement:** [FR-HEADER-002.4 Theme Persistence](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)

#### Precondition:

Open /welcome. Theme change to Dark.

#### Steps

Navigate to public page (e.g., /signin, /signup).<br>Use browser back/forward buttons.<br>Log in and navigate to private page (e.g., /home).<br>Open page in new tab.

#### Expected Results

Selected theme Dark persists across all page navigations.

---

### WT-34: Theme persists across logout and subsequent return

- **Priority:** high
- **Tags:** Functional,Header
- **Requirement:** [FR-HEADER-002.4 Theme Persistence](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)

#### Precondition

User is authenticated and has set theme to Dark.

#### Steps

Log out of the application.<br>Refresh page.<br>Log in.

#### Expected Results

Theme remains Dark (preference is not lost on logout).

---

### WT-35: Invalid theme value in localStorage is handled correctly

- **Priority:** high
- **Tags:** Functional,Header
- **Requirement:** [FR-HEADER-002.2.2 Default Theme Selection](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)

#### Precondition

Invalid theme value is present in localStorage (e.g., "", "random", 123, {}, \[], true). User is on any page.

#### Steps and Expected Results

**Step 1:** Reload app.

**Expected:** The application falls back to a default theme (Light) without errors or broken styling.

**Step 2:** Click the Theme Toggle.

**Expected:** Theme switches to the other supported theme and localStorage is corrected to a valid value.

---

### WT-66: Default theme when no saved preference

- **Priority:** high
- **Tags:** Functional,Header
- **Requirement:** [FR-HEADER-002.2.1 Default Theme Selection](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)

#### Precondition

Clear browser localStorage

#### Steps

Open application.<br>Verify localStorage for theme value.

#### Expected Results

Light theme is applied by default.<br>localStorage contains theme preference value.

---

### WT-67: Verify Theme Toggle Interaction

- **Priority:** high
- **Tags:** Functional,Header
- **Requirement:** [FR-HEADER-002.3 Theme Toggle Interaction](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)

#### Precondition

Application is open with Dark theme active.

#### Steps

Click toggle from Dark → Light, verify theme change.<br>Click toggle from Light → Dark, verify theme change.<br>Verify localStorage value.

#### Expected Results

Theme switches from Dark → Light and Light → Dark.<br>localStorage is updated with theme preference.

---

### WT-84: Apply saved theme from localStorage

- **Priority:** high
- **Tags:** Functional,Header
- **Requirement:** [FR-HEADER-002.2.2 Default Theme Selection](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)

#### Precondition

Application is open. Set Dark theme.

#### Steps

Close browser, reopen.<br>Verify localStorage value.<br>Repeat for Light theme.

#### Expected Results

Correct theme applied from localStorage.

---
