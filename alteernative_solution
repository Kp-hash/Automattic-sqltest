SELECT
  temp,
  name,
  state
FROM (
  SELECT
    temp,
    name,
    state,
    ROW_NUMBER() OVER(PARTITION BY name ORDER BY temp DESC) rn
  FROM
    `bigquery-public-data.noaa_gsod.gsod2019` gsod
  JOIN
    `bigquery-public-data.noaa_gsod.stations` st
  ON
    gsod.stn=st.usaf
  WHERE
    name IS NOT NULL
    AND country='US' 
    AND st.state in ("NY","IL","SC","IN","PA")
    AND gsod.mo in ('06','07','08'))

WHERE
  rn=1
ORDER BY
  temp DESC;
