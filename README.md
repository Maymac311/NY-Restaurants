# NY-Restaurants
Queries-Finding the best spots in the city

#1. I'm starting by getting a feel for the 'nomnom' table
SELECT *
FROM nomnom;

#2.Looking at what the distinct neighborhoods are
SELECT DISTINCT neighborhoods
FROM nomnom;

#3. Checking to see what the cuisine is like
SELECT DISINCT cusinie
FROM nomnom;

#4. Chinese sounds good, let me see what my options are
SELECT *
FROM nomnom
WHERE cuisine = 'Chinese';

#5. Now, I would like to see all the restaurants with reviews of 4 and above
SELECT *
FROM nomnom
WHERE review >=4;

#6. My friends, Abbie and Ilana, want to have a fancy dinner date. I want to see which Italian restaurants have a price point of at least '$$$'
SELECT *
FROM nomnom
WHERE cuisine = 'Italian'
AND price LIKE '%$$$%';

#7. Now my coworker Trey cant remember the exact name of a restaurant that he went to but he knows it contained the word 'meatball' in it
ELECT *
FROM nomnom
WHERE name LIKE '%meatball%';

#8. I decided to get food delivered to apt. Let me see what all the spots are close to 'Midtown', 'Downtown' or 'Chinatown'
SELECT *
FROM nomnom
WHERE neighborhood = 'Midtown'
OR neighborhood = 'Downtown'
OR neighborhood = 'Chinatown';

#9. I want to see all the health grade pending restaurants (empty values)
SELECT *
FROM nomnom
WHERE health IS NULL;

#10. Creating a Top 10 Restaurants Ranking based on reviews
ELECT *
FROM nomnom
ORDER BY review DESC;

#11. I'm including a limit to cap it at 10;
ELECT *
FROM nomnom
ORDER BY review DESC
LIMIT 10;

#12. Using a CASE statement to change the rating system to
-review > 4.5 is 'Extaordinary'
-review > 4 is 'Excellent'
-review > 3 is 'Good'
-review > 2 is 'Fair'
-Everything else is Poor

SELECT  name,
CASE
WHEN review > 4.5 THEN 'Extraordinary'
WHEN review > 4 THEN 'Excellent'
WHEN review > 3 THEN 'Good'
WHEN review >2 THEN 'Fair'
ELSE 'Poor'
END AS 'Review'
FROM nomnom;



