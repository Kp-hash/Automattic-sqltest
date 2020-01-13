SELECT distinct usaf,
                name,
                country,
                state
FROM `bigquery-public-data.noaa_gsod.stations`
WHERE country = 'US'
  AND state = 'SC'
GROUP BY name,
         usaf,
         country,
         state
ORDER BY name ;
