# 查詢狀態

!!! Warning "提醒"

先執行 UpdateStatus 取得最新 Trade 狀態。
若刪單／改單失敗，請重新更新該 Trade 物件，並檢查 OrderStatus 是否為可取消或可修改的狀態。

## 取得證券委託狀態

!!! Example "Input"

    ```C#
    pocketx.UpdateStatus(account, trade);
    pocketx.ListTrades();
    ```

!!! Success "Output"

    ```C#
    
    ```