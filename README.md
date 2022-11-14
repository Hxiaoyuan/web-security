# web-security
web安全大作业

# 程序运行
1. npm install 
2. node app.js | node click-hijack.js

## 点击劫持
1. 运行node app.js
2. 浏览器打开 http://localhost:3003/index.html,
3. 看到有很多投票按钮，可以任意投票
4. 现在再开一个命令行工具 运行 node app2.js
5. 浏览器打开 http://localhost:3004/attack.html，这时界面看到一个按钮，当你点击这个按钮的时候，实际上是给hgf投票了

## 防御
1. 打开 app.js
2. 添加res.setHeader('X-FRAME-OPTIONS','DENY')
3. 此时再浏览器打开 http://localhost:3004/attack.html，发现index.html并没有加载出来。

**（X-Frame-Options设置为DENY，表示当前页面不允许在frame中加载展示，以防止被劫持）**