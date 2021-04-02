<a href="red">**% Commission total =**</a>
<pre>
DIVIDE (
    CALCULATE (
        SUM ( '1-Sales Details'[NETAMOUNT] ),
       
        '1-Sales Details'[TENDERTYPE] <> "5"
    ),
    CALCULATE (
        SUM ( 'Commission target'[Amount] ),
        'Commission target'[Type] = "Total Target"
    )
)
</pre>

<a href="red">**% transaction without customer =**</a>
<pre>
DIVIDE (
    COUNTROWS ( DISTINCT ( '1-Sales Details'[RECEIPTID] ) ),
    [Total sales Transactions]
)
</pre>

<a href="red">**Actual gender =**</a>
<pre>
LOOKUPVALUE (
    'Employee Data'[GENDER],
    'Employee Data'[EMPLOYEECODE], '1-Sales Details'[STAFF]
)
</pre>

<a href="red">**Actual selling =**</a>
<pre>
CALCULATE (
    MAX ( 'selling price standard'[FinalPrice] ),
    CROSSFILTER ( '1-Sales Details'[ITEMID], ItemMaster[Itemcode], BOTH )
)
</pre>

<a href="red">**Actual staff =**</a>
<pre>
LOOKUPVALUE (
    'Employee Data'[EMPNAME],
    'Employee Data'[EMPLOYEECODE], '1-Sales Details'[STAFF]
)
</pre>

