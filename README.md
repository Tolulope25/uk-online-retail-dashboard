# UK Online Retailer: Sales & Operations Dashboard

A Power BI dashboard built on over one million UK online retail transactions, showing what drives revenue and where the business loses value to cancellations.

![Dashboard](dashboard.png)

## Business question
What drives this retailer's revenue, and where does it lose value?

## Data
Online Retail II, UCI Machine Learning Repository (CC BY 4.0): transactions from a UK-based online gift-ware retailer, 1 Dec 2009 to 9 Dec 2011. It's a public dataset, so the findings are descriptive and not real company results. The raw data isn't included. Download it from the UCI site.

## What I did
- **Combined two source sheets** in Power Query. Row counts showed an error, and a check on one invoice (536365, which I calculated by hand) showed its total doubled. The two sheets overlapped by nine days (1 to 9 Dec 2010; 22,523 rows, 1,088 invoices, identical in count and value), so I kept one copy.
- **Split sales from cancellations** (invoices starting with "C").
- **Excluded non-sale rows:** postage, manual entries, adjustments, discounts, carriage, samples, gift vouchers, test entries, and zero or negative prices. I checked each code's description before excluding it and kept real products with unusual codes.
- **Removed two outlier orders** (80,995 and 74,215 units, together worth about £246,000) that were placed and reversed the same day, with their cancellations.
- **Built a data model** with a date table and relationships, then wrote DAX measures for revenue, orders, customers, average order value, cancelled value and cancellation rate.

## Key findings
- Revenue is **£19.46M** from **39,514** orders, an average of **£492** per order.
- About **85%** of revenue comes from the UK. Ireland and the Netherlands are the next largest markets.
- Revenue is not concentrated in a few customers: the top customer is about 3% of revenue. About 13% of revenue has no customer ID.
- Cancellation invoices are about **16%** of all invoices, but cancelled value is only about **£474K**, around 2.4% of revenue, so cancellations are frequent but mostly small.
- [Add your own readings from the monthly charts: peak months, and the month with the highest cancelled value. Check them against your charts.]

## Limitations
- Prices are as recorded and may exclude VAT. There's no cost data, so this analyses revenue, not profit.
- Cancellations aren't linked to the original sale, so the cancellation rate is an approximation (cancellation invoices as a share of all invoices).
- December 2011 is a partial month.
- The customer analysis excludes sales with no customer ID.

## Tools and skills
Power BI, Power Query (M), DAX, data modelling, data validation, data storytelling.

## How to open
Download the `.pbix` file and open it in Power BI Desktop.
