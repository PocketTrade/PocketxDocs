# 已實現損益

用於查詢已實現損益，需要先登入。

!!! Example "Input"

    ```c#
    var res = pocketx.ListProfitLoss(begin_date, end_date, pocketx.StockAccount);
    Console.WriteLine($"ProfitLoss: {res}")
    ```

!!! Success "Output"

    ```
    ProfitLoss: {"9802269":[{"seqno":"5540359","dseq":"CO180","price":"123","pr_ratio":"-4.06","cond":"0","id":"0","code":"4953","quantity":"2000","pnl":"-10380","date":"20251030"},{"seqno":"5540359","dseq":"CJ239","price":"115","pr_ratio":"3.24","cond":"0","id":"1","code":"3029","quantity":"1000","pnl":"3592","date":"20251009"}]}
    ```

!!! Info "Attribute"

    ```
    seqno (string): seqno no.
    dseq (string): seqno no.
    price (decimal): 價格
    pr_ratio (decimal): 損益比
    cond (StockOrderCond): {
                Cash: 現股(預設值)
                Netting: 餘額交
                MarginTrading: 融資
                ShortSelling: 融券
                Emerging: 興櫃
            }
    "id": 可利用此id查詢明細
    "code": 商品代碼
    quantity (int): 數量
    pnl (fldecimaloat): 損益
    date (string): 交易日期
    ```