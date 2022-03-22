# 初探網路爬蟲---原始碼中的奧妙
### 首先，需要了解網站的內容才能夠進行爬蟲，而從網站的原始碼可以得知內部訊息。<br>那麼接下來就先以氣象觀測資料網站來做練習! <br>  <br>->[[點擊前往氣象局觀測資料網站]](https://e-service.cwb.gov.tw/HistoryDataQuery/index.jsp)

<p><br></p>

 # 實際練習 part1
> ### 1.我們選取中壢地區(C0C700_中壢)，2022年3月的雨量月報表進行查詢。<br>2.再來解讀網址(URL)的內容以便之後利用。

<p><br></p>

``` 
網址:https://e-service.cwb.gov.tw/HistoryDataQuery/MonthDataController.do?command=viewMain&station=C0C700&stname=%25E4%25B8%25AD%25E5%25A3%25A2&datepicker=2022-03&altitude=151.0m 

URL解讀:
1. https://e-service.cwb.gov.tw/HistoryDataQuery/MonthDataController.do 協議/存放資料位置/歷史查詢/月份查詢
2. '?'為分隔:分開前後區塊，後方為引數開頭，'&'為引數連線:將後方各個引數連接起來
3. command=viewMain&station=C0C700 :查看測站編號C0C700
4. stname=%25E4%25B8%25AD%25E5%25A3%25A2 :測站名稱=encodeURI("中壢")
5. datepicker=2022-03 :時間查詢範圍 ，altitude=151.0m :海拔高度151.0m
```
### 補充:[URL字串解碼網站](https://youtils.cc/urldecoder/zh-Hants)
+ encode:編碼 / decode:解碼 
+ 我們以上述網址為例: %25E4%25B8%25AD%25E5%25A3%25A2 
+ 進行decode解碼一次: %E4%B8%AD%E5%A3%A2
+ 進行decode解碼兩次: 中壢

<p><br></p>

> ### 3.利用檢查功能，查看氣象局網站原始碼與網站的關聯。
> #### + 對網頁按下滑鼠右鍵選擇"檢查"，可以呼叫出網頁檢查面板。
> #### + 如果想要取得完整原始碼，以對網頁按下滑鼠右鍵，選取"檢視網站原始碼"即可。

<p> <br></p>

<p align="center"><img src="https://raw.githubusercontent.com/luoyan109/web-crawler/main/image/%E6%AA%A2%E6%9F%A5.PNG" width=750px><br>^上圖為檢查介面的模樣(畫面右邊)</p>


<p> <br></p>

### 補充:檢查功能介紹
+ 選取網頁元素:可以選擇一個想要檢視的區塊，這樣就可以清楚知道單一區塊的程式碼內容
+ 
<p align="center"><img src="https://raw.githubusercontent.com/luoyan109/web-crawler/main/image/15.PNG" width=750px></p>

