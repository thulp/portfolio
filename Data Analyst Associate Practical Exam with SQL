-- Determine the number of products that have the year_added value missing

SELECT COUNT(*) missing_year
FROM public.products
WHERE year_added IS NULL;

-- Data cleaning

SELECT  
	product_id,
	product_type,
	CASE WHEN brand = '-' THEN 'Unknown'
		ELSE brand END AS brand,
	ROUND(CAST(TRIM(' grams' FROM weight) AS decimal), 2) weight,
	ROUND(price:: decimal, 2) price,
	average_units_sold,
	COALESCE(year_added, 2022) year_added,
	UPPER(stock_location) stock_location
FROM public.products;

-- Determine the minimum and maximum values for each product type
SELECT
	product_type,
	MIN(price) min_price,
	MAX(price) max_price
FROM public.products
GROUP BY product_type;
