<a href="red">**PT Commission =**</a>
<pre> 
IF (
    CALCULATE (
        SUM ( '1-Sales Details'[NETAMOUNT] ),
        FILTER(all(ItemMaster),ItemMaster[Z2] = "mc"),
      
       all('Complete Shop Details'[Sotre Name])
    ) >= 65000,
    CALCULATE (
        SUMX (
            FILTER (
                '1-Sales Details',
                '1-Sales Details'[NETAMOUNT] / '1-Sales Details'[QTY] >= 10
            ),
            '1-Sales Details'[QTY] * 2
        ),
       ItemMaster[Z2] = "mc",
        '1-Sales Details'[TENDERTYPE] <> "5"
    )
        ,
    CALCULATE (
        SUMX (
            FILTER (
                '1-Sales Details',
                '1-Sales Details'[NETAMOUNT] / '1-Sales Details'[QTY] >= 10
            ),
            '1-Sales Details'[QTY] * 1
        ),
       ItemMaster[Z2] = "mc",
        '1-Sales Details'[TENDERTYPE] <> "5"
    )
       
)
