## Cointab Data Analyst Challenge

## About the Challenge

The challenge involves creating analytical reconciliation models, reports, and MIS on financial data using Cointab's web-based SaaS software

## Business Scenario 

You are a data analyst and have a large ecommerce company in India (let’s call it X) as a client. X gets a few thousand orders via their website on a daily basis and they have to deliver them as fast as they can. For delivering the goods ordered by the customers, X has tied up with multiple courier companies in India who charge them some amount per delivery. On an average, the delivery charges are Rs. 100 per shipment. So if X ships 1,00,000 orders per month, they have to pay approximately Rs. 1 crore to the courier companies on a monthly basis as charges. 

## Input Data 

**Left-Hand Side (LHS) Data (X's internal data spread across three reports):**

1. **Website Order Report:** This report contains Order IDs and various products (SKUs) included in each order. The Order ID is a common identifier between X's order report and the courier company's invoice.

2. **SKU Master:** This data includes the gross weight of each product. It is used to calculate the total weight of each order and to compare it against the weight reported by the courier company in their CSV invoice. The courier company calculates weight in slabs of 0.5 KG multiples, so you must determine the total weight of the shipment and applicable weight slabs.

3. **Warehouse Pincode to All India Pincode Mapping:** This mapping is used to determine the delivery zone (a/b/c/d/e) and to compare it against the information reported by the courier company in their CSV invoice per Order ID.

**Right-Hand Side (RHS) Data (courier company invoice in CSV file):**

The courier company's invoice in CSV format contains the following fields:

- AWB Number (courier company’s internal ID)
- Order ID (X's order ID)
- Weight of shipment
- Warehouse pickup pincode
- Customer delivery pincode
- Zone of delivery
- Charges per shipment
- Type of shipment

The invoice also includes the courier charges rate card at weight slab and pincode level. The type of shipment (Forward charges or Forward and RTO charges) determines the applicable charges based on zones and fixed and additional weights according to weight slabs.

For the first 0.5 KG, a "fixed" rate is applicable. For each additional 0.5 KG, an "additional" weight charge in the same proportion is applicable. The total charges will be the sum of the "fixed" and "total additional" charges, if any.

### Output Data 1

The goal is to create a resultant CSV file with the following columns:

