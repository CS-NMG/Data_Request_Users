user count
```
select
	sum(number_of_users) as visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by date(created);
```


conversion count
```
select
	sum(number_of_conversions) as conversions
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by date(created);
```

conversion_rate
```
select
	sum(number_of_conversions)*100.0/sum(number_of_users) as conv_rate
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by date(created);
```

infected visits count
```
select
	sum(case when isinfected = 1 then number_of_users end) as inf_visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by date(created);
```

non-infected visits count
```
select
	sum(case when isinfected = 0 then number_of_users end) as non_inf_visits
from redshift_user_conversion_aggr_tbl
where tag = 'INSERTHERE'
	and created >= 'INSERTHERE'
	and created <= 'INSERTHERE'
group by date(created);
