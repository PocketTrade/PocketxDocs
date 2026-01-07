# 證券

!!! warning
    下單前，請先進行登入以及激活憑證


### 證券委託單

!!! Info "Attribute" 
    ```
    price (float or int): 價格
    quantity (int): 委託數量
    action (Action): {Buy: 買, Sell: 賣}
    price_type (StockPriceType): {LMT: 限價, MKT: 市價, MKP: 範圍市價}
    order_type (OrderType): 委託類別 {ROD, IOC, FOK}
    order_cond (StockOrderCond): {Cash:現股, MarginTrading:融資, ShortSelling:融券}(目前只支持Cash)
    order_lot (StockOrderLot): {Common:整股, Fixing:定盤, Odd:盤後零股, IntradayOdd:盤中零股}
    daytrade_short (DayTradeShort): 現沖 {Yes, No}
    account (:obj:Account): 下單帳號  
    custom_field (string): 備註
    ca (binary): the ca of this order
    ```


### 下單

下單時，請提供 商品檔資訊 以及 下單資訊。


!!! Example "商品檔"

    ```C#
    var contract = pocketx.Contracts.Stocks["TSE"]["0050"];
    ```

!!! Example "Input"

    ```C#
    var order = new StockOrder()
    {
        price = <price>,
        quantity = <qty>,
        action = Action.Buy,
        price_type = StockPriceType.LMT,
        order_type = OrderType.ROD,
        order_lot = orderLot,
        daytrade_short = DayTradeShort.No,
        custom_field = "Test",
    };
    var trade = pocketx.PlaceOrder(contract, order);
    ```

!!! Success "output"

    ```C#
        {
        "contract":{
            "security_type":"STK",
            "code":"0050",
            "symbol":"TSE0050",
            "exchange":"TSE",
            "limit_up":70.8,
            "limit_down":58.0,
            "reference":0.0,
            "margin_trading_balance":0,
            "short_selling_balance":0,
            "update_date":"2025/10/31",
            "category":"00",
            "day_trade":"2",
            "name":"元大台灣50",
            "target_code":""
        },
        "order":{
            "action":"Buy",
            "price":60.0,
            "quantity":3,
            "price_type":"LMT",
            "order_type":"ROD",
            "order_lot":"Common",
            "order_cond":"Cash",
            "daytrade_short":0,
            "id":"",
            "seqno":"484614",
            "ordno":"CL561",
            "account":"<your-account_msg>",
            "custom_field":"Test",
            "ca":"..."
        },
        "status":{
            "id":"",
            "status":"Submitted",
            "status_code":"00",
            "order_datetime":"20251031100509",
            "msg":"已處理 9802243 的 0050，價格為 60.0，數量為 3 (整張)",
            "modified_ts":0.0,
            "modified_price":0.0,
            "order_quantity":3000,
            "cancel_quantity":0,
            "act":0,
            "deals":null
        }
    }
    ```

### 改單

#### 改價

!!! Example "改價"

    ```C#
    var updatedTrade = pocketx.UpdateOrder(trade, price: 51.0, quantity: 0);
    ```

!!! Note 

    零股不得改價

!!! Success "output"

    ```json
    {
        "contract":{
            "security_type":"STK",
            "code":"0050",
            "symbol":"TSE0050",
            "exchange":"TSE",
            "limit_up":70.8,
            "limit_down":58.0,
            "reference":0.0,
            "margin_trading_balance":0,
            "short_selling_balance":0,
            "update_date":"2025/10/31",
            "category":"00",
            "day_trade":"2",
            "name":"元大台灣50",
            "target_code":""
        },
        "order":{
            "action":"Buy",
            "price":60.0,
            "quantity":3,
            "price_type":"LMT",
            "order_type":"ROD",
            "order_lot":"Common",
            "order_cond":"Cash",
            "daytrade_short":"",
            "id":"",
            "seqno":"484614",
            "ordno":"CL561",
            "account":"<your-account-info>",
            "custom_field":"Test",
            "ca":"..."
            },
        "status":{
            "id":"",
            "status":"Submitted",
            "status_code":"00",
            "order_datetime":"20251031100509",
            "msg":"已處理 9802243 的 0050，價格為 60.0，數量為 3 (整張)",
            "modified_ts":0.0,
            "modified_price":0.0,
            "order_quantity":3000,
            "cancel_quantity":0,
            "act":0,
            "deals":null
        }
    }
    ```

#### 改量(減量)

UpdateOrder 只能用來減少原委託單的委託數量。

!!! Example "改量"

    ```C#
    var updatedTrade2 = pocketx.UpdateOrder(trade, price: 0, quantity: 2);
    ```

### 刪單

!!! Example "Input"

    ```C#
    var updatedTrade2 = pocketx.UpdateOrder(trade, price: 0, quantity: 2);
    ```
