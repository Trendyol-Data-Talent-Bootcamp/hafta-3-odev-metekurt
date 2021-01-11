# SORU 1

```SQL

SELECT name,car.id AS car_id,car.model AS car_model,manufacture.year AS manufacture_year,
  ARRAY(SELECT AS STRUCT id, TIMESTAMP_ADD(date, INTERVAL 3 hour) AS date FROM unnest(purchase)) AS purchase
FROM `dsmbootcamp.han_kurt.semi_structured_hw`
CROSS JOIN unnest(car) AS car
CROSS JOIN unnest(manufacture) AS manufacture ON car.id=manufacture.id;

```
