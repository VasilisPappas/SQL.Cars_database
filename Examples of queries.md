Let's discover this database. Below is the connectivity structure of tables:

# productlines -> products 
# offices -> employees -> customers -> orders 
# orderdetails -> orders
# orderdetails -> products
# payments -> customers


## 1. Have a look of each one of the 8 tables. Well, more specifically get only the info about 'orderdetails' and 'payments':
> Nice to bear in mind that here the first 2 columns 'orderNumber', 'productCode' are a combination of primary keys for the table 'orderdetails' and foreign keys at the same time.

<pre>select * 
from orderdetails;</pre>

> Similarly, 'customerNumber', 'checkNumber' are primary keys while 'customerNumber' serves also as a foreigh key.

<pre>select * 
from payments;</pre>

## 2. Get the name of each product, along with the price and its category as well as the general text description:
<pre>select p1.productName,p1.buyPrice, p1.productLine, p2.textDescription
from products p1
join productlines p2 on p1.productLine=p2.productLine;</pre>

## 3. I want each customer to receive the items they purchased, determine the total amount they spent, and identify the employee who assisted them:
