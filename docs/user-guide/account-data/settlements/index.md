# 交割款

用於查詢交割款，需要先登入。

!!! Example "Input"

    ```c#
    var res = pocketx.Settlements();
    Console.WriteLine($"settlements: {res}")
    ```

!!! Success "Output"

    ```
    Settlements: [{"ddate":"20251030","amount":"0","tdate":0},{"ddate":"20251031","amount":"0","tdate":1},{"ddate":"20251103","amount":"175873","tdate":2}]
    ```

!!! Info "Attribute"

    ```json
    ddate (str):交割日期
    amount (str): 交割金額,
    tdate (str): Tday
    ```


    