# Data Directory

Place your data files here before running the notebook.

## Required Files

| File | Format | Description |
|------|--------|-------------|
| `department-v2.csv` | CSV | Department training data |
| `seniority-v2.csv` | CSV | Seniority training data |
| `testdata.txt` | JSON | Test CV profiles |

## Optional Files

| File | Description |
|------|-------------|
| `more.txt` | Additional test CVs |

---

## CSV Format (Training Data)

```csv
text,label
Software Engineer,Information Technology
Sales Manager,Sales
CEO,Management
Junior Developer,Junior
```

## JSON Format (Test Data)

```json
[
  [
    {
      "position": "Senior Software Engineer",
      "organization": "Google",
      "seniority": "Senior",
      "department": "Information Technology",
      "status": "ACTIVE"
    }
  ]
]
```

## Labels

**Seniority:** Junior, Professional, Senior, Lead, Director, Management

**Department:** Administrative, Business Development, Consulting, Customer Support, Human Resources, Information Technology, Marketing, Other, Project Management, Purchasing, Sales
