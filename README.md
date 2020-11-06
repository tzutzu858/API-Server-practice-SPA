# API-Server-practice-SPA
## 後端製作API，前端串 API<br>
https://tzutzu858.github.io/API-Server-practice-SPA/<br>
原本以為 github 上只能放靜態網頁，不過如果用 AJAX 拿資料，這樣 github 上也算可以放動態網站<br>
但如果把後端 API 放在伺服器，那幹嘛前端網頁不一起放在伺服器，大概是前端還沒修改完，放在這也可以做個版控吧 <br>
**********
## 目前錯誤
想說怎麼成功請求後幾秒後又失敗<br>
報錯 : This request has been blocked; the content must be served over HTTPS.<br>
查資料是說 https 網站內不可以傳送 http 請求，並且 http 請求直接被攔截並不傳送到後臺伺服器<br>
所以目前在這邊無法送請求是掛掉狀態<br>

先存一下找到的文章，因為自己 GCP 和 AWS 都有申請主機，是也有點想乾脆前端網頁放伺服器就好不要放在 github 這，就不需要設定 HTTPS 的問題，但想想也許會和別人協作，製作 API 讓別人串，好像還是要把 HTTPS 這個坑補起來<br>
<br>
## 參考文章 : 
1. [[教學] Google Cloud Storage 安裝SSL憑證，讓網站也有綠色鎖頭](https://www.minwt.com/website/server/21585.html)<br>
2. [AlwaysOnSSL 免費 SSL 憑證服務，自助驗證開啟 HTTPS 加密功能](https://free.com.tw/alwaysonssl/)一年免費，反正 AWS 主機也是一年免費，GCP 那邊現在我設定的主機不確定會不會算錢<br>
3. [關於AWS-EC2-設定HTTPS](https://medium.com/@justinlee_78563/%E9%97%9C%E6%96%BCaws-ec2-%E8%A8%AD%E5%AE%9Ahttps-17c95bc30d4e)<br>

## API
https://tzutzu858.tw/json/api_comments.php : 列出所有留言 API<br>
拿資料的時候 query string 帶上 site_key 也可以多帶上 before 來查看 before 前五筆資料<br>
資料結構：<br>
```
{
    "id": 1,
    "nickname": "tzu",
    "content": "tzu",
    "created_at": "2020-11-02 22:48:32"
}
```

<br>
<br>

https://tzutzu858.tw/json/api_add_comments.php : 新增留言 API<br>
POST 帶上 site_key、nickname、content。<br>
資料結構：<br>

```
{
    "ok": true,
    "discussions": [
        {
            "id": 1,
            "nickname": "小明",
            "content": "我來留言啦",
            "created_at": "2020-11-04 23:20:36"
        }
    ]
}
```
<br>
<br>
簡易留言板<br>
<img src="https://i.imgur.com/Y6AkVVn.png" width="400" ><br>
