﻿<a href="red">**Cosmetics Commission =**</a>
<pre>
IF (
    [% Commission Cosmetics] = 1,
    CALCULATE (
        SUM ( '1-Sales Details'[NETAMOUNT] ),
        FILTER ( ItemMaster, ItemMaster[Z2] = "Cosmetics" ),
        '1-Sales Details'[TENDERTYPE] <> "5"
    ) * .1,
    IF (
        [% Commission Cosmetics] > 1,
        CALCULATE (
            SUM ( '1-Sales Details'[NETAMOUNT] ),
            FILTER ( ItemMaster, ItemMaster[Z2] = "Cosmetics" ),
            '1-Sales Details'[TENDERTYPE] <> "5"
        ) * .1
            + (
                ROUNDDOWN (
                    ROUNDDOWN ( ( [% Commission Maylaa Cosmetics] - 1 ), 2 ) * 100 / 5,
                    0
                ) * .02
            )
                * CALCULATE (
                    SUM ( '1-Sales Details'[NETAMOUNT] ),
                    FILTER ( ItemMaster, ItemMaster[Z2] = "Cosmetics" ),
                    '1-Sales Details'[TENDERTYPE] <> "5"
                )
    )
)