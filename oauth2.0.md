
RFC 6749 - 定義與 Token 核發相關 Protocol 

RFC 6750 - 定義 Bearer Token 使用方式

### Resource Owner ( User )
- 資料擁有者 ( 你是擁有FB上關於自己的所有照片跟動態資料的人 )

### Client ( App ) 
- 欲存取資料的第三方程式 ( 某一個 App 想要存取關於你在FB上所有的照片 )
- 開發者必須先註冊
 * Client ID
 * Client Secret
 * Redirect URI

### Authorization Server 
- 負責管理授權的伺服器

- Access Token
 * 向 Resource Server 要資料
 * 可以綁定 Scope
 * 設定期限

- Refresh Token
 * 換發 Access Token 時使用，只會傳到 Auth.Server
 * 綁定一個 Access Token，跟 Access Token 一起核發
 * 使用過即失效

- State
 * 防止 CSRF 攻擊
 * State 傳到 Auth.Server 就要原封不動回傳，Client 驗證
 * 亂碼

### Resource Server 
- Client要存取資料的伺服器 ( FB上提供一個關於存取照片的API )
- Client 要有 Token 才能取得資料
- 可以用 Scope 限制 Token 能夠存取的資料範圍
- Password-Free API


### Endpoints
- Authorization Endpoint 
 * 一個網頁讓 User 本人授權
 * 拿回一個授權狀 ( Grant ) 而不是 Token
 * User 授權完，會導回 Client 的 RedirectURI

- Token Endpoint 
 * 一個讓 Client 取得 Token 的 API

- Redirection Endpoint
 * Client取得資料
 * 從瀏覽器接收 Auth.Server 的資料
 * 在 Client 執行
 * Auth.Server 會驗證 RedirectURI是否與當初申請時一樣才會轉址

