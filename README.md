# Automattic-sqltest
This was a pre-interview  SQL test I passed which got me an interview at Automattic. This was done using google Bigquery NOA public dataset. They required me to modify the SQL code below.

select

  st.name,

  st.state,

  sum(gsod.temp) / 91

from `bigquery-public-data.noaa_gsod.gsod2019` as gsod

left join `bigquery-public-data.noaa_gsod.stations` as st on st.usaf = gsod.stn

where country = "US"

  and st.state in ("NY","IL","SC","IN","PA")

  and gsod.mo in (06,07,08)

group by 1, 2


Please get the query running and working for our team lead, so that they can make a decision for our meetup, and return that query to us to complete the test.
