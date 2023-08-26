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

## 3. Get the company's number, company's name (customer name), date of order, status and number of order. We want ascending order by company's number whereas descending by number of order:

<pre>select o.customerNumber, c.customerName, o.orderDate, o.status, o.orderNumber 
from orders o
join customers c on o.customerNumber=c.customerNumber
order by customerNumber, orderNumber desc;</pre>
> As you can see, we are joining 2 tables. We could use the 'using' syntax since there are identical column names for the keys. However, I prefer the approach above as it clearly displays the connections. Nevertheless, using the 'using' syntax would make the query simpler:


<pre>select o.customerNumber, c.customerName, o.orderDate, o.status, o.orderNumber 
from orders o
join customers c using (customerNumber)
order by customerNumber, orderNumber desc;</pre>
## 4. I want each customer to receive the items they purchased, determine the total amount they spent, and identify the employee who assisted them:
