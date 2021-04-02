<a href="red">**commission giftset =**</a>
<pre>
CALCULATE (
    SUM ( '1-Sales Details'[QTY] ),
    ItemMaster[CategoryName] = "Cosmetics Gift Set",
    '1-Sales Details'[TENDERTYPE] <> "5",
    FILTER (
        '1-Sales Details',
        '1-Sales Details'[NETAMOUNT] / '1-Sales Details'[QTY] > 20
    )
) * 15
</pre>

<a href="red">**crossfilesalesandstock =**</a>
<pre>
CALCULATE (
    SUM ( 'ciurrent stock'[stockss] ),
    CROSSFILTER ( '1-Sales Details'[STORE], 'Complete Shop Details'[Sotre Name], BOTH )
)
</pre>

<a href="red">**discountPercentage =**</a>
<pre>
DIVIDE (
    SUM ( '1-Sales Details'[DISCAMOUNT] ),
    SUM ( '1-Sales Details'[PRICE] ) * SUM ( '1-Sales Details'[QTY] )
)
</pre>

<a href="red">**extra percentage =**</a>
<pre>
ROUNDDOWN (
    ROUNDDOWN ( ( [%  Cosmetics] - 1 ), 2 ) * 100 / 5,
    0
) * .02 * 100
</pre>

<a href="red">**Salespreviousyear =**</a>
<pre>
CALCULATE (
    SUM ( '1-Sales Details'[NETAMOUNT] ),
    DATEADD ( 'Date'[Date], -1, YEAR )
)
</pre>


