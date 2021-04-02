<a href="red">**acc commission =**</a>
<pre> 
var qty = CALCULATE (
    SUMX (
        FILTER (
            '1-Sales Details',
            '1-Sales Details'[NETAMOUNT] / '1-Sales Details'[QTY] >= 50
        ),
        '1-Sales Details'[QTY]
    ),
    FILTER (
        ItemMaster,
        ItemMaster[Z3] = "Accessories"
           
    ),
    '1-Sales Details'[TENDERTYPE] <> "5",
    FILTER (
        '1-Sales Details',
        DIVIDE (
            '1-Sales Details'[DISCAMOUNT],
            '1-Sales Details'[PRICE] * '1-Sales Details'[QTY]
        ) <= .20
    )
)


return If(qty <= 9 ,qty*1,IF(qty<=16,qty*2,qty*3))
