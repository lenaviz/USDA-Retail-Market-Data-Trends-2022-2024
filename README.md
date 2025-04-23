# USDA Retail Market Trends: Tomatoes (2022–2024)

This project is a business intelligence dashboard built in Tableau to help visualize trends in retail produce pricing across the U.S.. It is especially useful for anyone working in the B2B space, including:
* Farmers selling produce to distributors
* Distributors coordinating sales to stores
* Regional and national managers at large chains (e.g., Walmart) who need to plan what produce to buy, how much, and when.
  
The dashboard provides both high-level and detailed insights, tailored to different types of users. I built this with Walmart teams in mind, especially those working on the regional or national level to create a dashboard that may be useful for internal planning, pricing, and product decisions.

# What the Dashboard Shows
* Price trends over time
* Comparisons by variety (e.g., Grape Tomatoes vs Heirloom)
* Unit types (e.g., per lb, 10 oz)
* Organic vs. non-organic pricing differences
* Micro-level patterns for regional managers
* Macro-level summaries for national directors

For example, a regional director might look at:
* Whether organic apples are trending up or down in their area
* Which varieties are getting more promotion
* Wether or not produce for their area is coming from a Greenhouse or elsewhere

While a national director can compare:
* Price ranges across regions
* Packaging format performance over time
* Types of varieties that are popular

# Data Source & Cleaning
All data comes from the USDA Agricultural Marketing Service's public dataset: https://mymarketnews.ams.usda.gov/public_data

I filtered and cleaned the dataset to:
* Select only relevant columns with pricing and product info
* Remove rows with missing or incomplete data
* Ensure a consistent date range (2022–2024) across all regions
* Focus on six different U.S. regions (Northeast, Northwest, Southeast, Southwest, Midwest, Southcentral)

Note: I excluded Alaska, Hawaii, and national datasets to keep the focus on clearly defined regional behavior.

# USDA Reporting & Methodology
The USDA releases weekly retail reports for fresh fruits and vegetables. These reports include advertised prices gathered from:
* Printed grocery store flyers
* Newspaper inserts
* Online store ads
* Digital flyers

The USDA tracks promotions from both large national chains (e.g., Walmart, Kroger, Safeway) and regional or independent supermarkets, depending on who publishes ads that week.

I have seperated the datasets by regions. In each dataset for a partiuclar commidity, you will notice that each row in the dataset reflects **one product commodity** in **one region** for **one week**, and includes the following price fields:

# Price Fields Explained:
* Min Price (price_min): The lowest advertised price for a specific product in the region during the week
* Max Price (price_max): The highest advertised price for the same item in that region and time period
* Weighted Average Price (current_wtd_avg_price): An average price that is weighted by how often each price appeared in store ads. This gives a realistic view of what most consumers saw.
* Ad Count (current_ad_count): The number of ads (across print and digital) that featured the item that week. It does not represent the number of stores directly, but rather the frequency of promotion.

### Example row from one of the datasets:

| Date       | Region    | Class      | Commodity | Variety                 | Organic | Unit    | Environment | Min Price | Max Price | Ad Count | Wtd Avg Price |
|------------|-----------|------------|-----------|--------------------------|---------|---------|-------------|-----------|-----------|----------|----------------|
| 02/04/2022 | Southwest | Vegetables | Tomatoes  | VINE RIPES - ON THE VINE | Yes     | per lb  | Greenhouse  | 2.99      | 3.49      | 260      | 3.48           |


This row shows that during the week of February 4, 2022, in the Southwest region, the USDA reported:

* Organic vine-ripened tomatoes on the vine, sold per pound
* Grown in a greenhouse
* Advertised in 260 store promotions
* With prices ranging from $2.99 to $3.49
* And a weighted average advertised price of $3.48

In my dashboard, I have used the weighted average price as standard because it gives a more accurate picture of what prices were most commonly advertised, making it easier to spot trends and compare regions.


