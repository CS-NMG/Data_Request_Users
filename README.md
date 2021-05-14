user count
```
select
	sum(distinct number_of_users) as visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

device count
```
select
	device_type, sum(distinct number_of_users) as visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by device_type;
```

conversions count
```
select
	sum(distinct number_of_conversions) as conversions,
	sum(distinct number_of_order_ids) as orders
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

conversion rate
```
select
	sum(distinct number_of_conversions)*100.0/sum(distinct number_of_users) as conv_rate
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

infected visits count
```
select
	sum(distinct(case when isinfected = 1 then number_of_users end)) as inf_visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

non-infected visits count
```
select
	sum(distinct(case when isinfected = 0 then number_of_users end)) as non_inf_visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;

infection rate
```
select
	sum(distinct(case when isinfected = 1 then number_of_users end)) as inf_visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
select
	sum(case when isinfected = 1 then number_of_sessions else 0 end)*100.0 /sum(number_of_sessions) as ir
from redshift_session_conversion_aggr_tbl
where tag = '184S28W5K'
	and created >= '2021-05-13'
group by tag;

```

non-infection rate
```
select
	sum(distinct(case when isinfected = 0 then number_of_users end)) as non_inf_visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
