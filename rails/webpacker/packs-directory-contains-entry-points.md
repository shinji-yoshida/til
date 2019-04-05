app/javascript/packs 以下にエントリポイントを配置する。

`app/javascript/packs/application.js` のようなファイルが有るならば、
```
<%= javascript_pack_tag 'application' %>
```
このようにエントリポイントを利用できる。

`app/javascript/packs/foo/bar.js` ならば、 `<%= javascript_pack_tag 'foo/bar' %>` となる。

