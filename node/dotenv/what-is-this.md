.env ファイルから設定を読み込んでくれる。
``` js
require('dotenv').config()

const db = require('db')
db.connect({
  host: process.env.DB_HOST,
  username: process.env.DB_USER,
  password: process.env.DB_PASS
})
```
