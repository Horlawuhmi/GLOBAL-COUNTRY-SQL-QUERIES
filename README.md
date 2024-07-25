# GLOBAL-COUNTRY-SQL-QUERIES

MySQL Queries for the global country information data.


-- check for duplicates--
SELECT Country, COUNT(*)
FROM world_data
GROUP BY country
HAVING COUNT(*) > 1;

---- countries with the largest population--
SELECT Country, population, Largest_city
FROM world_data
ORDER BY Population;

-- Highest minimum wage--

SELECT Country, Minimum_wage
FROM world_data
ORDER BY Minimum_wage desc;

--- highest life expectancy---

SELECT Country, Life_expectancy
FROM world_data
ORDER BY Life_expectancy desc
LIMIT 10;

-- Correlation between forested area and co2 emissions--
SELECT country, Forested_area, CO2_Emissions
FROM world_data
GROUP BY country, Forested_area, CO2_Emissions
ORDER BY  Forested_area desc, CO2_Emissions desc;

--- correlation between birth rate, maternal mortality rate, infant mortality and fertility rate

SELECT country, Birth_rate, Maternal_mortality_ratio
FROM world_data
ORDER BY Birth_rate desc, Maternal_mortality_ratio desc;

SELECT Country, Birth_rate, infant_mortality
FROM world_data
ORDER BY Birth_rate desc, Infant_mortality desc;

SELECT country, fertility_rate
FROM world_data
ORDER BY Fertility_rate desc;
