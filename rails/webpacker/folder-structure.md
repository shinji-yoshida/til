entry point が
``` js
// app/javascript/packs/calendar.js

import 'calendar'
```
のようになっていて、 calendar をインポートした時、インポートされるファイルは

```
app/javascript/calendar/index.js
```
である。ただし、これは `config/webpacker.yml` で設定できる。
