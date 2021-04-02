<a href="red">**Latest Closing Balance =**</a>
<pre>
SUMX (
    TOPN ( 1, '2  Balance', '2  Balance'[RECID] ),
    '2  Balance'[ENDINGBALANCE]
)
</pre>

<a href="red">**NameA =**</a>
<pre>
MID (
    '2 PDC After clearing'[PAYMMODE],
    5,
    LEN ( '2 PDC After clearing'[PAYMMODE] ) - 4
)
</pre>

<a href="red">**branded =**</a>
<pre>

CALCULATE (
    SUMX (
        '1-Sales Details',
        IF (
            '1-Sales Details'[SalesdivideQty] > 200,
            '1-Sales Details'[QTY] * 10,
            IF ( '1-Sales Details'[SalesdivideQty] > 90, '1-Sales Details'[QTY] * 7 )
        )
    ),
    CROSSFILTER ( ItemMaster[Itemcode], '1-Sales Details'[ITEMID], BOTH ),
    DATESBETWEEN ( 'Date'[Date], [startdate], [start_enddate] ),
    FILTER ( VALUES ( ItemMaster[Z2] ), ItemMaster[Z2] = "Purchase" )
)


