```
                         ┌──────────────┐
                         │    Date      │
                         │──────────────│
                         │ DateKey (PK) │
                         │ Date         │
                         │ Year         │
                         │ Month        │
                         │ Quarter      │
                         │ Week         │
                         │ Weekday      │
                         └──────────────┘
                               ▲
                               │
                      ┌────────┴────────┐
                      │                 │
                 ┌──────────────┐   ┌──────────────┐
                 │  Employees   │   │ Departments   │
                 │──────────────│   │──────────────│
                 │ EmpID (PK)   │   │ DeptID (PK)   │
                 │ FullName     │   │ DeptName      │
                 │ Gender       │   │ Function      │
                 │ BirthDate    │   │ HeadcountTarget│
                 │ HireDate     │   └──────────────┘
                 │ TerminationDate │
                 │ ManagerID    │  → self-reference
                 │ DeptID (FK)  │
                 └──────────────┘
                        ▲
                        │
                 ┌──────┴─────────────┐
                 │  EmployeeEvents    │
                 │────────────────────│
                 │ EventID (PK)       │
                 │ EventDateKey (FK)  │ → Date
                 │ EmpID (FK)         │ → Employees
                 │ EventType          │ (Hire, Termination, Promotion, Transfer)
                 │ FromDeptID         │
                 │ ToDeptID           │
                 │ Comment            │
                 └────────────────────┘
```

## 🔍 Table Overview

| Table            | Type      | Description                                                                             |
| ---------------- | --------- | --------------------------------------------------------------------------------------- |
| `EmployeeEvents` | Fact      | Tracks hires, terminations, promotions, transfers — can have multiple rows per employee |
| `Employees`      | Dimension | Current or historical employee attributes (self-referencing manager)                    |
| `Departments`    | Dimension | Department metadata with targets and business function                                  |
| `Date`           | Dimension | Calendar with fiscal columns and continuous range                                       |

## ⚠️ Planned Edge Cases

| Type of Challenge                | Where It Appears              | Purpose                                                     |
| -------------------------------- | ----------------------------- | ----------------------------------------------------------- |
| Missing foreign keys             | `FromDeptID`, `ToDeptID`      | Simulate unknown/invalid departments                        |
| Duplicated employee records      | `Employees`                   | Detect via EmpID or email                                   |
| Manager loops or gaps            | `Employees.ManagerID`         | Stress-test self-reference relationships                    |
| Multiple events per employee     | `EmployeeEvents`              | Evaluate snapshot logic and filtering                       |
| Gaps or out-of-order event dates | `EmployeeEvents.EventDateKey` | Test time intelligence or sorting logic                     |
| Future-dated terminations        | `TerminationDate`             | Trigger incorrect active headcount unless handled carefully |
| Unused departments               | `Departments`                 | Challenge LEFT JOIN awareness                               |
| High-cardinality event comments  | `EmployeeEvents.Comment`      | Introduce performance inefficiency                          |

## 🎯 Modeling & DAX Use Cases

- Calculate active headcount over time
- Identify churn rate by department or manager
- Compare promotions vs transfers across departments
- Build employee journey drillthrough (from Employee table to events)
- Handle role-playing date (HireDate vs EventDate vs TerminationDate)
