# 🧱 Phase 2 – Power BI (Weeks 5–10)

**Area**: Power BI – Tool Mastery & Modeling
**Objective**: Deepen proficiency in Power BI through hands-on modeling, DAX formulas, data relationships, and more complex visuals. Focus on building scalable, performant, and insightful solutions.

---

## 🌟 Learning Goals

- Understand and apply star schema modeling concepts
- Write and debug basic to intermediate DAX expressions
- Build relationships between tables and understand filter context
- Use slicers, bookmarks, and interactions to enhance UX
- Apply performance best practices in report and model design

---

## 🧩 Topics Covered

### 1. **Star Schema & Data Modeling**

A star schema separates fact tables (e.g., sales, transactions) from dimension tables (e.g., customers, dates, products).

> Benefits include improved performance, easier DAX logic, and better scalability.

Key concepts:

- Fact tables: quantitative data (e.g., sales amount)
- Dimension tables: descriptive attributes (e.g., product name, region)
- Relationships: join tables based on keys (one-to-many recommended)
- Avoid bidirectional filters unless absolutely necessary

### 2. **DAX Fundamentals**

Data Analysis Expressions (DAX) is the formula language in Power BI used for calculated columns, measures, and tables.

Core concepts:

- Calculated columns: row-level operations, stored in memory
- Measures: dynamic calculations, recalculated per filter context
- Aggregations: SUM, AVERAGE, COUNT, DISTINCTCOUNT
- Time intelligence: TOTALYTD, SAMEPERIODLASTYEAR, DATEADD
- CALCULATE: central to modifying filter context

> Emphasize practicing small, testable DAX snippets in real reports.

### 3. **Relationships & Filter Context**

Understanding how filters flow between tables is critical:

- Direction: one-to-many vs many-to-one
- Single vs bidirectional filtering
- Filter context: what filters are active during evaluation?
- Row context: important for calculated columns

> Use the model view and diagram tools to visually inspect table connections.

### 4. **User Interactions: Slicers, Bookmarks, Drillthrough**

Enhance usability by enabling interactive features:

- **Slicers**: Allow filtering by dimensions
- **Bookmarks**: Save report states for storytelling or navigation
- **Drillthrough**: Let users click through to details for a single item

> These tools improve storytelling and end-user control.

### 5. **Performance & Optimization**

Avoid slow or overly complex reports:

- Use proper relationships (avoid many-to-many unless necessary)
- Minimize columns and cardinality in tables
- Prefer measures over calculated columns
- Optimize visuals (limit data categories in charts)

---

## 🛠️ Activities & Practice

| Activity                   | Description                                                                 |
| -------------------------- | --------------------------------------------------------------------------- |
| **Model from Scratch**     | Load multiple tables and build a clean star schema                          |
| **DAX Exercise Set**       | Solve progressively harder DAX problems (mentor provided)                   |
| **Visual UX Enhancements** | Add slicers, bookmarks, tooltips, and drillthroughs                         |
| **Performance Review**     | Analyze and optimize a slow report with mentor feedback                     |
| **Mini Project**           | Build a full report using public data with proper modeling and storytelling |

---

## ✅ To-Do Checklist

- [ ] Build a star schema with at least 3 dimension tables
- [ ] Create 5+ DAX measures (some time-based)
- [ ] Add bookmarks, slicers, or drillthrough to a report
- [ ] Explain how filters flow in your model
- [ ] Document key modeling decisions (e.g., column removed, relationships chosen)
- [ ] Present a short walkthrough of your report to the mentor

---

## 📚 Resources

- Microsoft Docs: [DAX Guide](https://dax.guide/)
- Article: [Understanding Filter Context](https://www.sqlbi.com/articles/understanding-filter-context-in-dax/)
- Tool: [DAX Formatter](https://www.daxformatter.com/)
- YouTube: [Guy in a Cube – Star Schema Explained](https://www.youtube.com/user/pragmaticworks)

---

## 📝 Reflection & Notes (Mentee)

- Which DAX functions feel natural, and which feel hard to grasp?
- What challenges did you face when building your model?
- What would you do differently in your next project?

---

## 🗓️ Suggested Timeline

| Week    | Focus                                 |
| ------- | ------------------------------------- |
| Week 5  | Modeling: Star schema & relationships |
| Week 6  | DAX introduction and first measures   |
| Week 7  | Filter context & calculated logic     |
| Week 8  | Visual interactions & UX features     |
| Week 9  | Performance tuning & optimization     |
| Week 10 | Final project build and review        |

---

**Next Step**: Move on to Phase 2 – Data Analysis (Applied Practice & Insight Building)
