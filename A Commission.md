<a href="red">**A Commission =**</a>

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
            ALL ( ItemMaster ),  
            ItemMaster[CategoryName] = "A"  
                || ItemMaster[CategoryName] = "A"  
        ),  
        '1-Sales Details'[TENDERTYPE] <> "5",  
        FILTER (  
            '1-Sales Details',  
            DIVIDE (  
                '1-Sales Details'[DISCAMOUNT],    
                CALCULATE (  
                    VALUES ( ItemMaster[sellingprice] ),   
                    CROSSFILTER ( ItemMaster[Itemcode], '1-Sales Details'[ITEMID], ONEWAY ) 
                ) * '1-Sales Details'[QTY]  
            ) <= .40  
        )  
    )  
RETURN  
    IF ( qty <= 3, qty * 1, IF ( qty <= 5, qty * 2, qty * 3 ) )  
