# API-Server-practice-SPA
## 後端製作API，前端串 API<br>
https://tzutzu858.github.io/API-Server-practice-SPA/<br>
原本以為 github 上只能放靜態網頁，不過如果用 AJAX 拿資料，這樣 github 上也算可以放動態網站<br>
但如果把後端 API 放在伺服器，那幹嘛前端網頁不一起放在伺服器，大概是前端還沒修改完，放在這也可以做個版控吧 <br>
**********

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


## 之前錯誤
錯誤 : 無法請求，沒有動態跑資料出來<br>
報錯 : This request has been blocked; the content must be served over HTTPS.<br>
查資料是說 https 網站內不可以傳送 http 請求，並且 http 請求直接被攔截並不傳送到後臺伺服器<br>
修正 : 主機那設定 HTTPS
