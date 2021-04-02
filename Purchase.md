<a href="red">**Last Refreshed Local =**</a>
<pre>
FORMAT(LASTDATE(LastRefresh_Local[LastRefresh]),"mmm dd, yyyy hh:mm:ss AM/PM")
</pre>

<a href="red">**PuchaseQTY =**</a>
<pre>
CALCULATE(SUM('1- Purchase'[QTY]),CROSSFILTER(ItemMaster[Itemcode],'Sales&Stock'[ITEMID],Both))
</pre>

<a href="red">**PurchaseV1 =**</a>
<pre> 
SUMX(
    FILTER(
        '1- Purchase',
        '1- Purchase'[PURCHPRICE]<>0
    ),
    '1- Purchase'[QTY]*'1- Purchase'[PURCHPRICE]
)+
SUMX(
    FILTER(
        '1- Purchase',
        '1- Purchase'[PURCHPRICE]=0
    ),
    '1- Purchase'[LINEAMOUNT]
)


WarehouseNotmatching =
AND (
    '1- Purchase'[STORENUMBER] = '1- Purchase'[INVENTSITEID],
    '1- Purchase'[INVENTSITEID] = '1- Purchase'[warehouse]
)
