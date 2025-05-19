# 🧑‍💻 Phase 1 – Power BI

**Area**: Power BI  
**Objective**: Introduce core concepts of Power BI Desktop, help the mentee become comfortable navigating the interface, importing data, and building basic reports and visualizations.

## 🌟 Introduction

Power BI is one of the most widely used tools in modern data analytics and business intelligence. It empowers analysts and decision-makers to transform raw data into interactive, insightful visualizations — without needing to write complex code.

This phase is designed to help you build a strong foundation in Power BI by focusing on the essentials:

- Navigating the Power BI Desktop interface
- Connecting to common data sources
- Creating basic visualizations
- Publishing reports to the Power BI Service

You’ll explore how Power BI fits into the broader data ecosystem, understand the differences between its Desktop, Service, and Mobile components, and gain hands-on experience building your first interactive report.

## 🎯 Learning Goals

By the end of this phase, you should be able to:

- ✅ Explain the purpose and components of the Power BI ecosystem (Desktop, Service, Mobile)
- ✅ Confidently navigate the Power BI Desktop interface, including Report, Data, and Model views
- ✅ Connect to common data sources such as Excel, CSV, and Web
- ✅ Perform basic data shaping operations during import (e.g., remove columns, rename fields)
- ✅ Build simple, interactive reports using core visualizations (bar, line, card, table)
- ✅ Apply basic formatting and interactivity (titles, labels, slicers, filters)
- ✅ Publish a report to the Power BI Service and understand what changes in the cloud environment
- ✅ Reflect on your experience and identify areas for further exploration

## 📊 Topics Covered

### 🔹 Power BI Ecosystem Overview

Power BI is not a single tool — it's a suite of components that work together to help users connect to data, build reports, and share insights. Understanding the ecosystem is essential before diving into the hands-on work.

#### 🧱 Components of the Power BI Ecosystem

| Component            | Purpose                                                                                                                        |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Power BI Desktop** | The main development environment where you connect to data, transform it, build models, and design reports. Installed locally. |
| **Power BI Service** | A cloud-based platform for publishing, sharing, and collaborating on reports and dashboards. Accessible via browser.           |
| **Power BI Mobile**  | A mobile app for viewing and interacting with published reports on the go. Available on iOS and Android.                       |

Each component plays a different role in the data journey:

- **Desktop** is where you build.
- **Service** is where you share.
- **Mobile** is where you consume.

---

#### 🔄 How They Work Together

1. You **build** your report in Power BI Desktop.
2. You **publish** it to the Power BI Service.
3. Stakeholders can **view and interact** with it in the browser or on mobile.

This separation allows for a clean workflow: development happens locally, while consumption and collaboration happen in the cloud.

---

> `Question for mentee:` Which component would you use to build a new report from scratch?
> `Question for mentee:` What are some advantages of separating development (Desktop) from sharing (Service)?

---

### 🖥️ Power BI Desktop UI & Navigation

Power BI Desktop is the primary development environment where you’ll spend most of your time building reports. Understanding its layout and views is essential for working efficiently.

#### 🧭 Main Views

Power BI Desktop has three core views, accessible via the icons on the left sidebar:

| View            | Purpose                                                                                                                                     |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Report View** | Where you design and arrange visuals on report pages. This is the default view.                                                             |
| **Data View**   | Allows you to inspect the data after it has been loaded and transformed. Useful for validation.                                             |
| **Model View**  | Displays the relationships between tables in your data model. Even in basic reports, understanding this view helps with field organization. |

---

#### 🧰 Key Interface Elements

| Element                 | Description                                                                                          |
| ----------------------- | ---------------------------------------------------------------------------------------------------- |
| **Ribbon**              | Contains commands for inserting visuals, managing data, formatting, and more.                        |
| **Fields Pane**         | Lists all tables, columns, and measures available in your model. Drag fields from here into visuals. |
| **Visualizations Pane** | Lets you choose chart types and customize their appearance and behavior.                             |
| **Canvas**              | The main area where you build and arrange your report visuals.                                       |

---

#### 🧑‍💻 Navigation Tips

- Hover over icons in the left sidebar to see tooltips for each view.
- Use the **View** tab in the ribbon to toggle gridlines, snap-to-grid, and other layout helpers.
- Right-click on fields in the Fields Pane to rename, hide, or create new calculated columns (though we won’t cover calculated columns in this phase).

---

> `Question for mentee:` What is the difference between Report View and Data View?
> `Question for mentee:` Where would you go to change a chart type from bar to line?
> `Question for mentee:` Try switching between all three views. What changes do you notice in the interface?

---

### 🔄 Getting Data into Power BI

One of Power BI’s strengths is its ability to connect to a wide variety of data sources — from simple Excel files to complex databases and APIs. In this phase, we’ll focus on the most common and beginner-friendly sources: Excel, CSV, and Web.

#### 📁 Supported Data Sources (Intro Level)

| Source Type | Example Use Case                            |
| ----------- | ------------------------------------------- |
| **Excel**   | Sales reports, budget tracking, survey data |
| **CSV**     | Exported data from systems or tools         |
| **Web**     | Public datasets, tables from websites       |

To connect to data:

1. Open Power BI Desktop.
2. Go to the **Home** tab.
3. Click **Get Data** → choose your source (e.g., Excel).
4. Browse to your file or enter a URL (for Web).
5. Preview the data and choose whether to **Load** or **Transform**.

---

#### 🧼 Light Data Shaping (Without Deep Power Query)

Even though we won’t dive deep into Power Query in this phase, it’s important to understand that Power BI allows you to do some basic shaping before loading data:

- Remove unnecessary columns
- Rename fields
- Filter rows
- Change data types (e.g., text to number)

These actions are done in the **Power Query Editor**, which opens when you click **Transform Data**.

---

> `Question for mentee:` What’s the difference between clicking “Load” and “Transform Data” when importing?
> `Question for mentee:` Why might it be useful to rename columns before loading your data?

---

### 🧭 Exploring the Interface in Detail

Before building reports or importing data, it's essential to understand the layout of Power BI Desktop. This section breaks down each part of the interface so you can navigate with confidence and know where to find the tools you need.

---

#### 🪟 Main Views (Left Sidebar)

Power BI Desktop has three primary views, accessible via the icons on the left-hand sidebar:

| View            | Icon | Description                                                                                                                                    |
| --------------- | ---- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Report View** | 📄   | The default view where you build and arrange visuals on report pages. This is where most of your report design happens.                        |
| **Data View**   | 🔢   | Lets you inspect the data after it has been loaded. You can see tables, rows, and columns — useful for validation and exploration.             |
| **Model View**  | 🔗   | Shows the relationships between tables in your data model. Even in simple reports, this view helps you understand how your data is structured. |

---

#### 📦 Fields Pane (Right Sidebar)

The **Fields Pane** shows all the tables and fields available in your data model. It’s organized by table, and each table contains columns (fields) and any calculated measures you’ve created.

- You can **drag fields** from here into visuals.
- Right-click a field to **rename**, **hide**, or **create new columns** (though we won’t cover calculated columns in this phase).
- Hovering over a field shows its data type (e.g., text, number, date).

---

#### 📊 Visualizations Pane

This pane allows you to:

- Select a **visual type** (e.g., bar chart, table, card)
- Drag fields into **visual-specific buckets** like Axis, Values, Legend, Tooltips
- Access the **Format tab** (paint roller icon) to customize appearance

Each visual has its own configuration options. For example:

- A bar chart will have Axis and Values buckets
- A card visual will only have a single field input

---

#### 🎛️ Slicer Pane (via Visualizations)

A **slicer** is a special type of visual that acts as a filter. It allows users to interactively filter other visuals on the page.

To add a slicer:

1. Select the **Slicer** visual from the Visualizations Pane.
2. Drag a field (e.g., `Region`) into the slicer.
3. Resize and position it on the canvas.

Slicers can be:

- Dropdowns
- Lists
- Date sliders

---

#### 🎨 Formatting Visuals

To format a visual:

1. Select the visual on the canvas.
2. Click the **Format tab** (paint roller icon) in the Visualizations Pane.
3. Explore formatting options such as:
   - Title text and alignment
   - Data labels (on/off, size, color)
   - Background color and borders
   - Legend position and font

---

> `Question for mentee:` What kind of tasks would you perform in the Data View that you wouldn’t do in Report View?
> `Question for mentee:` What’s the difference between a column and a measure in the Fields Pane?
> `Question for mentee:` Try selecting a visual and dragging different fields into the Axis and Values areas. What changes?
> `Question for mentee:` What’s the difference between a slicer and a filter applied directly to a visual?
> `Question for mentee:` Try changing the title of a visual and adjusting its font size. What other formatting options can you find?

---

### 📈 Creating Visualizations

Once your data is loaded into Power BI, the next step is to bring it to life through visuals. Power BI offers a wide range of built-in visualizations that help you explore patterns, compare values, and communicate insights effectively.

#### 🧰 Common Visual Types

| Visual Type          | Best For                                              |
| -------------------- | ----------------------------------------------------- |
| **Bar/Column Chart** | Comparing values across categories                    |
| **Line Chart**       | Showing trends over time                              |
| **Pie/Donut Chart**  | Showing proportions or parts of a whole               |
| **Card**             | Displaying a single summary value (e.g., Total Sales) |
| **Table/Matrix**     | Showing detailed data in rows and columns             |
| **Slicer**           | Adding interactivity by filtering visuals             |

---

#### 🛠️ Building a Visual

To create a visual:

1. Go to **Report View** (default view).
2. Select a visual type from the **Visualizations Pane**.
3. Drag fields from the **Fields Pane** into the appropriate buckets (e.g., Axis, Values, Legend).
4. Resize and position the visual on the canvas.

> Example: To create a bar chart showing total sales by region:
>
> - Select the **Clustered Bar Chart** visual.
> - Drag `Region` to the **Axis**.
> - Drag `Sales` to the **Values**.

---

#### 🎨 Formatting Visuals

Use the **Format** tab (paint roller icon) in the Visualizations Pane to customize:

- Titles and labels
- Colors and themes
- Data labels and tooltips
- Borders and backgrounds

---

> `Question for mentee:` When would you use a card visual instead of a bar chart?
> `Question for mentee:` What happens if you drag a text field into the Values area?
> `Question for mentee:` Try changing the title of your visual. What formatting options are available?

---

### ☁️ Publishing to Power BI Service

Once your report is ready in Power BI Desktop, the next step is to publish it to the Power BI Service — Microsoft’s cloud platform for sharing, collaborating, and managing reports.

#### 🚀 Why Publish?

Publishing allows you to:

- Access your report from any browser
- Share it with others in your organization
- Set up scheduled data refreshes
- Create dashboards by pinning visuals
- Collaborate in workspaces

---

#### 📤 How to Publish

To publish your report:

1. Save your `.pbix` file.
2. Click **File > Publish > Publish to Power BI**.
3. Sign in with your Power BI account (if prompted).
4. Choose a destination workspace (e.g., “My Workspace”).
5. Wait for the confirmation message and click the link to open the report in your browser.

> Note: You’ll need a Power BI account to publish. A free account allows publishing to “My Workspace,” while sharing with others requires a **Pro** or **Premium** license.

---

#### 🧭 What Changes in the Service?

Once published, your report becomes a **read-only** version in the cloud. You can:

- View and interact with visuals
- Share the report (if licensed)
- Create dashboards by pinning visuals
- Set up **scheduled refreshes** (if your data source supports it)

However, to make structural changes (e.g., add visuals, change data), you must return to Power BI Desktop, make edits, and **re-publish**.

---

> `Question for mentee:` Why might it be useful to publish a report instead of just sending someone the .pbix file?
> `Question for mentee:` What happens to your report once it’s published? Can you still edit it in Power BI Desktop?
> `Question for mentee:` Explore your published report in the Service. What features are available that weren’t in Desktop?

---

### 📘 Mini Glossary

A quick reference to help you understand key terms used throughout this phase:

| Term                 | Definition                                                                                                          |
| -------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **Power BI Desktop** | The Windows application used to build reports. This is where you connect to data, transform it, and design visuals. |
| **Power BI Service** | The cloud platform where reports are published, shared, and accessed via browser.                                   |
| **Visual**           | A chart, graph, card, or table that displays data in a report.                                                      |
| **Field**            | A column from a table in your dataset (e.g., `Region`, `Sales`). Fields are used to build visuals.                  |
| **Measure**          | A calculated value (e.g., `Total Sales`) often created using DAX. Not covered in this phase.                        |
| **Canvas**           | The main area in Report View where visuals are placed and arranged.                                                 |
| **Slicer**           | A visual that acts as a filter, allowing users to interactively control what data is shown in other visuals.        |
| **Filter**           | A setting that limits what data is shown in a visual or report. Can be applied at visual, page, or report level.    |
| **Data View**        | A view in Power BI Desktop where you can inspect the raw data after it’s loaded.                                    |
| **Model View**       | A view that shows how tables are related to each other. Useful for understanding data structure.                    |
| **.pbix File**       | The file format used by Power BI Desktop to save reports. Think of it like a PowerPoint file for data.              |

> Tip: If you’re ever unsure about a term, hover over it in Power BI or search Microsoft Learn for a quick explanation.

---

### ⚠️ Common Mistakes & Troubleshooting Tips

Even experienced users make mistakes — and that’s okay. Here are some common pitfalls to watch out for, along with tips to troubleshoot them:

---

#### 🧩 Dragging the Wrong Field Type

**Mistake:** Dragging a text field (e.g., `Customer Name`) into the **Values** area of a visual.  
**What Happens:** Power BI defaults to counting the number of entries instead of summing or averaging.  
**Fix:** Use numeric fields for aggregations, or change the aggregation type manually in the visual.

> `Tip:` Right-click the field in the Values area and choose “Don’t summarize” or “Count”/“Sum” as needed.

---

#### 🔄 Forgetting to Refresh After Data Changes

**Mistake:** Updating the source Excel/CSV file but not seeing changes in Power BI.  
**Fix:** Click **Home > Refresh** to reload the data from the source.

---

#### 🧭 Getting Lost in the Interface

**Mistake:** Not knowing which view (Report, Data, Model) you're in.  
**Fix:** Hover over the icons on the left sidebar — they’ll show tooltips. Use **Ctrl + 1/2/3** to switch views quickly.

---

#### 🎨 Overloading the Report Page

**Mistake:** Adding too many visuals to a single page, making it cluttered and hard to read.  
**Fix:** Focus on 3–5 key visuals per page. Use slicers and filters to add interactivity instead of duplicating visuals.

---

#### 🔐 Publishing Without Signing In

**Mistake:** Trying to publish a report without being signed into a Power BI account.  
**Fix:** Go to **File > Sign In** before publishing. Make sure you’re using a valid Microsoft account.

---

#### 🧼 Skipping Field Renaming

**Mistake:** Leaving field names like `Column1`, `Sheet1`, or `Table1` unchanged.  
**Fix:** Rename fields in Power BI to make your visuals easier to understand (e.g., `Sales Amount`, `Region`).

---

> `Pro Tip:` If something looks off, check the **Fields Pane** and **Visualizations Pane** — most issues can be traced back to how fields are assigned or aggregated.

---

### 🧾 Quick Reference Table: Visual Types

Use this table as a cheat sheet when deciding which visual to use in your report.

| Visual Type         | Best For                                     | Key Fields Needed        |
| ------------------- | -------------------------------------------- | ------------------------ |
| **Bar Chart**       | Comparing values across categories           | Category (Axis), Value   |
| **Column Chart**    | Same as bar chart, but vertical              | Category (Axis), Value   |
| **Line Chart**      | Showing trends over time                     | Date/Time (Axis), Value  |
| **Pie/Donut Chart** | Showing proportions or parts of a whole      | Category, Value          |
| **Card**            | Displaying a single summary value            | Value                    |
| **Table**           | Showing detailed data in rows and columns    | Multiple fields          |
| **Matrix**          | Pivot-style summaries with row/column groups | Rows, Columns, Values    |
| **Slicer**          | Adding interactivity to filter other visuals | One field (e.g., Region) |

> Tip: If you're unsure which visual to use, ask yourself:  
> “Am I comparing, showing change, or summarizing?”

> `Question for mentee:` Which visual would you use to show monthly sales trends over the past year?

---

### 🧪 "Try This" Micro Challenges

These optional challenges are designed to help you apply what you’ve learned in small, focused ways. You don’t need any extra files — just use sample data like Excel or CSV files you already have access to.

---

#### 🔹 Challenge 1: Create a Card Visual

- Import a small dataset (e.g., sales or expenses).
- Add a **Card** visual to the canvas.
- Show the total of a numeric field (e.g., Total Sales).

> `Question for mentee:` What happens if you drag a text field into the Card visual?

---

#### 🔹 Challenge 2: Build a Bar Chart

- Use the same dataset.
- Create a **Bar Chart** showing values by category (e.g., Sales by Region).
- Format the title and change the bar color.

> `Question for mentee:` How does changing the aggregation (Sum vs Count) affect the chart?

---

#### 🔹 Challenge 3: Add a Slicer

- Add a **Slicer** to your report.
- Use a field like `Region` or `Product Category`.
- Interact with the slicer and observe how it filters other visuals.

> `Question for mentee:` What happens if you select multiple values in the slicer?

---

#### 🔹 Challenge 4: Publish Your Report

- Save your `.pbix` file.
- Publish it to the Power BI Service.
- Open it in your browser and explore the online interface.

> `Question for mentee:` What features are available in the Service that aren’t in Desktop?

---

> Tip: These challenges are meant to be quick wins. Don’t worry about perfection — focus on exploration and learning.

---

### ✅ To-Do Checklist

After completing this phase, you should be able to perform the following tasks on your own. Use this checklist to confirm your understanding and readiness to move forward:

- [ ] Install and open Power BI Desktop
- [ ] Navigate between Report, Data, and Model views
- [ ] Identify and describe the purpose of the Fields and Visualizations panes
- [ ] Connect to a sample Excel or CSV file using **Get Data**
- [ ] Load or transform data before importing it into the model
- [ ] Rename fields and remove unnecessary columns
- [ ] Create at least three different visuals (e.g., bar chart, card, table)
- [ ] Add a slicer to filter visuals interactively
- [ ] Format a visual (e.g., title, colors, labels)
- [ ] Save your report as a `.pbix` file
- [ ] Publish your report to the Power BI Service
- [ ] Open the report in the browser and explore the online interface

> Tip: If you’re unsure about any item, revisit the relevant section in this guide or ask your mentor for clarification.

---

### 📚 Additional Resources

Here are some trusted, high-quality resources to help you deepen your understanding of Power BI:

---

#### 🧠 Microsoft Learn

- **Power BI Learning Path**  
  A structured, beginner-friendly curriculum from Microsoft.  
  👉 https://learn.microsoft.com/en-us/training/powerplatform/power-bi/

- **Guided Learning for Power BI**  
  Covers everything from getting started to advanced topics.  
  👉 https://learn.microsoft.com/en-us/power-bi/guided-learning/

---

#### 🎥 YouTube Channels

- **Guy in a Cube**  
  Weekly videos on Power BI tips, tricks, and troubleshooting.  
  👉 https://www.youtube.com/user/pragmaticworks

- **Microsoft Power BI Official Channel**  
  Product updates, tutorials, and demos.  
  👉 https://www.youtube.com/c/mspowerbi

---

#### 📘 Community & Blogs

- **Power BI Community Forum**  
  Ask questions, share solutions, and learn from others.  
  👉 https://community.powerbi.com/

- **RADACAD Blog**  
  Deep dives into Power BI features and best practices.  
  👉 https://radacad.com/blog

---

> Tip: Bookmark these resources and revisit them as you progress through future phases of the mentorship.

---

### 📝 Reflection Notes

Take a few minutes to reflect on your experience completing this phase. These questions are meant to help you consolidate your learning and identify areas for growth.

---

#### 🔍 What did you find easiest?

> Think about which parts of Power BI felt intuitive or enjoyable.

---

#### 🧠 What did you find most challenging?

> Were there any concepts, tools, or steps that felt confusing or frustrating?

---

#### ❓ What questions do you still have?

> List anything you’re unsure about or would like to explore further in future phases.

---

#### 💡 What would you like to try next?

> Is there a specific type of report, visual, or dataset you’re curious to work with?

---

#### 🗣️ Optional: Share with your mentor

> If you're working with a mentor, consider sharing your answers to spark a deeper conversation and get tailored guidance.

---
