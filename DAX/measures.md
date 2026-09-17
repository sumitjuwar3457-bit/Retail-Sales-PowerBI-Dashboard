# DAX Measures

This file contains the key DAX measures created for the Retail Sales Power BI Dashboard.

## 1. Total Sales

Calculates the total sales generated from all transactions.

```DAX
Total Sales =
SUM('Retail_sales'[Sales])
```

## 2. Total Profit

Calculates the total profit generated from all transactions.

```DAX
Total Profit =
SUM('Retail_sales'[Profit])
```

## 3. Total Quantity

Calculates the total quantity of products sold.

```DAX
Total Quantity =
SUM('Retail_sales'[Quantity])
```

## 4. Total Orders

Calculates the number of unique orders.

```DAX
Total Orders =
DISTINCTCOUNT('Retail_sales'[Order ID])
```

## 5. Total Customers

Calculates the number of unique customers.

```DAX
Total Customers =
DISTINCTCOUNT('Retail_sales'[Customer ID])
```

## 6. Average Order Value

Calculates the average sales value generated per order.

```DAX
Average Order Value =
DIVIDE([Total Sales], [Total Orders])
```

## 7. Profit Margin %

Calculates profit as a percentage of total sales.

```DAX
Profit Margin % =
DIVIDE([Total Profit], [Total Sales])
```

## 8. Profit Per Order

Calculates the average profit generated per order.

```DAX
Profit Per Order =
DIVIDE([Total Profit], [Total Orders])
```

## 9. Average Discount

Calculates the average discount applied across transactions.

```DAX
Average Discount =
AVERAGE('Retail_sales'[Discount])
```

## 10. Sales Previous Year

Calculates sales for the corresponding period in the previous year using Power BI time intelligence.

```DAX
Sales Previous Year =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(DateTable[Date])
)
```

## 11. Sales Growth %

Calculates the percentage growth in sales compared with the previous year.

```DAX
Sales Growth % =
DIVIDE(
    [Total Sales] - [Sales Previous Year],
    [Sales Previous Year]
)
```

## DAX Concepts Used

The dashboard uses the following DAX concepts:

* Aggregation functions
* `SUM`
* `AVERAGE`
* `DISTINCTCOUNT`
* `DIVIDE`
* `CALCULATE`
* `SAMEPERIODLASTYEAR`
* Time intelligence
* KPI calculations
* Profitability metrics
* Year-over-Year sales growth

## Key DAX Metrics

| Measure             | Purpose                           |
| ------------------- | --------------------------------- |
| Total Sales         | Measures overall sales            |
| Total Profit        | Measures overall profit           |
| Total Quantity      | Measures products sold            |
| Total Orders        | Measures unique orders            |
| Total Customers     | Measures unique customers         |
| Average Order Value | Measures average sales per order  |
| Profit Margin %     | Measures profitability            |
| Profit Per Order    | Measures average profit per order |
| Average Discount    | Measures average discount         |
| Sales Previous Year | Enables year-over-year comparison |
| Sales Growth %      | Measures sales growth             |

