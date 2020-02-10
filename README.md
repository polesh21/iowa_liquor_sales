# Iowa_liquor_sales exploratory data analysis


This dataset contains the spirits purchase information of Iowa Class “E” liquor licensees by product and date of purchase from January 1, 2012 to current. The dataset can be used to analyze total spirits sales in Iowa of individual products at the store level.

This dataset has the following 24 columns:
| Column Name           | API Column Name     | Data Type     | Description                                                                                                                                                                                                                                                |
|-----------------------|---------------------|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Invoice/Item Number   | invoice_line_no     | text          | Concatenated invoice and line number associated with the liquor order. This provides a unique identifier for the individual liquor products included in the store order                                                                                    |
| Date                  | date                | calendar_date | Date of order                                                                                                                                                                                                                                              |
| Store Number          | store               | text          | Unique number assigned to the store who ordered the liquor.                                                                                                                                                                                                |
| Store Name            | name                | text          | Name of store who ordered the liquor.                                                                                                                                                                                                                      |
| Address               | address             | text          | Address of store who ordered the liquor.                                                                                                                                                                                                                   |
| City                  | city                | text          | City where the store who ordered the liquor is located                                                                                                                                                                                                     |
| Zip Code              | zipcode             | text          | Zip code where the store who ordered the liquor is located                                                                                                                                                                                                 |
| Store Location        | store_location      | point         | Location of store who ordered the liquor. The Address, City, State and Zip Code are geocoded to provide geographic coordinates. Accuracy of geocoding is dependent on how well the address is interpreted and the completeness of the reference data used. |
| County Number         | county_number       | text          | Iowa county number for the county where store who ordered the liquor is located                                                                                                                                                                            |
| County                | county              | text          | County where the store who ordered the liquor is located                                                                                                                                                                                                   |
| Category              | category            | text          | Category code associated with the liquor ordered                                                                                                                                                                                                           |
| Category Name         | category_name       | text          | Category of the liquor ordered.                                                                                                                                                                                                                            |
| Vendor Number         | vendor_no           | text          | The vendor number of the company for the brand of liquor ordered                                                                                                                                                                                           |
| Vendor Name           | vendor_name         | text          | The vendor name of the company for the brand of liquor ordered                                                                                                                                                                                             |
| Item Number           | itemno              | text          | Item number for the individual liquor product ordered.                                                                                                                                                                                                     |
| Item Description      | im_desc             | text          | Description of the individual liquor product ordered.                                                                                                                                                                                                      |
| Pack                  | pack                | number        | The number of bottles in a case for the liquor ordered                                                                                                                                                                                                     |
| Bottle Volume (ml)    | bottle_volume_ml    | number        | Volume of each liquor bottle ordered in milliliters.                                                                                                                                                                                                       |
| State Bottle Cost     | state_bottle_cost   | number        | The amount that Alcoholic Beverages Division paid for each bottle of liquor ordered                                                                                                                                                                        |
| State Bottle Retail   | state_bottle_retail | number        | The amount the store paid for each bottle of liquor ordered                                                                                                                                                                                                |
| Bottles Sold          | sale_bottles        | number        | The number of bottles of liquor ordered by the store                                                                                                                                                                                                       |
| Sale (Dollars)        | sale_dollars        | number        | Total cost of liquor order (number of bottles multiplied by the state bottle retail)                                                                                                                                                                       |
| Volume Sold (Liters)  | sale_liters         | number        | Total volume of liquor ordered in liters. (i.e. (Bottle Volume (ml) x Bottles Sold)/1,000)                                                                                                                                                                 |
| Volume Sold (Gallons) | sale_gallons        | number        | Total volume of liquor ordered in gallons. (i.e. (Bottle Volume (ml) x Bottles Sold)/3785.411784)                                                                                                                                                          |

Project consists of 3 parts:

1. Connecting to Google Bigquery public data "iows_liquor_sales"
2. Data preparation
3. Data Analysis

Data Analysis is the main part of the project and includes analysis of:

1) Totals
   Sold liters amount, broken by years, months and days of a week
2) Cities
   Top cities based on total_volume_sold_liters metric
3) Stores
   Stores by total_sale_dollars
4) Categories
   Top categories based on total_sale_dollars and total_volume_sold_liters metrics + aggregated categories
5) Vendors
   Information about vendors based on total_sale_dollars and total_volume_sold_liters metrics + most popular bottle_volume for every vendor
6) Products
   Top products by total_volume_sold_liters metrics
