# Dax code used in PowerBI report

<a href="red">**crossfilesalesandstock =**</a>

<pre>:
CALCULATE (  
    SUM ( 'ciurrent stock'[stockss] ),  
    CROSSFILTER ( '1-Sales Details'[STORE], 'Complete Shop Details'[Sotre Name], BOTH )  
) 


