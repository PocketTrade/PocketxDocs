## 商品檔

商品檔將在很多地方被使用，例如下單、訂閱行情...等。

### 取得商品檔
當登入成功後，會開始下載商品檔。

### 商品檔資訊

目前我們所提供的商品只有證券 (未來會提供更多交易商品)。可從下列方法更詳細得到我們所提供的商品。

!!! Example "Input"

    ```c#
    using PocketxSDK;

    var pocketx = new Pocketx();
    var contract = pocketx.Contracts;
    Console.WriteLine(_contract);
    ```

!!! Success "Output"

    ```json
    {
        "Indexs":{},"Stocks":{"OTC":{"006201":{"security_type":"STK","code":"006201","symbol":"OTC006201","exchange":"OTC","limit_up":26.57,"limit_down":21.75,"reference":0.0,"margin_trading_balance":0,"short_selling_balance":0,"update_date":"2024/07/19","category":"00","day_trade":2,"name":"元大富櫃50","target_code":""}, .... }}
    }
    ```


#### 證券

!!! Example "Input"

    ```c#
    var contract_0050 = _api.Contracts.Stocks["TSE"]["0050"];
    Console.WriteLine(contract_0050.ToString());
    ```

!!! Success "Out:"

    ```json
    {
        "security_type":"STK",
        "code":"0050",
        "symbol":"TSE0050",
        "exchange":"TSE",
        "limit_up":209.65,
        "limit_down":171.55,
        "reference":0.0,
        "margin_trading_balance":0,
        "short_selling_balance":0,
        "update_date":"2024/07/19",
        "day_trade":2,
        "category":"00",
        "name":"元大台灣50",
        "target_code":"",
    }
    ```

!!! Info "Attribute"

    ```
    code (str): 商品代碼
    symbol (str): 符號
    exchange (Exchange): 交易所 {OES, OTC, TSE ...等}
    limit_up (float): 漲停價
    limit_down (float): 跌停價
    name (str): 商品名稱
    reference (float): 參考價
    margin_trading_balance (int): 融資餘額
    short_selling_balance (int): 融券餘額
    update_date (str): 更新日期
    day_trade (DayTrade): 可否當沖 {Yes, No, OnlyBuy}
    category (str): 類別
    name (str): 名稱
    ```
