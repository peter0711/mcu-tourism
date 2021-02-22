Linebot-Demo-AccountBook
===

此Line bot範例為使用 LineBotSDK 建立的 <br>
電子記帳本 <br>
用戶可以跟 bot 說 <br>
-------------------- <br>
87 </B><br>
或 <br>
87 麥當勞 <br>
-------------------- <br>
bot就會將此筆消費紀錄儲存起來 <br>
用戶也可以說 『/month』 或 『/today』 取得本月或今天的消費金額小記 <br>

使用畫面
===
 ![](https://i.imgur.com/JG97Yml.png)

測試 - 想要試玩看看?
===
您可以用LINE 搜尋 @lep6424e 將其加入好友即可測試 <br>
或掃描QR Code <br>
![](https://i.imgur.com/sEMbP4J.png)

如何佈署專案
===
* 請 clone 之後，修改 web.config 中的 ChannelAccessToken
```xml
  <appSettings>
    <add key="ChannelAccessToken" value="請改成你自己的channel access token"/>
  </appSettings>
```
* 為了便於除錯，請修改 LineAccountBookController.cs 中的 Admin User Id
```csharp
   catch (Exception ex)
            {
                //回覆訊息
                this.PushMessage("請改成你自己的Admin User Id", "發生錯誤:\n" + ex.Message);
                //response OK
                return Ok();
            }
```
* 建議使用Ngrok進行測試 <br/>
(可參考 https://youtu.be/kCga1_E-ijs ) 
* LINE Bot後台的WebHook設定，其位置為 Http://你的domain/api/LineAccountBook

資料庫
===
* 為了符合最低開發需求，此範例資料庫採用 SQL Express (已commit進去專案中) 以及 LinqToSql
* 開發環境需要安裝 SQL Express, 若要佈署至 Azure Web Site (或自行搭建的IIS)，需要自行改為使用Azure SQL DB
* 如果你的Visual Studio沒有安裝LinqToSQL，可以參考底下的畫面進行調整:
 ![](https://i.imgur.com/ew6acqd.png)
 
注意事項
===
由於這只是一個範例，我們盡可能用最簡單的方式來開發。 <br/>
範例中記錄狀態的方式採用了Application[]變數，但實務上建議您調整成資料庫或其他storage。

線上課程 與 電子書 
===
LineBotSDK線上教學課程: <br/>
https://www.udemy.com/line-bot <br/>
 <br/>
電子書購買位置(包含範例完整說明): <br/>
https://www.pubu.com.tw/ebook/103305 <br/>

