#                                                     Calculated Columns and Measures in DAX

> ## _The **difference** is the context of evaluation. A measure is evaluated in the context of the cell evaluated in a report or in a DAX query, whereas a calculated column is computed at the row level within the table it belongs to._



## Calculated Columns

When you create a data model in Power BI you can extend a table by creating new columns. The content of the columns is defined by a **DAX** expression evaluated row by row.

In Power BI, **to create** a column you need to click the New Column button or right click on the other columns so you can select New Column. The new column is part of a formula you write in the formula texbox.

**The difference** between a `native column` and a `calculated column` is that native columns are those read from the data source or evaluated by a query, where calculated columns are those created extending a table in the data model.
	

### _The DAX expression inside the calculated column operates in the context of the current row across that table._ 

`TABLENAME[COLUMNNAME] = <DAX EXPRESSION FOR CALCULATED COLUMN>`


## Measures

Its useful whenever you don't want to compute values for each row but to aggregate values from **many rows in a table**.

A **measure operates** on aggregations of data defined by the current context, which depends on the filter applied in the report – such as slicer, rows, and columns selection in a pivot table, or axes and filters applied to a chart.

**For example:** When you need to compute the aggregate value as the sum of gross margin divided by the sum of sales amount, you need to compute the ratio on the aggregates – you cannot use an aggregation of calculated columns. In other words, you compute the ratio of the sums, not the sum of the ratio. 

### _measure whenever you want to display resulting calculation values that reflect user selections and see them in the values area of a pivot table, or in the plot area of a chart_

`TABLENAME[MEASURENAME] := <DAX EXPRESSION FOR MEASURE>`

