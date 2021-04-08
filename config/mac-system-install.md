# 重新安装mac系统

## 主题
重装mac系统时，需要软件及需配置的环境变量。

### 题记
这次重装mac系统，真的把人整惨了，之前的环境变量，都需要重新装载一遍，光是查，就查了很久。<br/>
现在把主要步骤记录，方便下一次处理。

### 安装软件

1.搜狗。<br/>
2.brew。<br/>

```
brew 是一个mac的包管理工具，很有必要安装。
按照官网安装很费流量，如果安装不成功，可以先安装：
xcode-select --install
然后继续安装brew.
brew 安装的好处很多，可以用来安装，ruby，git等。
虽然系统本身就安装了ruby，git但是还是需要使用brew安装，这样不会破坏系统
的软件，并且易于维护。
```
3.iterm.

```
命令输入。
配置：iterm -> preference
->general.
去掉closing 中，2个confirm ...
->appearance.
tab bar location: top, theme: dark.
hide srollbars. 选中
->profiles->window.
transparency: 调节透明度。
rows： 调节输入框高度。
style: full-width top of screen.
screen: screen with cursor.
space: current space.
end.
配置完成后，重启命令行。
```

4.zsh,oh my zsh.

```
zsh: 使用brew安装。
将zsh 目录，举例为：/usr/local/Cellar/zsh/5.5.1/bin/zsh-5.5.1
放置到/etc/shells 文件中。(使用 sudo vi shells)
然后运行切换shell命令：
chsh -s /usr/local/Cellar/zsh/5.5.1/bin/zsh-5.5.1
重启命令行输入框。
test:
输入：echo $SHELL
显示：/usr/local/Cellar/zsh/5.5.1/bin/zsh-5.5.1(安装的zsh目录)
输入：which zsh
显示：/usr/local/bin/zsh (这是因为用brew安装默认软链接显示在这里)
```

```
oh my zsh: 官网安装方法。
```

5.vscode.

6.ruby,git. 使用brew安装。

7.evernote.

8.设置git代理,加快提交代码速度。

```
// 走 HTTP 代理
git config --global http.proxy "http://127.0.0.1:8080"
git config --global https.proxy "http://127.0.0.1:8080"
// 走 socks5 代理（如 Shadowsocks）
git config --global http.proxy "socks5://127.0.0.1:1080"
git config --global https.proxy "socks5://127.0.0.1:1080"
// 取消设置
git config --global --unset http.proxy
git config --global --unset https.proxy

// ssh形式
// 修改 ~/.ssh/config 文件（不存在则新建）
# 必须是 github.com
Host github.com
   HostName github.com
   User git
   # 走 HTTP 代理
   # ProxyCommand socat - PROXY:127.0.0.1:%h:%p,proxyport=8080
   # 走 socks5 代理（如 Shadowsocks）
   # ProxyCommand nc -v -x 127.0.0.1:1080 %h %p

```

