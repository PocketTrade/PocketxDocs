

### 登入啟用並憑證

!!! example "Input"

    ```C#
    using PocketxSDK;

    var pocketx = new Pocketx();
    var _accounts = pocketx.Login("YOUR_API_KEY", "YOUR_SECRET_KEY");
    var flag = pocketx.ca_activate("<你的pfx路徑>", "<你的 personal_id>", "<你的 personal_id>");
    Console.WriteLine(_accounts);
    ```

### 下單


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