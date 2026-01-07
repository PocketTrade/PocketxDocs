# 銀行餘額

用於查詢現貨交割帳戶餘額，需要先登入。

!!! Example "Input"

    ```c#
    var res = pocketx.AccountBalance();
    Console.WriteLine($"accountBalance: {res}");
    ```

!!! Success "Output"

    ```
    accountBalance: accountBalance: {"acc_balance":0.0,"date":"xx/xx/2025 05:59:26","errmsg":""}
    ```

!!! Info "Attribute"

    ```json
    acc_balance (float): 餘額,
    date (str): 查詢日期,
    errmsg (str): 錯誤訊息
    ```