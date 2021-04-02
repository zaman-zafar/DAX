<a href="red">**mang C =**</a>
<pre>
IF (
    [% Commission MC] = 1,
    CALCULATE (
        SUM ( '1-Sales Details'[NETAMOUNT] ),
        FILTER ( ItemMaster, ItemMaster[Z2] = "MC" ),
        '1-Sales Details'[TENDERTYPE] <> "5"
    ) * .1,
    IF (
        [% Commission MC] > 1,
        CALCULATE (
            SUM ( '1-Sales Details'[NETAMOUNT] ),
            FILTER ( ItemMaster, ItemMaster[Z2] = "MC" ),
            '1-Sales Details'[TENDERTYPE] <> "5"
        ) * .1
            + (
                ROUNDDOWN (
                    ROUNDDOWN ( ( [% Commission MC] - 1 ), 2 ) * 100 / 5,
                    0
                ) * .02
            )
                * CALCULATE (
                    SUM ( '1-Sales Details'[NETAMOUNT] ),
                    FILTER ( ItemMaster, ItemMaster[Z2] = "MC" ),
                    '1-Sales Details'[TENDERTYPE] <> "5"
                )
    )
)
