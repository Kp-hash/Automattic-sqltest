SELECT
  st.name,
  st.state,
  max(gsod.temp) AS max_temp

FROM `bigquery-public-data.noaa_gsod.gsod2019` AS gsod

LEFT JOIN `bigquery-public-data.noaa_gsod.stations` AS st ON st.usaf = gsod.stn

  WHERE
    name IS NOT NULL
    AND country='US' 
    AND st.state in ('NY','IL','SC','IN','PA')
    AND gsod.mo in ('06','07','08')


GROUP BY name,state
ORDER BY max_temp DESC;
