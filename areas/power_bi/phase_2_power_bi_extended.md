# 🧱 Phase 2 – Power BI (Weeks 5–10)

**Area**: Power BI – Tool Mastery & Modeling  
**Objective**: Deepen proficiency in Power BI through hands-on modeling, DAX formulas, data relationships, and more complex visuals. Focus on building scalable, performant, and insightful solutions.

---

## 🌟 Introduction

This phase is where your Power BI skills become more intentional, technical, and impactful.

You already know how to build a report and publish it. Now, you’ll learn how to design models that scale, write DAX that adapts to user filters, and build reports that tell stories — not just show numbers.

We’ll shift from using Power BI to **thinking like a Power BI developer**:

- How should the data be modeled?
- What makes a DAX measure reusable?
- How do filters actually flow through the model?
- How can we build reports that are both performant and user-friendly?

> This is a **practice-first phase** — the best way to learn is to do. Expect to build, test, tweak, and explain your work throughout.

---

## 🎯 Learning Goals

By the end of this phase, you should be able to:

- ✅ Design a star schema using fact and dimension tables
- ✅ Build and explain relationships between tables
- ✅ Write and debug DAX measures with confidence
- ✅ Understand and apply row context and filter context
- ✅ Add slicers, bookmarks, and drillthrough for user interactivity
- ✅ Optimize reports and data models for performance
- ✅ Present and explain your modeling and DAX decisions

---

## 🧠 What’s Different in This Phase?

| Phase 1                | Phase 2                                       |
| ---------------------- | --------------------------------------------- |
| Learn the interface    | Master the modeling layer                     |
| Build simple reports   | Design scalable star schemas                  |
| Add basic visuals      | Craft visuals with interaction and UX in mind |
| Understand what DAX is | Write and debug real DAX measures             |
| Publish to the Service | Analyze and optimize your reports like a pro  |

---

## Topics covered

### 🧱 Section 1: Star Schema & Data Modeling

**Objective**: Build a strong foundation in dimensional modeling by creating a star schema that supports scalable, performant, and intuitive DAX logic.

---

#### 🌟 Key Concepts

A **star schema** is a modeling technique where a central **fact table** is surrounded by one or more **dimension tables**. It is the preferred approach in Power BI because it enables faster queries, clearer relationships, and simpler DAX formulas.

> Think of it like this:  
> The fact table holds **what happened** (e.g., Sales),  
> while dimensions explain **who, what, when, and where** (e.g., Customer, Product, Date).

---

#### 🧱 Components of a Star Schema

| Component           | Description                                                                                     |
| ------------------- | ----------------------------------------------------------------------------------------------- |
| **Fact Table**      | Contains transactional or measurable data (e.g., Sales Amount, Quantity)                        |
| **Dimension Table** | Contains descriptive information used for slicing and grouping (e.g., Region, Product Category) |
| **Primary Key**     | A unique identifier in each dimension table (e.g., `CustomerID`)                                |
| **Foreign Key**     | A field in the fact table that links to a dimension’s primary key                               |
| **Relationships**   | Usually one-to-many from dimension to fact table (single direction filtering)                   |

> 🔎 **Tip**: Always start your model by designing the dimensions first — facts depend on them.

---

#### 🔄 Modeling Best Practices

- ✅ **Use single-direction relationships** wherever possible
- ✅ **Avoid many-to-many relationships** unless business logic requires them
- ✅ Create a **Date table** with continuous dates and mark it as a **Date Table** in Power BI
- ✅ **Do not join** fact-to-fact tables — model joins should flow from dimensions to facts
- ✅ **Avoid bi-directional filters** unless you understand their performance and logic impact
- ✅ Use **integer surrogate keys** for joins when working with large datasets

---

#### 💡 Why Star Schema?

| Benefit                   | Explanation                                                             |
| ------------------------- | ----------------------------------------------------------------------- |
| **Better Performance**    | Power BI’s VertiPaq engine compresses columns better in star schemas    |
| **Simpler DAX**           | Measures become easier to write and interpret                           |
| **Clearer Relationships** | Visual diagram stays clean and readable                                 |
| **Scalable Models**       | Easier to add new facts or dimensions without disrupting existing logic |

> 💭 **Analogy**: Think of dimensions like filter panels — they help you "slice" into the facts easily.

---

#### 🧪 Hands-On Practice

Try these in Power BI using any sample dataset — or one of the ones we’ll provide later in the program:

##### 🔹 Challenge 1: Model From Scratch

- Import at least **one fact table** (e.g., Sales) and **three dimension tables** (e.g., Products, Customers, Dates)
- Create relationships: **one-to-many** from dimension to fact
- Review the **model view** — are all joins pointing in one direction?
- Rename tables and columns for readability

> `Mentor Prompt:` What would happen if you accidentally created a many-to-many relationship?  
> `Mentor Prompt:` Why is it risky to use auto-detected relationships?

---

##### 🔹 Challenge 2: Date Table Creation

- Create a custom **Date table** using DAX:
  ```DAX
  DateTable =
  ADDCOLUMNS(
      CALENDAR(DATE(2022,1,1), DATE(2025,12,31)),
      "Year", YEAR([Date]),
      "Month", FORMAT([Date], "MMM"),
      "MonthNumber", MONTH([Date]),
      "Quarter", "Q" & FORMAT([Date], "Q")
  )
  ```
- Mark it as a Date Table in Power BI
- Connect it to your fact table using a Date column

> `Mentor Prompt`: Why is it better to use a dedicated date table instead of relying on auto-generated date hierarchies?

#### ⚠️ Common Mistakes

| Mistake                                  | Why It’s a Problem                                           | How to Fix It                             |
| ---------------------------------------- | ------------------------------------------------------------ | ----------------------------------------- |
| Using a flat table with repeated values  | Increases model size, reduces performance                    | Normalize into dimensions                 |
| Creating circular or bidirectional joins | Causes performance issues and confusing filter logic         | Use single-direction relationships        |
| Forgetting to create a Date table        | Prevents time intelligence functions from working properly   | Always include a proper Date dimension    |
| Using descriptive fields as join keys    | Text-based joins are slower and prone to data quality issues | Use numeric surrogate keys where possible |

#### 📘 Discussion Prompts

> `Question for mentee`: What’s the difference between a fact and a dimension table?
> `Question for mentee`: What happens if you create a relationship that flows both ways?
> `Question for mentee`: Why is it useful to “hide” keys in the Fields Pane?

#### ✅ To-Do Checklist for This Section

- [ ] Build a star schema with at least one fact table and three dimensions
- [ ] Ensure all relationships are single-direction (1:\* from dimension to fact)
- [ ] Rename all tables and columns for clarity
- [ ] Add a custom Date table and mark it as a date table
- [ ] Review the model view and explain how filters flow through your schema

#### 📝 Reflection

- What was the most confusing part of setting up your schema?
- Did you run into any relationship issues? How did you resolve them?
- How confident do you feel explaining your model to a colleague?

#### 📚 Resources

- 📄 [Star Schema Basics – SQLBI](https://www.sqlbi.com/articles/star-schema-vs-snowflake-schema/)
- 📺 [Guy in a Cube – Power BI Modeling Tips](https://www.youtube.com/watch?v=yKTSLffVGbk)
- 🛠️ [DAX Guide – CALENDAR & DATEADD](https://dax.guide/calendar/)

### 🧮 Section 2: DAX Fundamentals

**Objective**: Understand and apply DAX (Data Analysis Expressions) to create dynamic, context-aware calculations for Power BI reports.

---

#### 🌟 Key Concepts

DAX is the formula language used in Power BI to create **measures**, **calculated columns**, and **calculated tables**. It’s powerful because it allows you to perform custom aggregations and logic based on user interaction and filters.

Think of DAX as Excel’s smarter cousin — built for models, not just spreadsheets. It’s **context-aware**, **optimized for relationships**, and **essential** for advanced reporting.

---

#### 🧠 Core DAX Elements

| Element               | Purpose                                            | Recalculated?       | Memory Usage            |
| --------------------- | -------------------------------------------------- | ------------------- | ----------------------- |
| **Calculated Column** | Adds a new column to a table, evaluated row-by-row | Static (on refresh) | Stored in model         |
| **Measure**           | Creates a dynamic value based on filter context    | Yes (live)          | Lightweight (on-demand) |
| **Calculated Table**  | Creates a new table using logic or filters         | Static (on refresh) | Stored in model         |

> 🧠 Rule of thumb: Prefer **measures** over calculated columns unless you need row-level logic for sorting or relationships.

---

#### 🔢 Common DAX Functions

| Category                | Functions                                     | Example Use Cases                                |
| ----------------------- | --------------------------------------------- | ------------------------------------------------ |
| **Aggregation**         | `SUM`, `AVERAGE`, `COUNT`, `DISTINCTCOUNT`    | Total sales, average rating, number of customers |
| **Time Intelligence**   | `TOTALYTD`, `SAMEPERIODLASTYEAR`, `DATEADD`   | YoY growth, rolling averages, period comparisons |
| **Filter Modifiers**    | `CALCULATE`, `FILTER`, `ALL`, `REMOVEFILTERS` | Custom logic, overrules visual filters           |
| **Logical/Conditional** | `IF`, `SWITCH`, `AND`, `OR`                   | Flagging conditions, conditional logic in KPIs   |
| **Text/Math**           | `FORMAT`, `ROUND`, `CONCATENATE`, `LEFT`      | Custom labels, number formatting, data prep      |

> ⚠️ `CALCULATE` is the **core building block** of DAX — it lets you modify the filter context.

---

#### 🔄 Filter Context vs Row Context

Understanding **context** is the secret to mastering DAX.

- **Row Context**: Evaluates each row individually — applies to calculated columns
- **Filter Context**: The active filters applied via visuals, slicers, and report pages — affects measures

DAX measures are **context-aware** — they recalculate based on the user’s selections.

> 💬 “Which rows are visible right now — and how should we aggregate them?”

---

#### 🧪 Hands-On Practice

These exercises are best done with a sample report that has at least:

- A `Sales` table (fact)
- A `Date` table
- At least two dimension tables (e.g., `Customer`, `Product`)

---

##### 🔹 Challenge 1: Create Simple Measures

Create the following measures in the `Sales` table:

```DAX
Total Sales = SUM(Sales[SalesAmount])
Order Count = COUNTROWS(Sales)
Avg Sale per Order = [Total Sales] / [Order Count]
```

> `Mentor Prompt`: What happens to the result when you add a slicer by Product Category?

##### 🔹Challenge 2: Time Intelligence

Using a proper Date table:

```DAX
Sales Last Year =
CALCULATE([Total Sales],
    SAMEPERIODLASTYEAR('Date'[Date])
)

Sales YTD =
TOTALYTD([Total Sales], 'Date'[Date])

```

> `Mentor Prompt`: Why do these measures return blank if the date table isn’t properly related or marked?

##### 🔹 Challenge 3: Modify Filters with CALCULATE

```DAX
Sales for 2024 =
CALCULATE([Total Sales],
    'Date'[Year] = 2024
)

All-Time Sales (Ignore Filters) =
CALCULATE([Total Sales], REMOVEFILTERS('Date'))
```

> `Mentor Prompt`: How does REMOVEFILTERS differ from ALL?

#### ⚠️ Common Mistakes

| Mistake                                            | Why It Happens                                         | Fix It By...                                |
| -------------------------------------------------- | ------------------------------------------------------ | ------------------------------------------- |
| Using calculated columns instead of measures       | Leads to unnecessary memory usage and poor performance | Use measures for aggregations               |
| Forgetting to mark the Date table                  | Time intelligence functions won’t work properly        | Go to Modeling → Mark as Date Table         |
| Expecting filters to apply across unrelated tables | Model logic doesn’t work as expected                   | Check your schema and relationships         |
| Mixing row and filter context blindly              | Unexpected results or calculation errors               | Practice evaluating what filters are active |

#### 📘 Discussion Prompts

> `Question for mentee`: What’s the difference between a measure and a calculated column?
> `Question for mentee`: Why is CALCULATE considered “the most important function” in DAX?
> `Question for mentee`: When does context cause a DAX measure to return unexpected results?

#### ✅ To-Do Checklist for This Section

- [ ] Create at least 5 custom measures in a report
- [ ] Use a time intelligence function (e.g., SAMEPERIODLASTYEAR)
- [ ] Use CALCULATE to apply or override a filter
- [ ] Explain the differencs between row context and filter context
- [ ] Share one DAX formula and explain it to a peer or mentor

#### 📝 Reflection

- Which DAX functions felt intuitive to you?
- What’s one concept or formula that confused you at first?
- How do you check if a DAX formula is working as intended?

#### 📚 Resources

- 📄 [DAX Guide](https://dax.guide/)
- 📺 [Understanding Filter Context (SQLBI)](https://www.sqlbi.com/articles/understanding-filter-context-in-dax/)
- 🛠️ [DAX Formatter](https://www.daxformatter.com/)
- 📺 [Guy in a Cube – CALCULATE Explained](https://www.youtube.com/watch?v=9yD30K6nHBA)

### 🔗 Section 3: Relationships & Filter Context

**Objective**: Understand how relationships control data flow between tables and how filter context impacts DAX calculations.

---

#### 🌟 Key Concepts

In Power BI, relationships define how tables "talk" to each other. When you build a model with multiple tables (e.g., Sales, Products, Customers), the **relationships** between them control how filters flow and how calculations are evaluated.

This section focuses on:

- Building **correct relationships**
- Understanding **filter direction**
- Distinguishing between **row** and **filter context**
- Debugging unexpected calculation results caused by context issues

> 💡 Most DAX issues are not syntax problems — they’re **context problems**.

---

#### 🔧 Relationship Basics

| Concept                   | Description                                                                |
| ------------------------- | -------------------------------------------------------------------------- |
| **One-to-Many**           | A single value in one table (dimension) maps to many in another (fact)     |
| **Single Direction**      | Filters flow from the one-side to the many-side only                       |
| **Bidirectional**         | Filters flow in both directions (use with caution)                         |
| **Inactive Relationship** | Exists but doesn't affect filters until activated with `USERELATIONSHIP()` |

> 🧠 Relationships are visible and configurable in the **Model View** — always check them visually.

---

#### 🧠 Filter Context in Action

Filter context defines **what data is visible** when a DAX formula runs. It's shaped by:

- Visuals (e.g., selected category in a chart)
- Page/report-level filters
- Slicers
- Measures that modify context using `CALCULATE`, `FILTER`, etc.

> 🧠 DAX doesn't just compute numbers — it **reacts to filters**.

---

#### 🧮 Row Context vs Filter Context

| Context Type       | Applies To         | Example Use Case                                                |
| ------------------ | ------------------ | --------------------------------------------------------------- |
| **Row Context**    | Calculated columns | Add a new column `Sales[LineTotal] = Sales[Qty] * Sales[Price]` |
| **Filter Context** | Measures, visuals  | SUM of sales based on selected region                           |

> 🔄 `CALCULATE` is the bridge between row and filter context. It lets you **create or override filters** explicitly.

---

#### 🧪 Hands-On Practice

These activities assume you have a model with:

- A `Sales` fact table
- Dimension tables like `Product`, `Customer`, and `Date`
- Proper one-to-many relationships defined

---

##### 🔹 Challenge 1: Diagnose Filter Flow

1. Open **Model View**
2. Check the direction of relationships between your tables
3. Ask:
   - Do all dimension tables filter into the fact table?
   - Are any relationships bidirectional? If yes, why?
   - Are any inactive?

> `Mentor Prompt:` What risks come with bidirectional filtering in large models?

---

##### 🔹 Challenge 2: Write a Relationship-Sensitive Measure

Create this basic DAX measure:

```DAX
Total Sales = SUM(Sales[SalesAmount])
```

Now test it under different visual filters:

- By product
- By customer
- By month

Does the measure behave as expected? If not, check:

- Are relationships in place?
- Are keys clean (no nulls or duplicates)?
- Are columns used from the correct table?

> `Mentor Prompt`: What happens if you use a column from a disconnected table in the visual?

##### 🔹 Challenge 3: Use USERELATIONSHIP (Optional)

If you have multiple date columns (e.g., OrderDate, ShipDate), you can only have one active relationship at a time. To use the inactive one in a measure:

```DAX
Sales by Ship Date =
CALCULATE([Total Sales],
    USERELATIONSHIP('Date'[Date], Sales[ShipDate])
)
```

> `Mentor Prompt`: Why does Power BI only allow one active relationship between two tables?

#### ⚠️ Common Mistakes

| Mistake                                   | Why It Matters                                   | How to Fix It                                   |
| ----------------------------------------- | ------------------------------------------------ | ----------------------------------------------- |
| Bidirectional filters overused            | Causes performance issues and logic confusion    | Use single-direction filtering unless needed    |
| No relationship between key tables        | Filters won’t apply — visuals and DAX may break  | Create proper relationships in Model View       |
| Using unrelated fields in visuals         | Results appear blank or incorrect                | Use fields from related tables only             |
| Ambiguous relationships in complex models | Leads to circular references or ambiguity errors | Simplify the model or split logic across layers |

#### 📘 Discussion Prompts

> `Question for mentee`: How can you tell if a relationship is working?
> `Question for mentee`: When would you use an inactive relationship and USERELATIONSHIP()?
> `Question for mentee`: What’s the difference between row and filter context — and why does it matter?

#### ✅ To-Do Checklist for This Section

- [ ] Review and validate all relationships in Model View
- [ ] Ensure all filters flow from dimension to fact tables
- [ ] Use CALCULATE to manipulate filter context
- [ ] Test a measure by placing it in different visuals with slicers
- [ ] Explain why a relationship is single-direction or inactive

#### 📝 Reflection

- Have you ever encountered a blank visual and didn’t know why?
- How do you troubleshoot filter context issues in Power BI?
- What’s one thing you learned about relationships that surprised you?

#### 📚 Resources

- 📄 [Understanding Filter Context in DAX – SQLBI](https://www.sqlbi.com/articles/understanding-filter-context-in-dax/)
- 📺 [Guy in a Cube – Relationships in Power BI](https://www.youtube.com/watch?v=yeuIq2tC4L8)
- 📄 [USERELATIONSHIP Explained](https://www.sqlbi.com/articles/using-multiple-dates-in-dax/)

### 🧭 Section 4: User Interactions – Slicers, Bookmarks, Drillthrough

**Objective**: Enhance report usability and storytelling through interactive elements like slicers, bookmarks, and drillthrough navigation.

---

## 🌟 Key Concepts

Power BI isn’t just about data — it’s about how people **explore and interpret** that data. Good reports are not static dashboards — they’re **interactive tools** that help users ask better questions and uncover insights quickly.

This section focuses on the **features that improve UX** (user experience):

- **Slicers**: filter visuals based on user selections
- **Bookmarks**: save and toggle specific report views
- **Drillthrough**: allow users to “zoom in” for more detail

Used well, these features transform reports from passive summaries into **navigable, decision-focused tools**.

---

## 🎮 User Interaction Tools Overview

| Feature          | Purpose                                                 | Example Use Case                               |
| ---------------- | ------------------------------------------------------- | ---------------------------------------------- |
| **Slicer**       | Interactive filter visible on report page               | Filter by Region, Product Category, or Year    |
| **Bookmark**     | Save report state (filters, visibility, etc.) for reuse | Show/hide visuals, switch between views        |
| **Drillthrough** | Navigate to detail page based on selected item          | Click a customer name to view detailed history |

> 🧠 These features don’t just improve UX — they reduce clutter and support **storytelling and focus**.

---

### 🔍 Slicers

A slicer is a **visual** that lets users filter other visuals on the page.

| Type                | Description                   |
| ------------------- | ----------------------------- |
| **List / Dropdown** | Select one or more categories |
| **Date Slider**     | Filter by date range          |
| **Searchable**      | Useful for large lists        |

> 🔄 Slicers apply a **visual-level or page-level filter** — automatically adjusting connected visuals.

---

### 📌 Bookmarks

Bookmarks capture the current state of a report page — including:

- Visible visuals
- Filters and slicer selections
- Drill positions
- Sort order

Bookmarks are useful for:

- Creating custom navigation buttons
- Designing toggle views (e.g., show/hide details)
- Walking through a data story or scenario

---

### 🔍 Drillthrough

Drillthrough enables **navigating from summary to detail**.

You define a separate report page and configure it to accept a drillthrough filter — typically based on a field like `Customer`, `Product`, or `Region`.

> 📋 Example: From a sales overview page, right-click a specific `Customer` and choose **Drillthrough → Customer Details**.

---

## 🧪 Hands-On Practice

---

#### 🔹 Challenge 1: Add a Slicer to Control a Report

1. Add a **Slicer** visual to the report
2. Drag a field like `Region`, `Year`, or `Product Category` into it
3. Test:
   - Can you select multiple items?
   - Do the visuals update as expected?

> `Mentor Prompt:` What happens if a slicer and a page-level filter conflict?

---

#### 🔹 Challenge 2: Create a Bookmark + Toggle Button

1. Select a visual or group of visuals (e.g., a table)
2. Hide it using the **Selection Pane**
3. Create a **Bookmark** while the object is hidden (e.g., "Table Hidden")
4. Show the visual and create another Bookmark (e.g., "Table Visible")
5. Add **Buttons → Blank → Assign Actions** to trigger the bookmarks

> `Mentor Prompt:` How could you use bookmarks to support storytelling in a report review meeting?

---

#### 🔹 Challenge 3: Configure Drillthrough Navigation

1. Create a new page (e.g., `Customer Details`)
2. Add `Customer Name` (or another field) to the **Drillthrough filter well**
3. Add visuals relevant to the selected customer (e.g., Sales, Orders, Activity)
4. From your main page, right-click a customer in a visual → Drillthrough

> `Mentor Prompt:` How does drillthrough help reduce clutter on the main dashboard?

---

## ⚠️ Common Mistakes

| Mistake                                    | Why It Matters                                           | How to Fix It                                            |
| ------------------------------------------ | -------------------------------------------------------- | -------------------------------------------------------- |
| Overusing slicers                          | Clutters layout and may confuse users                    | Prioritize high-value filters                            |
| Bookmarks not updating after changes       | Outdated bookmarks may not reflect desired state         | Use “Update” button in Bookmarks Pane                    |
| Forgetting to include visuals in bookmarks | May cause toggle buttons to behave inconsistently        | Use Selection Pane and double-check visibility           |
| Drillthrough not working                   | Happens when the source field doesn’t match filter setup | Ensure field used in visual = field in drillthrough pane |

---

## 📘 Discussion Prompts

> `Question for mentee:` When should you use a slicer instead of a page or report-level filter?  
> `Question for mentee:` What’s the difference between drillthrough and drill-down in a visual?  
> `Question for mentee:` How could bookmarks improve storytelling or layout in your reports?

---

## ✅ To-Do Checklist for This Section

- [ ] Add at least two slicers to a report (e.g., Year, Region)
- [ ] Create two bookmarks and assign them to toggle buttons
- [ ] Build a drillthrough page and test it with at least one field
- [ ] Use the Selection and Bookmarks Pane together for layout control
- [ ] Explain how user interactions improve your report UX

---

## 📝 Reflection

- Which of these tools (slicer, bookmark, drillthrough) was new to you?
- How could you use bookmarks or drillthrough in a report you’ve already built?
- What makes a report feel “user-friendly” to you?

---

## 📚 Resources

- 📺 [Guy in a Cube – Slicers vs Filters](https://www.youtube.com/watch?v=z2RJFGmRjV4)
- 📺 [Bookmarks in Power BI – Microsoft Docs](https://learn.microsoft.com/en-us/power-bi/create-reports/desktop-bookmarks)
- 📄 [Drillthrough Best Practices – SQLBI](https://www.sqlbi.com/articles/creating-efficient-drillthrough-pages-in-power-bi/)

---

### 🚀 Section 5: Performance & Optimization

**Objective**: Learn how to design fast, efficient Power BI reports by applying best practices in modeling, DAX writing, and visual layout.

---

## 🌟 Key Concepts

Power BI reports can slow down or become unstable for many reasons — large data volumes, inefficient models, expensive visuals, or heavy DAX expressions.

Performance isn’t just a “nice to have.” In a professional setting, it affects:

- End-user experience
- Adoption and trust
- System resources and refresh times

This section teaches how to identify performance problems and prevent them through smart design.

> 🧠 Optimization starts **before** you publish — in your data model, table design, and visual layout.

---

## ⚙️ Performance Principles

| Area              | Best Practices                                                                          |
| ----------------- | --------------------------------------------------------------------------------------- |
| **Data Model**    | Use star schema, avoid many-to-many, hide unnecessary columns                           |
| **Relationships** | Use single-direction filtering, avoid bi-directional unless truly needed                |
| **DAX**           | Use measures (not calculated columns), write efficient logic, avoid iterators           |
| **Visuals**       | Limit visuals per page, avoid high-cardinality axes, reduce visuals with heavy tooltips |
| **Data Volume**   | Remove unused columns/rows early, filter at the source, summarize where possible        |

> 💡 Smaller models = faster reports = happier users

---

## 🔬 Common Bottlenecks

| Issue                     | Cause                                                   |
| ------------------------- | ------------------------------------------------------- |
| **Slow visuals**          | Complex DAX, too many visuals, high cardinality fields  |
| **Large file size**       | Wide tables, unnecessary columns, calculated columns    |
| **Delayed refresh times** | Excessive row count, unoptimized queries in Power Query |
| **Slicer lag**            | Too many slicers or slicers on high-cardinality fields  |
| **Blank visuals**         | Broken relationships or context issues                  |

---

## 🧪 Hands-On Practice

---

#### 🔹 Challenge 1: Visual Load Audit

1. Open a report with at least 6 visuals on a page
2. Use **Performance Analyzer**:
   - View → Performance Analyzer → Start Recording
   - Interact with the report (e.g., click slicers)
   - Check which visuals take the longest to load

> `Mentor Prompt:` Which visuals were slowest? Can any be simplified or moved to another page?

---

#### 🔹 Challenge 2: Reduce Cardinality

1. Find a high-cardinality field (e.g., `Customer Name`, `Order ID`)
2. Replace it in visuals with a lower-cardinality field (e.g., `Customer Segment`, `Region`)
3. Re-run Performance Analyzer

> `Mentor Prompt:` Why is cardinality so important in Power BI performance?

---

#### 🔹 Challenge 3: Optimize the Model

1. Open **Model View**
2. Remove or hide unused columns (especially text fields)
3. Turn off “Auto Date/Time” under Options → Data Load
4. Review column data types (e.g., format dates as integers where possible)

> `Mentor Prompt:` What’s the difference between deleting vs hiding a column? When should you do each?

---

## ⚠️ Common Mistakes

| Mistake                            | Why It Matters                                       | Fix It By...                                 |
| ---------------------------------- | ---------------------------------------------------- | -------------------------------------------- |
| Keeping all columns “just in case” | Bloats model size, increases refresh time            | Only load needed fields into the model       |
| Overusing calculated columns       | Increases memory usage and file size unnecessarily   | Use DAX measures instead                     |
| Using text fields in visuals       | High cardinality reduces compression & slows filters | Aggregate by categories, not raw text        |
| Ignoring model size warnings       | Can lead to publish or refresh failures              | Use View → Model Size to inspect table sizes |

---

## 📘 Discussion Prompts

> `Question for mentee:` What causes one visual to render slower than others?  
> `Question for mentee:` Why is a star schema more performant than a flat table?  
> `Question for mentee:` When should you use a summary table instead of raw data?

---

## ✅ To-Do Checklist for This Section

- [ ] Use Performance Analyzer to profile at least one page
- [ ] Identify and reduce a high-cardinality field used in visuals
- [ ] Remove or hide unnecessary columns from your model
- [ ] Explain the impact of calculated columns vs measures
- [ ] Apply at least one improvement that reduces report load time

---

## 📝 Reflection

- What surprised you about which visuals were slowest?
- How confident are you in identifying performance issues in a report?
- What habits can you adopt now to make future reports faster by design?

---

## 📚 Resources

- 📄 [VertiPaq Analyzer – DAX Studio Tool](https://www.sqlbi.com/tools/vertipaq-analyzer/)
- 📺 [Guy in a Cube – Performance Tips](https://www.youtube.com/watch?v=sPfruGZ2j1Y)
- 📄 [Best Practices for Power BI Modeling](https://docs.microsoft.com/en-us/power-bi/guidance/modeling-best-practices)

---

---

# 🧾 Phase Summary

In this phase, you’ve transitioned from basic Power BI usage to structured, scalable report development. You’ve learned how to model data effectively, write dynamic DAX expressions, manage filter context, build interactivity, and improve report performance.

You are no longer just building charts — you're building models that answer questions clearly, reliably, and fast.

> 💡 The habits you form here — like modeling before visualizing, using measures over columns, thinking in filter context, and testing performance — will serve you in every future Power BI project.

---

## ✅ To-Do Checklist

Use this checklist to confirm your understanding and track your hands-on progress.

| Category                   | Task                                                                |
| -------------------------- | ------------------------------------------------------------------- |
| ⭐ Star Schema             | [ ] Build a model with 1 fact + 3 dimension tables                  |
|                            | [ ] Use single-direction relationships only                         |
| 🧮 DAX                     | [ ] Write at least 5 custom measures                                |
|                            | [ ] Use CALCULATE and a time intelligence function                  |
|                            | [ ] Explain row vs filter context with an example                   |
| 🔗 Relationships & Context | [ ] Verify relationship directions and explain filter flow          |
|                            | [ ] Use USERELATIONSHIP for an inactive relationship (optional)     |
| 🧭 UX Interactions         | [ ] Add slicers for two fields (e.g., Year, Region)                 |
|                            | [ ] Create two bookmarks and assign to toggle buttons               |
|                            | [ ] Build a drillthrough page for a dimension like Customer/Product |
| 🚀 Performance             | [ ] Use Performance Analyzer to profile visual load times           |
|                            | [ ] Hide/remove unused columns or high-cardinality fields           |
|                            | [ ] Reduce unnecessary visuals or slicers                           |
| 🧠 Communication           | [ ] Present your report and explain key modeling and DAX decisions  |
|                            | [ ] Share one performance improvement you applied                   |

> Tip: You don’t need to check every box in a single sitting — use this as a guide throughout Weeks 5–10.

---

## 📚 Additional Resources

Here’s a curated collection of tools and learning resources to deepen your skills during and after this phase.

### 📘 DAX & Modeling

- [DAX Guide (by SQLBI)](https://dax.guide/)
- [Understanding Filter Context in DAX](https://www.sqlbi.com/articles/understanding-filter-context-in-dax/)
- [VertiPaq Analyzer (DAX Studio)](https://www.sqlbi.com/tools/vertipaq-analyzer/)

### 🎥 YouTube – Practical Learning

- [Guy in a Cube – DAX, Performance, Modeling Tips](https://www.youtube.com/@GuyinaCube)
- [Drillthrough and UX Tricks](https://www.youtube.com/watch?v=U5w1pjU7N0o)

### 📄 Official Docs

- [Microsoft – Power BI Performance Best Practices](https://learn.microsoft.com/en-us/power-bi/guidance/power-bi-performance-best-practices)
- [Power BI – Bookmarks & Drillthrough](https://learn.microsoft.com/en-us/power-bi/create-reports/desktop-bookmarks)

---

## 📝 Reflection Prompts

Take a few minutes to reflect at the end of this phase. Write your thoughts down or discuss with your mentor:

### 🔍 What felt most different from Phase 1?

> What did you notice about how you work with models and filters now?

---

### 🧠 What was your biggest DAX “aha moment”?

> Was there a concept (like CALCULATE, filter context, or row vs filter logic) that clicked for you?

---

### ⚙️ What performance habits will you use going forward?

> What small changes will you make in future reports to ensure speed and stability?

---

### 🎯 What kind of report or business case do you want to build next?

> Is there a domain, challenge, or dataset you’re curious to explore with what you’ve learned?

---

## 🗣️ Optional: Share with Your Mentor

> Choose one of the following to bring to your next mentoring session:
>
> - A DAX formula you wrote and how it works
> - A performance issue you found and improved
> - A sketch of your star schema with relationships
> - A before/after UX enhancement using bookmarks or drillthrough

Sharing your process builds confidence — and helps you internalize what you’ve learned.
