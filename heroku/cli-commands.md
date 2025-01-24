show version
```bash
heroku --version
```
show all apps
```bash
heroku list -A
```
run command
```bash
heroku run -a [app name] [command]
```
一時間以上 I/O が無い場合 KILL されるので、それを防ぎたい場合は detached で run する
```bash
heroku run:detached -a [app name] [command]
```
