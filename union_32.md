<a href="red">**3 AllChequesCombined =**</a>
<pre>

UNION (
    SELECTCOLUMNS (
        '2 Cheque from General Journal',
        "BankName", '2 Cheque from General Journal'[FullbankName],
        "Date", '2 Cheque from General Journal'[TRANSDATE],
        "Store", '2 Cheque from General Journal'[STORENUMBER],
        "ChqNo", '2 Cheque from General Journal'[PAYMREFERENCE],
        "SupplierDetails", '2 Cheque from General Journal'[TXT],
        "Amount", '2 Cheque from General Journal'[AMOUNTCURCREDIT],
        "Type", '2 Cheque from General Journal'[VOUCHER]
    ),
    SELECTCOLUMNS (
        '2 Cheque from General Journal1-1',
        "BankName", '2 Cheque from General Journal1-1'[FullbankName],
        "Date", '2 Cheque from General Journal1-1'[TRANSDATE],
        "Store", '2 Cheque from General Journal1-1'[STORENUMBER],
        "ChqNo", '2 Cheque from General Journal1-1'[PAYMREFERENCE],
        "SupplierDetails", '2 Cheque from General Journal1-1'[TXT],
        "Amount", '2 Cheque from General Journal1-1'[AMOUNTCURDEBIT],
        "Type", '2 Cheque from General Journal1-1'[VOUCHER]
    ),
    SELECTCOLUMNS (
        '2 Cheques in Bank',
        "BankName", '2 Cheques in Bank'[name],
        "Date", '2 Cheques in Bank'[TRANSDATE],
        "Store", '2 Cheques in Bank'[STORENUMBER],
        "ChqNo", '2 Cheques in Bank'[CHEQUENUM],
        "SupplierDetails", '2 Cheques in Bank'[NAME2],
        "Amount", '2 Cheques in Bank'[AMOUNTCUR],
        "Type", '2 Cheques in Bank'[VOUCHER]
    ),
    SELECTCOLUMNS (
        '2 PDC Cheques',
        "BankName", '2 PDC Cheques'[BankNameP],
        "Date", '2 PDC Cheques'[MATURITYDATE],
        "Store", '2 PDC Cheques'[STORENUMBER],
        "ChqNo", '2 PDC Cheques'[CHECKNUMBER],
        "SupplierDetails", '2 PDC Cheques'[NAME2],
        "Amount", '2 PDC Cheques'[AMOUNTPDC],
        "Type", '2 PDC Cheques'[NAME]
    ),
    SELECTCOLUMNS (
        '2 PDC Cheque After clearing',
        "BankName", '2 PDC Cheque After clearing'[BankNameA],
        "Date", '2 PDC Cheque After clearing'[TRANSDATE],
        "Store", '2 PDC Cheque After clearing'[STORENUMBER],
        "ChqNo", '2 PDC Cheque After clearing'[BANKCHEQUENUM],
        "SupplierDetails", '2 PDC Cheque After clearing'[TXT],
        "Amount", '2 PDC Cheque After clearing'[AMOUNTCURDEBIT],
        "Type", '2 PDC Cheque After clearing'[VOUCHER]
    )
)
