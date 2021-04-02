<a href="red">**Imp C =**</a>
<pre>
VAR qty =
    CALCULATE (
        SUMX (
            FILTER (
                '1-Sales Details',
                '1-Sales Details'[NETAMOUNT] / '1-Sales Details'[QTY] >= 50
            ),
            '1-Sales Details'[QTY]
        ),
        FILTER (
            ItemMaster,
            ItemMaster[CategoryName] = "Imp"
                || ItemMaster[CategoryName] = "Imp"
        ),
        '1-Sales Details'[TENDERTYPE] <> "5",
        FILTER (
            '1-Sales Details',
            DIVIDE (
                '1-Sales Details'[DISCAMOUNT],
                '1-Sales Details'[PRICE] * '1-Sales Details'[QTY]
            ) <= .25
        )
    )
RETURN
    IF ( qty <= 3, qty * 1, IF ( qty <= 5, qty * 2, qty * 3 ) )
