<a href="red">**Sales&Stock = **</a>
<pre>
UNION (
    SELECTCOLUMNS (
        'Closing Stock 1',
        "ITEMID", 'Closing Stock 1'[ITEMID],
        "Date", 'Closing Stock 1'[TRANSDATE],
        "Store", 'Closing Stock 1'[INVENTSITEID],
        "BuyerGroup", BLANK(),
        "Identity", BLANK(),
        "Stock", 'Closing Stock 1'[AMOUNT],
        "sales", BLANK(),
        "Qty P", 'Closing Stock 1'[QTY],
        "Qty s", BLANK()
    ),
    SELECTCOLUMNS (
        '1-Sales Details',
        "ITEMID", '1-Sales Details'[ITEMID],
        "Date", '1-Sales Details'[TRANSDATE],
        "Store", '1-Sales Details'[STORE],
        "BuyerGroup", '1-Sales Details'[ITEMBUYERGROUPID],
        "Identity", '1-Sales Details'[Identify],
        "Stock", '1-Sales Details'[Purchase],
        "sales", '1-Sales Details'[NETAMOUNT],
        "Qty P", BLANK(),
        "Qty s", ('1-Sales Details'[QTY])*-1
    )
)

 
