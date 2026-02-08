# User Name Validation (Equivalence Partitioning and BVA)

## Application Context

- **Feature**: SettingModal Component
- **Field**: User Name (text input)
- **Validation Rules**:
  - Length: 1-32 characters
  - Allowed: Letters (any language), numbers, spaces, special characters

## User Name Validation – Checklist

| Class   | Subclass               | Value                    | Expected Result                    | Checklist ID |
| ------- | ---------------------- | ------------------------ | ---------------------------------- | ------------ |
| Valid   | Min boundary (1 char)  | `"A"`                    | Accepted                           | WT-148       |
| Valid   | Max boundary (32 char) | `"A" x 32`               | Accepted                           | WT-149       |
| Valid   | Latin only             | `"John Doe"`             | Accepted                           | WT-150       |
| Valid   | With spaces            | `"John  Doe"` (2 spaces) | Trimmed                            | WT-151       |
| Valid   | Cyrillic only          | `"Ольга Шевчук"`         | Accepted                           | WT-152       |
| Valid   | Chinese only           | `"王小明"`               | Accepted                           | WT-153       |
| Valid   | With numbers           | `"007 James Bond"`       | Accepted                           | WT-154       |
| Valid   | With emoji             | `"😊 John Smith"`        | Accepted                           | WT-155       |
| Valid   | With symbols           | `"Σ∫∂ User"`             | Accepted                           | WT-156       |
| Valid   | Mixed Latin + Cyrillic | `"John Шевчук"`          | Accepted                           | WT-157       |
| Invalid | Empty string           | `""`                     | Error: **Name required**           | WT-158       |
| Invalid | Only spaces            | `" "`                    | Error: **Name required (trimmed)** | WT-159       |
| Invalid | Above max (33 char)    | `"A" x 33`               | Error: **Max 32 characters**       | WT-160       |
| Invalid | Leading spaces         | `" John"`                | Trimmed                            | WT-161       |
| Invalid | Trailing spaces        | `"John "`                | Trimmed                            | WT-162       |
