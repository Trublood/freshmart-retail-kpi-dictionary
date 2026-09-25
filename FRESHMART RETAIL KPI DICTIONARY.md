FRESHMART RETAIL KPI DICTIONARY
1. Executive Summary
FreshMart's Retail KPI Dictionary provides the agreed business definitions for the core performance measures used across the Retail Analytics Data Warehouse.
The purpose is to ensure that analysts, developers and business stakeholders use the same interpretation of key retail metrics across Executive, Commercial, Finance, Store Operations, Supply Chain, Customer and Promotional reporting.
The dictionary contains 36 core KPIs across eight business areas. Each KPI includes its business purpose, definition, business-level formula, calculation logic, unit of measure, reporting frequency, primary data source, primary business owner and notes where required.
The document is designed to reduce inconsistent reporting, duplicated calculations and disputes over metric meaning. It establishes a common business language between operational teams and the analytics functions that build reports and data products.
This document defines business rules only. SQL logic, dimensional modelling, transformation rules and Power BI implementation are intentionally outside scope and should be handled in downstream technical projects.
2. Project Brief
2.1 Background
FreshMart is a fictional national UK supermarket chain operating supermarket, convenience stores, online grocery services, distribution centers and supporting commercial functions. Different functions use overlapping retail metrics, creating a risk that the same KPI is interpreted or calculated differently across teams.
2.2 Business Problem
•	Different sales figures across reports
•	Inconsistent treatment of VAT, refunds, returns, discounts and promotions
•	Confusion between similar metrics
•	Reduced trust in reporting
•	Poor decisions caused by misunderstood measures
2.3 Objective
To create a concise and practical Retail KPI Dictionary containing approximately 30 - 40 of FreshMart's most important metrics, with clear business ownership and governance.
2.4 Intended Users
•	Business and Data Analysts
•	BI Developers and Data Engineers
•	Finance and Commercial Teams
•	Store and Retail Operations
•	Supply Chain and Procurement
•	Customer / Marketing Teams
•	Senior Management and Data Governance
2.5 Scope
The dictionary covers Sales & Trading, Customer, Store Performance, Inventory & Availability, Promotions, Operations & Labour, Supply Chain, and Finance & Profitability.
2.6 Out of Scope
•	SQL queries and technical transformations
•	Dimensional models and physical database design
•	ETL / data-pipeline implementation
•	Power BI visuals and dashboard layout
•	Predictive modelling or machine learning
2.7 Key Business Assumptions
•	FreshMart operates physical stores and online grocery channels across the UK.
•	FreshMart maintains central POS, inventory, finance, promotion, customer, workforce and supply-chain systems.
•	The business uses UK retail terminology and standard VAT / accounting concepts.
•	KPI definitions are governed centrally even when multiple functions use the same metric.
3. KPI Categories
Category	Purpose	KPIs
Sales & Trading	Overall trading performance, growth, product volume, pricing and space productivity.	6
Customer	Shopping activity, identifiable customer reach, basket size and visit frequency.	5
Store Performance	Store-level trading results, target delivery and productivity.	4
Inventory & Availability	Stock position, availability, out-of-stocks, stock efficiency and waste.	6
Promotions	Scale, sales impact and profitability of promotional activity.	4
Operations & Labour	Store labour cost, productivity and operational stock loss.	4
Supply Chain	Delivery timeliness, order completeness and supplier service.	3
Finance & Profitability	Product cost, gross profit, margin and operating profitability.	4

4. KPI Dictionary
The following 36 KPIs form FreshMart's core business dictionary. Definitions are written at business level and avoid technical implementation details.
4.1 Sales & Trading
Net Sales
Business Purpose: Measure the value of products sold after relevant sales deductions and provide FreshMart's primary trading revenue measure.
Business Definition: Value of completed customer sales after discounts, refunds and returns, excluding VAT.
Formula (business level):  
Gross Sales - Discounts - Refunds - Returns - VAT
Calculation Logic: Include eligible completed store and online sales in the reporting period. Exclude cancelled or voided transactions and deduct qualifying discounts, refunds and returns.
Unit of Measure: GBP (£)
Reporting Frequency: Daily, Weekly, Periodic, Monthly, Annual
Primary Data Source: Point-of-Sale and Online Order Systems
Business Owner: Finance
Notes / Common Considerations: Net Sales is the standard base sales measure for FreshMart reporting. Treatment of refunds, returns and VAT must remain consistent.

Sales Growth %
Business Purpose: Measure whether sales are increasing or decreasing against a selected comparable period.
Business Definition: Percentage change in Net Sales between the current reporting period and the selected comparison period.
Formula (business level): 
((Current Period Net Sales - Previous Period Net Sales) / Previous Period Net Sales) x 100
Calculation Logic: Compare Net Sales for equivalent periods, such as week-on-week or year-on-year.
Unit of Measure: Percentage (%)
Reporting Frequency: Weekly, Periodic, Monthly, Annual
Primary Data Source: Sales and Finance Systems
Business Owner: Commercial

Like-for-Like Sales Growth %
Business Purpose: Measure underlying sales performance from a consistent group of established stores.
Business Definition: Percentage change in Net Sales from stores meeting FreshMart's approved like-for-like eligibility criteria in both periods.
Formula (business level): 
((Current Comparable Store Sales - Prior Comparable Store Sales) / Prior Comparable Store Sales) x 100
Calculation Logic: Include only eligible comparable stores in both periods. New stores and permanent closures may be excluded.
Unit of Measure: Percentage (%)
Reporting Frequency: Weekly, Periodic, Monthly, Annual
Primary Data Source: Point-of-Sale and Store Master Data
Business Owner: Commercial

Units Sold
Business Purpose: Measure physical product volume and separate volume growth from price-driven sales growth.
Business Definition: Total quantity of saleable product units purchased through completed customer transactions.
Formula (business level): 
Sum of Product Units Sold
Calculation Logic: Sum quantities on completed transactions and deduct returned units where applicable.
Unit of Measure: Units
Reporting Frequency: Daily, Weekly, Periodic, Monthly, Annual
Primary Data Source: Point-of-Sale and Online Order Systems
Business Owner: Commercial

Average Selling Price
Business Purpose: Understand the average sales value generated per unit sold.
Business Definition: Average Net Sales value received per unit sold during the reporting period.
Formula (business level): 
Net Sales / Units Sold
Calculation Logic: Divide Net Sales for the selected scope by the corresponding Units Sold.
Unit of Measure: GBP per Unit (£/unit)
Reporting Frequency: Weekly, Periodic, Monthly
Primary Data Source: Point-of-Sale and Product Systems
Business Owner: Commercial
Notes / Common Considerations: Changes can reflect direct price movement, promotions or a shift in product mix.

Sales per Square Foot
Business Purpose: Measure how effectively active retail selling space generates revenue.
Business Definition: Net Sales generated per square foot of active customer-facing selling space.
Formula (business level): 
Net Sales / Selling Area (sq ft)
Calculation Logic: Divide store Net Sales by active selling area. Exclude non-selling areas such as stockrooms, offices and colleague facilities/space.
Unit of Measure: GBP per Square Foot (£/sq ft)
Reporting Frequency: Periodic, Monthly, Annual
Primary Data Source: Point-of-Sale and Store Property / Master Data
Business Owner: Retail Operations

4.2 Customer
Customer Transactions
Business Purpose: Measure completed shopping occasions and trading activity.
Business Definition: Total number of completed customer purchase transactions in the reporting period.
Formula (business level): 
Count of Completed Sales Transactions
Calculation Logic: Count each completed checkout transaction once. Exclude cancelled, voided or fully reversed transactions.
Unit of Measure: Transactions
Reporting Frequency: Daily, Weekly, Periodic, Monthly, Annual
Primary Data Source: Point-of-Sale and Online Order Systems
Business Owner: Retail Operations
Notes / Common Considerations: Transactions are not the same as customers; one customer may complete multiple transactions.

Unique Customers
Business Purpose: Measure the number of identifiable individual customers.
Business Definition: Number of distinct identifiable customers completing at least one purchase in the reporting period.
Formula (business level): 
Count of Distinct Identifiable Customers with Completed Purchases
Calculation Logic: Use FreshMart's approved customer identifier, such as loyalty ID or registered online account, and count each person once per reporting period.
Unit of Measure: Customers
Reporting Frequency: Weekly, Periodic, Monthly, Annual
Primary Data Source: Loyalty, Customer Account, POS and Online Order Systems
Business Owner: Customer / Marketing
Notes / Common Considerations: Anonymous shoppers cannot be reliably counted as unique individuals.

Average Transaction Value
Business Purpose: Measure the average amount spent per completed transaction.
Business Definition: Average Net Sales generated per completed transaction.
Formula (business level): 
Net Sales / Customer Transactions
Calculation Logic: Divide Net Sales by completed transactions for the same reporting scope and period.
Unit of Measure: GBP per Transaction (£/transaction)
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Point-of-Sale and Online Order Systems
Business Owner: Commercial
Notes / Common Considerations: ATV can rise because of more items, higher prices or a different product mix. Interpret with User Per Transaction and ASP.

Units per Transaction
Business Purpose: Measure average basket size in physical product terms.
Business Definition: Average number of product units purchased per completed transaction.
Formula (business level): 
Units Sold / Customer Transactions
Calculation Logic: Divide total Units Sold by completed Customer Transactions for the same period.
Unit of Measure: Units per Transaction
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Point-of-Sale and Online Order Systems
Business Owner: Commercial
Notes / Common Considerations: UPT measures quantity rather than value; product-size and category mix can affect comparisons.

Customer Purchase Frequency
Business Purpose: Understand how often identifiable customers return to shop.
Business Definition: Average number of completed identified transactions per identifiable customer within a defined period.
Formula (business level): 
Identified Customer Transactions / Unique Customers
Calculation Logic: Count completed transactions linked to identifiable customers and divide by Unique Customers for the same period.
Unit of Measure: Transactions per Customer
Reporting Frequency: Monthly, Quarterly, Annual
Primary Data Source: Loyalty, Customer Account, POS and Online Order Systems
Business Owner: Customer / Marketing
Notes / Common Considerations: The reporting period must be explicit. Anonymous transactions are excluded.
4.3 Store Performance
Store Sales
Business Purpose: Measure Net Sales generated by an individual FreshMart store or defined store group.
Business Definition: Total Net Sales attributable to the selected store during the reporting period.
Formula (business level): 
Sum of Net Sales for Selected Store
Calculation Logic: Apply the approved Net Sales definition and attribute eligible transactions to the relevant store.
Unit of Measure: GBP (£)
Reporting Frequency: Daily, Weekly, Periodic, Monthly, Annual
Primary Data Source: Point-of-Sale, Online Order and Store Master Data
Business Owner: Retail Operations
Notes / Common Considerations: Store Sales should not be compared in isolation across materially different store formats, sizes or locations.

Store Target Achievement %
Business Purpose: Show whether a store is meeting its approved sales target.
Business Definition: Actual store Net Sales expressed as a percentage of the approved sales target for the same period.
Formula (business level): 
 (Actual Store Net Sales / Store Sales Target) x 100
Calculation Logic: Compare actual Store Sales with the approved target for the same reporting period.
Unit of Measure: Percentage (%)
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Point-of-Sale and Finance Planning / Target Systems
Business Owner: Retail Operations


Transactions per Store
Business Purpose: Compare transaction activity across regions, formats or groups of stores.
Business Definition: Average number of completed customer transactions per active store during the reporting period.
Formula (business level): 
Total Store Transactions / Number of Active Stores
Calculation Logic: Sum completed transactions across the selected store population and divide by active stores in the same period.
Unit of Measure: Transactions per Store
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Point-of-Sale and Store Master Data
Business Owner: Retail Operations
Notes / Common Considerations: For an individual store, the raw transaction count is generally more useful. Temporary closures and partial periods require consistent treatment.

Sales per Trading Hour
Business Purpose: Measure how effectively available customer trading time generates sales.
Business Definition: Net Sales generated for each hour a store is open and available for customer trading.
Formula (business level): 
Store Net Sales / Store Trading Hours
Calculation Logic: Divide Store Sales by actual customer trading hours for the same reporting period.
Unit of Measure: GBP per Trading Hour (£/hour)
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Point-of-Sale and Store Operating Hours Data
Business Owner: Retail Operations
Notes / Common Considerations: Trading hours are not labour hours.
4.4 Inventory & Availability
Stock on Hand
Business Purpose: Measure the quantity of inventory currently held at a defined stock location.
Business Definition: Recorded quantity of saleable inventory physically held at a defined location at a specific point in time.
Formula (business level): 
Opening Stock + Receipts + Transfers In - Sales - Transfers Out - Recorded Waste and Adjustments
Calculation Logic: Use the latest recognised inventory position after legitimate stock movements and adjustments.
Unit of Measure: Units, Cases or GBP Value
Reporting Frequency: Daily
Primary Data Source: Inventory Management and Stock Control Systems
Business Owner: Supply Chain
Notes / Common Considerations: System stock may differ from physical stock because of theft, scanning errors, unrecorded waste or processing delays.

Stock Availability %
Business Purpose: Measure whether products expected to be available are actually available for customer purchase.
Business Definition: Percentage of ranged products expected to be available that are currently saleable to the customer.
Formula (business level): 
(Available Ranged Products / Total Ranged Products Expected to Be Available) x 100
Calculation Logic: For the selected store or category, apply FreshMart's approved availability rule to ranged products expected to be available.
Unit of Measure: Percentage (%)
Reporting Frequency: Daily, Weekly
Primary Data Source: Inventory, Replenishment and Product Ranging Systems
Business Owner: Retail Operations

Out-of-Stock Rate
Business Purpose: Measure the proportion of expected products that are unavailable to customers.
Business Definition: Percentage of ranged products expected to be available that have no saleable stock available.
Formula (business level): 
(Out-of-Stock Ranged Products / Total Ranged Products Expected to Be Available) x 100
Calculation Logic: Apply the same scope and measurement framework used for Stock Availability %.
Unit of Measure: Percentage (%)
Reporting Frequency: Daily, Weekly
Primary Data Source: Inventory, Replenishment and Product Ranging Systems
Business Owner: Retail Operations
Notes / Common Considerations: Under a consistent rule, this is broadly the inverse of Stock Availability %. Both are retained because teams may prefer an availability or failure view.

Inventory Turnover
Business Purpose: Measure how quickly inventory is sold and replaced.
Business Definition: Number of times average inventory at cost is sold through during a defined period.
Formula (business level): 
Cost of Goods Sold / Average Inventory at Cost
Calculation Logic: Divide COGS by average inventory value at cost for the same period.
Unit of Measure: Times
Reporting Frequency: Monthly, Quarterly, Annual
Primary Data Source: Inventory and Finance Systems
Business Owner: Supply Chain
Notes / Common Considerations: Turnover expectations differ by category. Very high turnover can also signal understocking if availability deteriorates.

Days of Inventory
Business Purpose: Estimate how many days average inventory would support normal trading.
Business Definition: Estimated number of days that average inventory at cost would cover based on average daily COGS.
Formula (business level): 
Average Inventory / Average Daily Cost of Goods Sold
Calculation Logic: Divide average inventory at cost by average daily COGS for the same reporting period.
Unit of Measure: Days
Reporting Frequency: Weekly, Monthly
Primary Data Source: Inventory and Finance Systems
Business Owner: Supply Chain
Notes / Common Considerations: Appropriate days of stock differ significantly between fresh, ambient, seasonal and slower-moving categories.

Waste %
Business Purpose: Measure known inventory loss and identify avoidable waste.
Business Definition: Recorded authorised waste value expressed as a percentage of Net Sales.
Formula (business level): 
(Recorded Waste Value / Net Sales) x 100
Calculation Logic: Sum approved waste such as expiry, spoilage, damage or quality failure and divide by Net Sales for the same scope and period.
Unit of Measure: Percentage (%)
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Inventory, Waste Recording and Point-of-Sale Systems
Business Owner: Retail Operations
Notes / Common Considerations: Waste is known and recorded. Unexplained loss belongs under Shrinkage.
4.5 Promotions
Promotional Sales
Business Purpose: Measure sales generated from products sold under approved promotions.
Business Definition: Net Sales value generated while a qualifying FreshMart promotion is active.
Formula (business level): 
Sum of Net Sales from Promotional Transactions
Calculation Logic: Identify transaction lines linked to approved promotional activity and sum associated Net Sales.
Unit of Measure: GBP (£)
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Point-of-Sale and Promotion Management Systems
Business Owner: Commercial
Notes / Common Considerations: Clearance, markdowns, permanent price changes and colleague discounts are not automatically promotional sales.

Promotional Sales Mix %
Business Purpose: Measure how much of total sales depends on promotional activity.
Business Definition: Promotional Sales expressed as a percentage of total Net Sales.
Formula (business level): 
(Promotional Sales / Net Sales) x 100
Calculation Logic: Divide Promotional Sales by Net Sales for the same scope and period.
Unit of Measure: Percentage (%)
Reporting Frequency: Weekly, Periodic, Monthly
Primary Data Source: Point-of-Sale and Promotion Management Systems
Business Owner: Commercial

Promotional Uplift %
Business Purpose: Estimate additional sales generated by a promotion relative to expected normal sales.
Business Definition: Percentage increase in promotional-period sales relative to an approved baseline representing expected non-promotional sales.
Formula (business level): 
((Promotional Period Sales - Baseline Sales) / Baseline Sales) x 100
Calculation Logic: Compare actual promotional sales with an agreed baseline such as recent non-promotional performance or a comparable historical period.
Unit of Measure: Percentage (%)
Reporting Frequency: Per Promotion, Weekly, Periodic
Primary Data Source: Point-of-Sale, Promotion Management and Historical Sales Data
Business Owner: Commercial

Promotional Gross Margin %
Business Purpose: Measure profitability of promotional sales after product cost.
Business Definition: Gross profit generated from promotional sales expressed as a percentage of Promotional Sales.
Formula (business level): 
((Promotional Sales - Promotional COGS) / Promotional Sales) x 100
Calculation Logic: Deduct the cost of products sold under promotion from Promotional Sales and divide by Promotional Sales.
Unit of Measure: Percentage (%)
Reporting Frequency: Per Promotion, Weekly, Periodic, Monthly
Primary Data Source: Point-of-Sale, Promotion Management and Finance Systems
Business Owner: Finance
4.6 Operations & Labour
Store Labour Cost
Business Purpose: Measure the total recognised cost of employing store colleagues.
Business Definition: Total recognised store colleague cost, including regular pay, overtime and other employment costs covered by FreshMart's approved labour policy.
Formula (business level): 
Regular Pay + Overtime Pay + Applicable Employment Costs
Calculation Logic: Sum recognised labour costs for colleagues assigned to stores or selected retail-operational areas.
Unit of Measure: GBP (£)
Reporting Frequency: Weekly, Periodic, Monthly
Primary Data Source: Payroll and Workforce Management Systems
Business Owner: Retail Operations
Notes / Common Considerations: The policy must define treatment of employer NI, pensions, agency labour and bonuses. This KPI is store labour, not all company labour.

Labour Cost % of Sales
Business Purpose: Measure how much store sales revenue is consumed by store labour cost.
Business Definition: Store Labour Cost expressed as a percentage of Net Sales.
Formula (business level): 
(Store Labour Cost / Net Sales) x 100
Calculation Logic: Divide Store Labour Cost by Net Sales for the same scope and period.
Unit of Measure: Percentage (%)
Reporting Frequency: Weekly, Periodic, Monthly
Primary Data Source: Payroll, Workforce Management and Point-of-Sale Systems
Business Owner: Retail Operations
Notes / Common Considerations: A lower percentage is not automatically better if availability, queues, service or store standards deteriorate.
—
Sales per Labour Hour
Business Purpose: Measure store labour productivity.
Business Definition: Net Sales generated for each actual labour hour worked by included store colleagues.
Formula (business level): 
Net Sales / Labour Hours Worked
Calculation Logic: Divide Net Sales by actual recorded labour hours for the same scope and period.
Unit of Measure: GBP per Labour Hour (£/hour)
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Workforce Management, Time & Attendance and Point-of-Sale Systems
Business Owner: Retail Operations
Notes / Common Considerations: Use actual hours worked where reliable. Store format, service model and trading intensity affect comparisons.

Shrinkage %
Business Purpose: Measure unexplained inventory loss and stock-control weakness.
Business Definition: Value of stock loss not explained by recorded sales, authorised waste, transfers or other legitimate movements, expressed as a percentage of Net Sales.
Formula (business level): 
(Shrinkage Value / Net Sales) x 100
Calculation Logic: Compare expected inventory with verified inventory after legitimate movements and recognised adjustments, then express unexplained loss value as a percentage of Net Sales.
Unit of Measure: Percentage (%)
Reporting Frequency: Periodic, Monthly, Annual
Primary Data Source: Inventory Management, Stock Count and Point-of-Sale Systems
Business Owner: Loss Prevention
Notes / Common Considerations: Shrinkage can arise from theft, scanning errors, receiving discrepancies or stock-record inaccuracies. Keep separate from recorded Waste.

4.7 Supply Chain
On-Time Delivery %
Business Purpose: Measure whether deliveries arrive within agreed delivery windows.
Business Definition: Percentage of completed deliveries that arrive within FreshMart's approved delivery-time tolerance.
Formula (business level): 
(On-Time Deliveries / Total Completed Deliveries) x 100
Calculation Logic: Compare actual delivery arrival time with the agreed delivery window for each eligible completed delivery.
Unit of Measure: Percentage (%)
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Transport Management and Distribution Systems
Business Owner: Logistics
Notes / Common Considerations: FreshMart must define the approved tolerance. Very early arrivals may also be operationally problematic.

Order Fill Rate
Business Purpose: Measure how completely store or distribution orders are supplied.
Business Definition: Percentage of eligible ordered product quantity actually supplied.
Formula (business level): 
(Quantity Supplied / Quantity Ordered) x 100
Calculation Logic: Compare supplied quantity with confirmed ordered quantity across eligible order lines.
Unit of Measure: Percentage (%)
Reporting Frequency: Daily, Weekly, Periodic, Monthly
Primary Data Source: Ordering, Warehouse Management and Distribution Systems
Business Owner: Supply Chain
Notes / Common Considerations: Approved substitutions, cancellations and store-requested amendments must be treated consistently.

Supplier Service Level %
Business Purpose: Measure whether suppliers fulfil agreed demand both in full and on time.
Business Definition: Percentage of eligible supplier order lines delivered in full and within the agreed delivery window.
Formula (business level): 
(Order Lines Delivered In Full and On Time / Total Eligible Supplier Order Lines) x 100
Calculation Logic: For each eligible supplier order line, assess both quantity fulfilment and delivery timing against agreed terms. Count only lines meeting both conditions as successful.
Unit of Measure: Percentage (%)
Reporting Frequency: Weekly, Periodic, Monthly
Primary Data Source: Supplier Ordering, Goods Receiving and Procurement Systems
Business Owner: Procurement
Notes / Common Considerations: This is broader than On-Time Delivery because a punctual short-delivery does not count as successful service.
4.8 Finance & Profitability
Cost of Goods Sold
Business Purpose: Measure the recognised direct cost of products sold.
Business Definition: Cost of products recognised as sold during the reporting period under FreshMart's approved inventory valuation policy.
Formula (business level): 
Opening Inventory + Purchases - Closing Inventory
Calculation Logic: Recognise the product cost attributable to goods sold using FreshMart's approved valuation policy and compatible inventory-cost basis.
Unit of Measure: GBP (£)
Reporting Frequency: Weekly, Periodic, Monthly, Annual
Primary Data Source: Finance, Procurement and Inventory Systems
Business Owner: Finance

Gross Profit
Business Purpose: Measure the value remaining from sales after direct product cost.
Business Definition: Net Sales less Cost of Goods Sold for the same reporting scope and period.
Formula (business level): 
Net Sales - Cost of Goods Sold
Calculation Logic: Subtract COGS from Net Sales for the same scope and reporting period.
Unit of Measure: GBP (£)
Reporting Frequency: Weekly, Periodic, Monthly, Annual
Primary Data Source: Finance and Sales Systems
Business Owner: Finance
Notes / Common Considerations: Gross Profit does not deduct store labour, property, utilities or other operating expenses.

Gross Margin %
Business Purpose: Measure product-level profitability relative to sales.
Business Definition: Gross Profit expressed as a percentage of Net Sales.
Formula (business level): 
(Gross Profit / Net Sales) x 100
Calculation Logic: Divide Gross Profit by Net Sales for the same scope and period.
Unit of Measure: Percentage (%)
Reporting Frequency: Weekly, Periodic, Monthly, Annual
Primary Data Source: Finance and Sales Systems
Business Owner: Finance
Notes / Common Considerations: Changes may reflect product cost, selling price, promotions, supplier funding or product mix.

Operating Margin %
Business Purpose: Measure how much operating profit remains from sales after recognised operating expenses.
Business Definition: Operating Profit expressed as a percentage of Net Sales.
Formula (business level): 
(Operating Profit / Net Sales) x 100
Calculation Logic: Deduct recognised operating expenses from Gross Profit to determine Operating Profit, then divide by Net Sales.
Unit of Measure: Percentage (%)
Reporting Frequency: Periodic, Monthly, Quarterly, Annual
Primary Data Source: Finance System
Business Owner: Finance
Notes / Common Considerations: Do not confuse with Gross Margin. FreshMart must maintain an approved definition of operating expenses included.
5. Glossary of Retail Terms
Active Store - A FreshMart location considered open and trading during the relevant reporting period.
Average Selling Price (ASP) - Average Net Sales generated per product unit sold.
Average Transaction Value (ATV) - Average Net Sales generated per completed transaction.
Baseline Sales - Expected sales without the effect of a specific promotion.
Basket - Products purchased within a single customer transaction.
Category - Commercially managed group of similar or related products.
Comparable Store - Store meeting approved Like-for-Like eligibility criteria.
Cost of Goods Sold (COGS) - Recognised cost of products sold during a reporting period.
Distribution Centre (DC) - Logistics facility used to receive, hold and distribute stock.
Gross Margin - Gross Profit expressed as a percentage of Net Sales.
Gross Profit - Net Sales remaining after COGS is deducted.
Gross Sales - Initial sales value before relevant sales deductions.
Inventory - Products held for future sale or distribution.
Like-for-Like (LFL) - Comparison using a consistent group of established stores across both periods.
Markdown - Reduction in selling price, often used to clear stock or reduce waste; not automatically a promotion.
Net Sales - Sales revenue after relevant deductions and excluding VAT under FreshMart's approved definition.
Out of Stock (OOS) - Product expected to be available but unavailable for customer purchase.
Product Mix - Combination of products or categories contributing to total sales.
Promotion - Approved temporary customer offer intended to influence purchasing behaviour.
Ranged Product - Product approved for sale within a particular store, format or channel.
Replenishment - Process of replacing stock that has been sold or consumed.
Shrinkage - Unexplained inventory loss after legitimate stock movements are accounted for.
SKU - Stock Keeping Unit; a specific saleable product or variant tracked individually.
Stock Availability - Extent to which expected products are actually available for customer purchase.
Stock on Hand - Quantity of inventory recorded as held at a location at a point in time.
Trading Hour - Hour during which a store is open and available for customer trading.
Transaction - Completed customer purchase recorded through an approved sales channel.
Units per Transaction (UPT) - Average number of product units purchased per transaction.
Waste - Known and recorded inventory loss such as expiry, spoilage or damage.

