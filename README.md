# Bililiveauto

兼容[B站录播姬](https://github.com/BililiveRecorder/BililiveRecorder)的开播自动提醒脚本

## 下载

```bash
git clone https://github.com/ZYGLQexplorer/Bililiveauto
```

## 配置

此脚本使用.env文件作为配置文件，模板如下：
```yaml
# .env

#run
port=8081
#Telegram
TG_CHAT_ID=12345678 # Telegram ID
TG_TOKEN=9876543:abcdeffhijklmnopqrstuvwxyz # Telegram Bot Token
```

### 通知

本脚本使用Telegram来通知，只需要向[@userinfobot](https://t.me/userinfobot)发送任意消息即可得到Telegram ID; 向[@BotFather](https://t.me/BotFather)申请Bot获得Bot Token

最后将两者填入配置文件即可

当然要记得私聊一下你的bot

## 运行

运行本脚本需要先安装nodejs 

建议使用nvm脚本快速安装

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
nvm install --lts
```
然后在此脚本目录运行`node server.js`即可

### pm2持久化运行

安装pm2

```bash
npm install pm2 -g
```

运行bililiveauto

```bash
pm2 start server.js --name bililiveauto
```

配置pm2开机自启
root用户全自动，非root用户请执行命令后根据提示复制命令执行
```bash
pm2 startup
```

储存当前服务列表并加入自启
```bash
pm2 save
```

此致，你的bililiveauto将自动在后台运行并在重启时自启。可使用`pm2 status`查看服务状态，`pm2 logs bililiveauto`查看日志，`pm2 monit`打开状态监视器。

## 最后一步

在录播姬的设置里, 将地址填入"webhook v2"即可, 如"http://127.0.0.1:8081"

# 鸣谢
[原项目 Morax-xyc/Bililiveauto](https://github.com/Morax-xyc/Bililiveauto)

[Bilibili直播](https://live.bilibili.com)

[B站录播姬](https://github.com/BililiveRecorder/BililiveRecorder)
