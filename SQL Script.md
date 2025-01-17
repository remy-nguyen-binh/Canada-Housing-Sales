## Overall look of the dataset
``` sql
SELECT  *
from housing_in_canada;
```

## Data Cleaning
### Check for duplicates
``` sql
SELECT 'address', 'price', Count(*)
FROM housing_in_canada
GROUP BY 'address', 'price'
HAVING COUNT(*) > 1;
```


### Check for missing values
``` sql
SELECT 
    COUNT(*) - COUNT(city) AS missing_city,
    COUNT(*) - COUNT(price) AS missing_price,
    COUNT(*) - COUNT(address) AS missing_address,
    COUNT(*) - COUNT(number_beds) AS missing_bedrooms,
    COUNT(*) - COUNT(number_baths) AS missing_baths,
    COUNT(*) - COUNT(province) AS missing_province,
    COUNT(*) - COUNT(population) AS missing_population,
    COUNT(*) - COUNT(latitude) AS missing_latitude,
    COUNT(*) - COUNT(longitude) AS missing_longitude,
    COUNT(*) - COUNT(median_family_income) AS missing_median_family_income
FROM housing_in_canada;
```

## Data aggregation
### Check the average, min, max and STTDEV of the housing price
``` sql
SELECT 
    AVG(price) as avg_price,
    MIN(price) as min_price,
    MAX(price) as max_price,
    STDDEV(price) as stddev_price
FROM housing_in_canada;
```

### Price per bedrooms
``` sql
SELECT 
    city, 
    AVG(price / number_beds) as avg_price_per_bedroom
FROM housing_in_canada
GROUP BY city
ORDER BY avg_price_per_bedroom DESC
LIMIT 30;
```

### Correlation between the housing price and the median family income
``` sql
SELECT 
    (COUNT(*) * SUM(price * median_family_income) - SUM(price) * SUM(median_family_income)) /
    (SQRT((COUNT(*) * SUM(price * price) - SUM(price) * SUM(price)) *
          (COUNT(*) * SUM(median_family_income * median_family_income) - SUM(median_family_income) * SUM(median_family_income))))
    AS correlation_coefficient
FROM housing_in_canada;
```

### Average price by number of bedrooms and bathrooms
``` sql
SELECT 
    number_beds,
    number_baths,
    AVG(price) as avg_price
FROM housing_in_canada
GROUP BY number_beds, number_baths
ORDER BY number_beds, number_baths;
```

### Cities with the highest and lowest average prices
#### Highest prices
``` sql
SELECT city, AVG(price) as avg_price
FROM housing_in_canada
GROUP BY city
ORDER BY avg_price DESC
LIMIT 10;
```

#### Lowest prices
``` sql
SELECT city, AVG(price) as avg_price
FROM housing_in_canada
GROUP BY city
ORDER BY avg_price ASC
LIMIT 10;
```


### Price range distribution
```sql
SELECT 
    CASE 
        WHEN price < 100000 THEN 'Under 100k'
        WHEN price BETWEEN 100000 AND 250000 THEN '100k-250k'
        WHEN price BETWEEN 250001 AND 500000 THEN '250k-500k'
        WHEN price BETWEEN 500001 AND 1000000 THEN '500k-1M'
        ELSE 'Over 1M'
    END AS price_range,
    COUNT(*) as count
FROM housing_in_canada
GROUP BY price_range
ORDER BY count DESC;
```

``` sql
SELECT 
    city,
    AVG(price / median_family_income) as price_to_income_ratio
FROM housing_in_canada
GROUP BY city
ORDER BY price_to_income_ratio DESC;
```

### Ranking cities by average price within each province
``` sql
SELECT 
    province,
    city,
    avg_price,
    RANK() OVER (PARTITION BY province ORDER BY avg_price DESC) as price_rank
FROM (
    SELECT 
        province,
        city,
        AVG(price) as avg_price
    FROM housing_in_canada
    GROUP BY province, city
) subquery


SELECT 
    city,
    population,
    AVG(price) as avg_price,
    RANK() OVER (ORDER BY population DESC) as population_rank,
    RANK() OVER (ORDER BY AVG(price) DESC) as price_rank
FROM housing_in_canada
GROUP BY city, population
ORDER BY population DESC; ```

## Price per capita
SELECT 
    city,
    AVG(price) / MAX(population) as price_per_capita
FROM housing_in_canada
GROUP BY city
ORDER BY price_per_capita DESC
