# 💰 Student Personal Finance & Budget Tracker

An Excel-based personal finance management tool built to help students track income, monitor monthly expenses, reconcile budgeted vs. actual spending, and manage savings goals — all in one structured workbook.

---

## 📌 Project Overview

Managing finances as a graduate student can be challenging — juggling tuition, rent, groceries, and savings all at once. This project builds a structured, formula-driven Excel workbook that makes it easy to:

- Track all income sources and expenses month by month
- Automatically calculate net savings and savings rate each month
- Reconcile planned vs. actual spending to identify overspending
- Monitor progress toward multiple savings goals throughout the academic year

---

## 📂 Workbook Structure

The workbook contains **3 sheets**, each serving a specific financial tracking purpose:

---

### 📋 Sheet 1 — Monthly Budget

Tracks all income and expenses across **7 months** of the academic year (Sep – Mar).

**Income tracked:**
- Part-time Job
- Stipend / Financial Aid
- Family Support
- Freelance / Other

**Expenses tracked (11 categories):**
- Tuition & Fees, Rent, Groceries, Transport / CTA
- Utilities, Phone Bill, Dining Out, Entertainment
- Books & Supplies, Health & Personal, Miscellaneous

**Key calculated rows (auto-updated using Excel formulas):**

| Row | Formula Used | What It Does |
|---|---|---|
| Total Income | `=SUM(B5:B8)` | Adds all income sources per month |
| Total Expenses | `=SUM(B12:B22)` | Adds all expense categories per month |
| Net Savings / Deficit | `=Total Income - Total Expenses` | Shows how much was saved or overspent |
| Savings Rate (%) | `=Net Savings / Total Income` | Shows what % of income was saved |

**Conditional formatting** highlights Net Savings row automatically:
- 🟢 Green = positive savings
- 🔴 Red = deficit (overspent)

---

### 🔍 Sheet 2 — Expense Reconciliation (October 2025)

Compares **budgeted amounts** vs. **actual spending** for October 2025, with variance analysis for each expense category.

**How it works:**
- The **Budgeted** column contains planned monthly spending targets
- The **Actual** column pulls data **directly from Sheet 1** using cross-sheet formulas:
  ```
  ='Monthly Budget'!C14   ← pulls October Groceries value from Sheet 1
  ```
- The **Variance** column calculates the difference: `=Budgeted - Actual`
- The **Variance %** shows the percentage over or under budget: `=(Budgeted - Actual) / Budgeted`
- The **Status** column is auto-generated using an IF formula:
  ```
  =IF(Actual > Budgeted, "Over Budget", IF(Actual < Budgeted, "Under Budget", "On Track"))
  ```

**Conditional formatting** color-codes the Status column:
- 🟢 Green = On Track / Under Budget
- 🔴 Red = Over Budget

A summary row at the bottom counts total categories over budget and flags them automatically.

---

### 🎯 Sheet 3 — Savings Goals

Tracks progress toward **5 personal savings goals** throughout the academic year.

**Goals tracked:**
| Goal | Target |
|---|---|
| Emergency Fund | $1,000 |
| Laptop Upgrade | $800 |
| Spring Break Trip | $600 |
| Professional Certification | $150 |
| Graduation Fund | $500 |

**For each goal, the sheet tracks:**
- Monthly contributions (Sep – Mar)
- Total saved so far: `=SUM(C4:I4)`
- % Complete: `=Saved So Far / Target`
- Status — auto-calculated using nested IF formula:
  ```
  =IF(Saved >= Target, "Completed!",
    IF(Saved/Target >= 0.75, "Almost There",
      IF(Saved/Target >= 0.40, "In Progress", "Just Started")))
  ```

**Conditional formatting** color-codes Status:
- 🟢 Green = Completed / Almost There
- 🟡 Yellow = In Progress
- 🔴 Red = Just Started

A summary section at the bottom shows total saved across all goals, total target, and overall progress percentage.

---

## 🛠 Tools & Skills Used

| Tool / Skill | How It Was Applied |
|---|---|
| **Microsoft Excel** | Primary tool for building the entire workbook |
| **Excel Formulas** | SUM, IF, nested IF, cross-sheet references |
| **Conditional Formatting** | Auto color-coding based on cell values |
| **Cross-Sheet References** | Sheet 2 pulls live data from Sheet 1 |
| **Financial Reconciliation** | Budgeted vs. Actual variance analysis |
| **Data Organization** | Structured layout across multiple sheets |

---

## 💡 Key Excel Concepts Demonstrated

**1. Cross-Sheet Formula Linking**
Sheet 2 pulls actual spending values directly from Sheet 1 — so if you update any number in Sheet 1, Sheet 2 automatically reflects the change. No manual re-entry needed.

**2. Nested IF Logic**
The Savings Goals status uses a 3-level nested IF to categorize progress into 4 meaningful labels — a common pattern in financial and operational reporting.

**3. Variance Analysis**
The reconciliation sheet mirrors the same process used in professional financial reporting — comparing planned vs. actual figures and flagging anomalies.

**4. Conditional Formatting Rules**
Multiple formatting rules applied to automatically highlight overspending, deficits, and goal statuses — making the data visually scannable at a glance.

---

## 📁 File

| File | Description |
|---|---|
| `Student_Finance_Tracker.xlsx` | Main workbook with all 3 sheets |

---

## 👩‍💻 Author

**Janhavi Kotulkar**
MS Business Analytics — DePaul University, Chicago
