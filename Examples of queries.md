Let's discover this database.

1) Have a look of each one of the 8 tables. Well, more specifically get the info about 'orderdetails' and 'payments':
> Nice to bear in mind that here the first 2 columns 'orderNumber', 'productCode' are a combination of primary keys for the table 'orderdetails' and foreign keys at the same time.

<pre>select * 
from orderdetails;</pre>

> Similarly, 'customerNumber', 'checkNumber' are primary keys while 'customerNumber' refers also as foreigh key.

<pre>select * 
from payments;</pre>
