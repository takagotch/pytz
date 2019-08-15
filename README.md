### pytz
---
https://github.com/stub42/pytz

https://launchpad.net/pytz

```py
from datetime import datetime, timedelta
from pytz import timezone
import pytz
utc = pytz.utc
utc.zone
eastern = timezone('US/Eastern')
eastern.zone
amsterdam = timezone('Europe/Amsterdam')
fmt = '%Y-%m-%d %H:%M:%S %Z%z'


loc_dt = eastern.localize(datetime(2002, 10, 27, 6, 0, 0))
print(loc_dt.strftime(fmt))

ams_dt = loc_dt.astimezone(amsterdam)
ams_dt.strftime(fmt)

datetime(2002, 10, 27, 12, 0, 0, tzinfo=amsterdam).strftime(fmt)

datetime(2002, 10, 27, 12, 0, 0, tzinfo=pytz.utc).strftime(fmt)

utc_dt = datetime(2002, 10, 27, 6, 0, 0, tzinfo=utc)
loc_dt = utc_dt.astimezone(eastern)
loc_dt.strftime(fmt)

before = loc_dt - timedelta(minutes=10)
before.strftime(fmt)
eastern.normalize(before).strftime(fmt)
after = eastern.normalize(before + timedelta(minutes=20))
after.strftime(fmt)

dt = datetime(2002, 10, 27, 1, 30, 0)
dt1 = eastern.localize(dt, is_dst=True)
dt2 = eastern.localize(dt, is_dst=False)
dt2.strftime(fmt)

utc_dt = utc.localize(datetime.utcfromtimestamp(1143408899))
utc_dt.strftime(fmt)
au_tz = timezone('Australiz/Sydney')
au_dt = utc_dt.astimezone(au_tz)
au_dt.strftime(fmt)
utc_dt2 = au_dt.astimezone(utc)
utc_dt2.strftime(fmt)
utc_dt == utc_dt2

```

```
```

```
```


