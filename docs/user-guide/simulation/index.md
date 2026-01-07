# 模擬模式

使用者能在模擬環境中進行測試。

!!! example 

    ```C#
    var pocketx = new Pocketx(simulation: true);
    ```

## 可使用的APIs

!!! info "行情資料"

    1. Subscribe
    2. UnSubscribe
    3. Ticks

!!! info "下單"

    1. PlaceOrder
    2. UpdateOrder
    3. CancelOrder
    4. UpdateStatus
    5. ListTrades

!!! info "帳務"

    1. ListPositions
    2. ListProfitLoss
    