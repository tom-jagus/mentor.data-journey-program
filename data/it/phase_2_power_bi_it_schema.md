```
                           ┌──────────────┐
                           │    Date      │
                           │──────────────│
                           │ DateKey (PK) │
                           │ Date         │
                           │ Year         │
                           │ Month        │
                           │ Week         │
                           │ Weekday      │
                           │ IsWeekend    │
                           └──────────────┘
                                 ▲
                                 │
                        ┌────────┴────────┐
                        │                 │
                   ┌──────────────┐   ┌──────────────┐
                   │  Employees   │   │    Teams     │
                   │──────────────│   │──────────────│
                   │ EmpID (PK)   │   │ TeamID (PK)  │
                   │ FullName     │   │ TeamName     │
                   │ Department   │   │ Location     │
                   │ JobTitle     │   │ Speciality   │
                   │ HireDate     │   │ ManagerName  │
                   └──────────────┘   └──────────────┘
                        ▲                 ▲
                        │                 │
                        └─────┬──────┬─────┘
                              │      │
                              ▼      ▼
                       ┌────────────────────┐
                       │      Tickets       │
                       │────────────────────│
                       │ TicketID (PK)      │
                       │ CreatedDateKey (FK)│ → Date
                       │ ClosedDateKey (FK) │ → Date
                       │ EmployeeID (FK)    │ → Employees
                       │ AssignedTeamID (FK)│ → Teams
                       │ SLA_ID (FK)        │ → SLA_Thresholds
                       │ Priority           │
                       │ Status             │
                       │ TimeToClose (hrs)  │
                       │ SLA_Violated       │
                       │ Category           │
                       └────────────────────┘
                              ▲
                              │
                        ┌─────┴────────────┐
                        │  SLA_Thresholds  │
                        │──────────────────│
                        │ SLA_ID (PK)      │
                        │ Priority         │
                        │ MaxHoursAllowed  │
                        │ SLA_Name         │
                        └──────────────────┘
```

## 🔍 Schema Summary

| Table            | Type      | Key Fields                        | Notes                                                       |
| ---------------- | --------- | --------------------------------- | ----------------------------------------------------------- |
| `Tickets`        | Fact      | TicketID, CreatedDateKey, SLA_ID  | Main transactional table; 50k–100k rows                     |
| `Date`           | Dimension | DateKey (int), Date (actual date) | Continuous calendar, 3 years, for both Created/Closed dates |
| `Employees`      | Dimension | EmpID                             | Reference employees who reported or resolved tickets        |
| `Teams`          | Dimension | TeamID                            | Teams responsible for resolution                            |
| `SLA_Thresholds` | Dimension | SLA_ID, Priority, MaxHoursAllowed | Lookup table for SLA benchmarking by ticket priority        |

## ✅ Key Modeling & DAX Opportunities

| Topic                   | Application                                                       |
| ----------------------- | ----------------------------------------------------------------- |
| Star Schema Design      | `Tickets` as fact, all others as dimensions                       |
| Role-playing Dates      | `CreatedDateKey` vs `ClosedDateKey` (use `USERELATIONSHIP`)       |
| Time Intelligence       | YTD tickets, avg time to close, SLA breach % over time            |
| Relationships & Filters | Simulating a missing employee, inactive team, or unmatched SLA_ID |
| Performance Tuning      | Hiding verbose text fields or high-cardinality ticket categories  |
