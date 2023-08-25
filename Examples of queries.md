Let's discover this database.
# Order structure of tables: 
# productlines -> products -> offices -> employees -> customers -> orders -> orderdetails -> payments



## 1. Have a look of each one of the 8 tables. Well, more specifically get only the info about 'orderdetails' and 'payments':
> Nice to bear in mind that here the first 2 columns 'orderNumber', 'productCode' are a combination of primary keys for the table 'orderdetails' and foreign keys at the same time.

<pre>select * 
from orderdetails;</pre>

> Similarly, 'customerNumber', 'checkNumber' are primary keys while 'customerNumber' serves also as a foreigh key.

<pre>select * 
from payments;</pre>

## 2. 
