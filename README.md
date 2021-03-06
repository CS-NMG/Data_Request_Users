user count
```
select
	sum(number_of_users) as visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

device count
```
select
	device_type, sum(number_of_users) as visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by device_type;
```

conversions count
```
select
	sum(number_of_conversions) as conversions,
	sum(number_of_order_ids) as orders
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

conversion rate
```
select
	sum(number_of_conversions)*100.0/sum(number_of_users) as conv_rate
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

infected visits count
```
select
	sum(case when isinfected = 1 then number_of_users end) as inf_visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

non-infected visits count
```
select
	sum(case when isinfected = 0 then number_of_users end) as non_inf_visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

infection rate
```
select
	sum(case when isinfected = 1 then number_of_sessions else 0 end)*100.0/sum(number_of_sessions) as inf_rate
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```

non-infection rate
```
select
	sum(case when isinfected = 0 then number_of_sessions else 0 end)*100.0/sum(number_of_sessions) as non_inf_rate
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by tag;
```
