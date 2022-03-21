# 初探網路爬蟲
#### 我們要了解網站的內容才能夠進行爬蟲，但是不知道原始碼在寫什麼怎麼辦?接下來我們以氣象局觀測資料網站來做練習! <br> ->[[點擊前往氣象局觀測資料網站]](https://e-service.cwb.gov.tw/HistoryDataQuery/index.jsp)

<p><br></p>

 ## 實際練習 part1
> ### 1.我們選取中壢地區(C0C700_中壢)，2022年3月的雨量資訊進行查詢。<br>2.我們先來解讀網址的內容以便之後利用。
> 
<p><br></p>

``` 
網站網址:https://e-service.cwb.gov.tw/HistoryDataQuery/MonthDataController.do?command=viewMain&station=C0C700&stname=%25E4%25B8%25AD%25E5%25A3%25A2&datepicker=2022-03&altitude=151.0m 

1. https://e-service.cwb.gov.tw/HistoryDataQuery/MonthDataController.do 原始的網址/歷史查詢/月份查詢
2.'?'為斷句:分開前後區塊，&為分隔:分開個別參數
3. command=viewMain&station=C0C700
```
<p><br></p>

> ### 3.利用檢查功能，查看氣象局網站原始碼與網站的關聯。
<p align="center"><img src="https://raw.githubusercontent.com/luoyan109/web-crawler/main/image/%E6%AA%A2%E6%9F%A5.PNG" width=750px></p>

