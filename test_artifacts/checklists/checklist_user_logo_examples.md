# User Logo Display Logic Validation (Decision Table)

## Application Context

- **Feature**: User Logo Component
- **Requirements**: [4.3 User Logo Display Logic](https://github.com/NatHumeniuk/water-tracker-tests/blob/main/requirements/requirements_header.md)

## Decision Table

| Condition   | Parameters               | Case 1 | Case 2 | Case 3 | Case 4 |
| ----------- | ------------------------ | ------ | ------ | ------ | ------ |
| User Email  | Always `True (T)`        | T      | T      | T      | T      |
| User Name   | `True (T)` / `False (F)` | T      | T      | F      | F      |
| User Avatar | `True (T)` / `False (F)` | T      | F      | T      | F      |

| Action                                   | Case 1 | Case 2 | Case 3 | Case 4 |
| ---------------------------------------- | ------ | ------ | ------ | ------ |
| Name as text label                       | X      | X      |        |        |
| Email as text label                      |        |        | X      | X      |
| User’s avatar image                      | X      |        | X      |        |
| Name as placeholder avatar (1st letter)  |        | X      |        |        |
| Email as placeholder avatar (1st letter) |        |        |        | X      |

---

## Base Scenarios Checklists

| #   | Scenario                | User Name | User Avatar | Text Label Display | Visual Avatar Display             | Checklist ID |
| --- | ----------------------- | :-------: | :---------: | ------------------ | --------------------------------- | ------------ |
| 1   | name+avatar+email       |     ✓     |      ✓      | User Name          | User's Avatar Image               | WT-048       |
| 2   | name+no avatar+email    |     ✓     |      ✗      | User Name          | Name as Placeholder (1st letter)  | WT-049       |
| 3   | no name+avatar+email    |     ✗     |      ✓      | Email Prefix       | User's Avatar Image               | WT-092       |
| 4   | no name+no avatar+email |     ✗     |      ✗      | Email Prefix       | Email as Placeholder (1st letter) | WT-050       |

**Legend:**

- ✓ = Present/True
- ✗ = Absent/False
