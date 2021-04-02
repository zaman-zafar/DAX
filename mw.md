<a href="red">**MW 25% = **</a>
<pre>
CALCULATE (
    SUMX (
        FILTER (
            '1-Sales Details',
            '1-Sales Details'[NETAMOUNT] / '1-Sales Details'[QTY] >= 100
        ),
        '1-Sales Details'[QTY] * 1
    ),
    ItemMaster[Z3] = "W",
    '1-Sales Details'[TENDERTYPE] <> "5",
    FILTER (
        '1-Sales Details',
        DIVIDE (
            '1-Sales Details'[DISCAMOUNT],
            '1-Sales Details'[PRICE] * '1-Sales Details'[QTY]
        ) < .25
    )
)
    + CALCULATE (
        SUMX (
            FILTER (
                '1-Sales Details',
                '1-Sales Details'[NETAMOUNT] / '1-Sales Details'[QTY] >= 100
            ),
            '1-Sales Details'[QTY] * 2
        ),
        ItemMaster[Z2] = "E",
        '1-Sales Details'[TENDERTYPE] <> "5",
        FILTER (
            '1-Sales Details',
            DIVIDE (
                '1-Sales Details'[DISCAMOUNT],
                '1-Sales Details'[PRICE] * '1-Sales Details'[QTY]
            ) < .25
        )
    )