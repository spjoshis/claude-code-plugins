---
name: excel-analysis
description: Master Excel for data analysis with pivot tables, formulas, Power Query, and advanced Excel techniques.
---

# Excel Analysis

Master Excel for data analysis using pivot tables, formulas, Power Query, and advanced features for business analytics.

## When to Use This Skill

- Ad-hoc analysis
- Quick reporting
- Data cleaning
- Financial modeling
- Business calculations
- Data transformation
- Stakeholder reports
- Self-service analytics

## Core Concepts

### 1. Pivot Tables

```markdown
## Sales Analysis Pivot Table

**Source Data**: Sales transactions (Date, Region, Product, Sales Rep, Amount)

**Pivot Table Setup**:
- Rows: Region, Sales Rep
- Columns: Month (Date grouped by month)
- Values: Sum of Amount
- Filters: Product, Date Range

**Calculated Fields**:
- Average Sale = Sum of Amount / Count of Transactions
- Target vs Actual = Sum of Amount - Target
- % of Total = Sum of Amount / Grand Total

**Formatting**:
- Currency format for amounts
- Percentage for % of Total
- Conditional formatting: Above/below average
```

### 2. Useful Formulas

```excel
# VLOOKUP - Lookup customer name from ID
=VLOOKUP(A2, Customers!A:B, 2, FALSE)

# SUMIFS - Sum sales for specific region and product
=SUMIFS(Sales, Region, "West", Product, "Widget")

# INDEX/MATCH - More flexible than VLOOKUP
=INDEX(Customers!B:B, MATCH(A2, Customers!A:A, 0))

# Array Formula - Count unique values
=SUM(1/COUNTIF(A2:A100, A2:A100))

# TEXTJOIN - Combine values with delimiter
=TEXTJOIN(", ", TRUE, A2:A10)

# IFS - Multiple conditions
=IFS(A2>90, "A", A2>80, "B", A2>70, "C", TRUE, "F")

# Date calculations
=EDATE(A2, 3)  # Add 3 months
=NETWORKDAYS(A2, B2)  # Business days between dates
```

### 3. Power Query

```markdown
## ETL with Power Query

**Transform Sales Data**:
1. Load data from CSV
2. Remove duplicates
3. Filter out cancelled orders
4. Split full name into first/last
5. Change date format
6. Group by customer, sum amounts
7. Add calculated column: Tier (based on total)
8. Load to Excel table

**M Code Example**:
```m
let
    Source = Csv.Document(File.Contents("sales.csv")),
    RemoveDuplicates = Table.Distinct(Source),
    FilterCancelled = Table.SelectRows(RemoveDuplicates, each [Status] <> "Cancelled"),
    SplitName = Table.SplitColumn(FilterCancelled, "Name", Splitter.SplitTextByDelimiter(" "), {"FirstName", "LastName"}),
    GroupedRows = Table.Group(SplitName, {"CustomerID"}, {{"TotalSales", each List.Sum([Amount]), type number}}),
    AddTier = Table.AddColumn(GroupedRows, "Tier", each if [TotalSales] > 10000 then "Gold" else if [TotalSales] > 5000 then "Silver" else "Bronze")
in
    AddTier
```
```

## Best Practices

1. **Use tables** - Structured references, auto-expansion
2. **Name ranges** - Formulas more readable
3. **Avoid merged cells** - Breaks sorting, filtering
4. **Document assumptions** - Comments, separate tab
5. **Validate data** - Data validation rules
6. **Use shortcuts** - Ctrl+T (table), Alt+D+P (pivot)
7. **Power Query for ETL** - Repeatable transformations
8. **Version control** - Save versions, track changes

## Resources

- **Excel Jet**: Formula reference and tips
- **Mr. Excel**: Advanced Excel techniques
