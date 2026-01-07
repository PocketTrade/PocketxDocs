## Login

登入必須擁有口袋帳戶。若你還沒有擁口袋帳戶，可詳見 [口袋開戶](https://www.pocket.tw/openaccountonline/oa/home?mkCode=MK0000&channel=CH0003&utm_source=pocketw&openExternalBrowser=1&showYuShanBtn=Y)

!!! example "Input"

    ```C#
    using PocketxSDK;

    var pocketx = new Pocketx();
    var _accounts = pocketx.Login("YOUR_API_KEY", "YOUR_SECRET_KEY");
    var flag = pocketx.ca_activate("<你的pfx路徑>", "<你的 personal_id>", "<你的 personal_id>");
    Console.WriteLine(_accounts);
    ```

!!! Success "Output"

    ```
    [2025-xx-xx 13:59:21][INF][SYSTEM] Welcome to Pocketx!!!
    [2025-xx-xx 13:59:21][INF][SYSTEM] Login...
    [2025-xx-xx 13:59:22][INF][SYSTEM] Connecting to PulsarService...
    [2025-xx-xx 13:59:22][INF][SYSTEM] Connected to PulsarService Successfully !!!
    ```


### List Accounts

有兩種方式可以獲得你的帳戶資訊

!!! example "Input"

    ```c#
    using PocketxSDK;

    var pocketx = new Pocketx();
    var _accounts = pocketx.Login("YOUR_API_KEY", "YOUR_SECRET_KEY");
    Console.WriteLine($"_accounts: {_accounts}");
    ```

!!! example "Input"

    ```C#
    using PocketxSDK;

    var pocketx = new Pocketx();
    var listAccounts = ListAccounts(pocketx);
    Console.WriteLine(listAccounts);
    ```

!!! Success "Output"

    ```
    listAccounts: [
        {"account_type":"...","person_id":"...","broker_id":"...","account_id":"...","signed":true,"username":"..."}
    ]
    ```

### Logout

!!! example "Input"

    ```C#
    using PocketxSDK;

    var pocketx = new Pocketx();
    var res = _api.Logout();
    Console.WriteLine(res); 
    ```
