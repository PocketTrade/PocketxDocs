# 委託回報

每次使用 PlaceOrder、UpdateOrder 或者 CancelOrder 時，皆會收到來自交易所的委託或成交回報。

## 處理委託及成交回報

!!! Example "Input"

    ```c#
    static public void MyCallBackFunction(OrderState orderState, dynamic msg)
    {
        Console.WriteLine("my_order_callback");
        Console.WriteLine($"OrderState.{orderState} - {msg}");
    }

    pocketx.SetOrderCallback((orderState, msg) => {
        Console.WriteLine($"訂單狀態變更: {orderState} - {msg}");
    });

    ```

!!! Success "Output"

    ```
    [2025-10-30 14:38:43][INF][SYSTEM] Set Order Callback Successfully!!!
    ```

### 委託回報

!!! Success

    ```
    OrderState.StockOrder - {
        "stat": "SORDER",
        "msg": {
            "operation": {
                "op_type": "Cancel",
                "op_code": "",
                "op_msg": ""
            },
            "order": {
                "id": "",
                "seqno": 355251,
                "ordno": "CP354",
                "account": "<your-account-ino>",
                "action": "Buy",
                "price": "56.0",
                "quantity": "5",
                "order_type": "ROD",
                "price_type": "LMT",
                "order_cond": "Cash",
                "order_lot": "Common",
                "custom_field": "Test"
            },
            "status": {
                "id": "",
                "exchange_ts": "113842123",
                "modified_price": "56.0",
                "cancel_quantity": "1000",
                "order_quantity": "0",
                "web_id": ""
            },
            "contract": {
                "security_type": "STK",
                "exchange": "TSE",
                "code": "0050",
                "symbol": "TSE0050",
                "name": "元大台灣50",
                "currency": "TWD"
            }
        }
    }
    ```

### 成交回報

!!! Success 

    ```
    ...
    ```