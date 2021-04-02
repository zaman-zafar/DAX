<a href="red">**sales_brandedperfumes =**</a>
<pre>
CALCULATE (
    SUM ( '1-Sales Details'[QTY] ),
    CROSSFILTER ( ItemMaster[Itemcode], 'Aging report AX'[Item number], BOTH ),
    DATESBETWEEN ( 'Date'[Date], [startdate], [start_enddate] ),
    FILTER ( VALUES ( ItemMaster[Z2] ), ItemMaster[Z2] = "Purchase Perfumes" )
)
</pre>


<a href="red">**CardCorrect =**</a>
<pre>
SUMX (
    FILTER ( 'card Received', 'card Received'[TENDERTYPE] = "2" ),
    'card Received'[AMOUNTMST] * .9811
)
</pre>


<a href="red">**CardNoEntered =**</a>
<pre>
IF ( LEN ( 'card Received'[CARDORACCOUNT] ) = 16, "Correct", "Not Entered" )
</pre>


<a href="red">**last return =**</a>
<pre>
CALCULATE (
    MAX ( '1- Purchase'[INVOICEDATE] ),
    FILTER (
        '1- Purchase',
        
        '1- Purchase'[QTY] < 0
    )
)
</pre>


<a href="red">**LastPurchasedate =**</a>
<pre>
MAX (
    CALCULATE (
        MAX ( '1- Purchase'[INVOICEDATE] ),
        FILTER ( '1- Purchase', '1- Purchase'[QTY] > 0 )
    ),
    CALCULATE (
        MAX ( 'Transfer Order'[DATEFINANCIAL] ),
        FILTER ( 'Transfer Order', 'Transfer Order'[QTY] > 0 )
    )
)
</pre>


<a href="red">**stocktoorder =**</a>
<pre>
IF (
    SUM ( 'current stock'[stockss] ) - SUM ( 'Sales 3 months'[Average sales] ) < 0,
    ROUND (
        SUM ( 'current stock'[stockss] ) - SUM ( 'Sales 3 months'[Average sales] ),
        2
    ),
    BLANK ()
)
</pre>


<a href="red">**TotalStockkarji =**</a>
<pre>
CALCULATE (
    SUM ( 'ciurrent stock'[stockss] ),
    ALL ( 'Complete Shop Details'[Stoer name] ),
    'Complete Shop Details'[Stoer name] <> "MAY"
)
</pre>


