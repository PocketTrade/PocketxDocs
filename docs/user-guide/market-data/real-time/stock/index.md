# 證券

目前尚未提供此功能 ！！！

<!-- 
透過[商品檔]()，來訂閱行情

## Tick (一般股票)

### 整股

!!! Example "Input"

    ```C#
    pocketx.Subscribe(contract, quoteType: QuoteType.tick, intradayOdd: false, version: QuoteVersion.v0);
    ```

!!! Success "Output"

    ```
    [2025-10-31 11:20:51][INF][QUOTE] {"code":"0","action":"Common_Tick","version":"v0","quote_time":112051796779,"response":{"data":{"Code":"TWSE:0050","AmountSum":0.0,"Close":64.6,"Date":"2025/10/31","TickType":0,"Time":"11:20:51.796779","VolSum":32150,"Volume":1},"msg":""}
    ```

### 盤中零股

!!! Example "Input"

    ```C#
    var contract = pocketx.Contracts.Stocks["TSE"]["0050"];
    pocketx.Subscribe(contract, quoteType: QuoteType.tick, intradayOdd: true, version: QuoteVersion.v0);
    ```
    
!!! Success "Output"

    ```
    [2025-10-31 11:08:46][INF][SYSTEM] Connecting to QuoteServiceWebsocket...
    [2025-10-31 11:08:46][INF][SYSTEM] Connected to QuoteServiceWebsocket Successfully !!!
    ```

## BidAsk (五檔)
### 整股
目前尚未支持

### 盤中零股
目前尚未支持

## Quote ()
目前尚未支持

## Callback
用來在即時行情觸發時，進行操作。

### Set Quote Callback
!!! Example "In:"

    ```C#
    private static void myQuoteCB(Exchange exchange, dynamic quote)
    {
        Console.WriteLine($"Symbal: {quote.Code}");

        Console.WriteLine($"QuoteCB | Exchange.{exchange} {quote.GetType().Name} {quote}");
    }

    pocketx.SetQuoteCallback(myQuoteCB);
    ``` -->