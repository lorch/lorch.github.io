# 初涉GoLang之编程环境篇

标签（空格分隔）： 环境配置

---
工欲善其事，必先利其器。所以Golang部署，是我的第一篇纪录.
> 部署环境：sublime2 ＋ mac

## 下载Golang并安装

- golang下载地址：[戳我，我是地址君](http://golang.org/doc/install)
- 选择对应的版本，这里我选的是：`go1.4.2.darwin-amd64-osx10.8.pkg`
- 双击下载包，安装

## 部署GoLang环境变量
在mac中，打开iTerm输入 `vim ./bash_profig`，添加如下路径：
```bash
⚠ 这是mac默认安装的所选择的路径，其他系统按照不同的安装路径,将GOROOT设置为不同值*
export GOROOT=/usr/local/Cellar/go/1.4/libexec/
export GOBIN=$GOROOT/bin
⚠ GOPATH有点儿特殊，是一个工作空间，一般一个GoLang应用有一个工作空间，多个路径之间的用:[mac,linux]连接[windows用; 这个跟path环境变量的多个链接相同]。 
export GOPATH=/Users/YourGoPath
export PATH=$PATH:$GOBIN:$GOPATH
```
现在，在iTerm输入 go version, 应该可以看到Go的版本号的输出了。

## 配置sublime2上的Golang编写环境
可以编译Go的编辑器有很多，IiteIDE， Goclipse，Vim， Emacs之类的都行，万能的Vim配好了其实也很好用，是大神利器。此外，个人感觉安装最便利的是Goclipse，使用最便利的是IiteIDE，毕竟这个是专为GoLang设计的忠犬，Emacs没有用过，据说是个大杀器。
但是这里我选择了sublime。原谅我是一个可耻的外卖协会，sublime的界面让我在写代码的时候感觉非常舒服，而且支持语法高亮，有点儿简陋的语义提示，此外，在保存的时候会自动矫正错误格式。
sublime几乎可以算得上的免费。试用无时间限制，但是时不时会提示你购买，偶尔会觉得这一点儿非常烦，可以找下破解，kill掉这个。

闲话到此，这里提供下sublime的官方下载地址：[戳我，我是地址君](http://www.sublimetext.com/2)

- 选择合适自己的版本，双击安装。
- 打开sublime，安装GoSubLime插件
> * 按下`command＋shift＋p` [window用`ctrl＋shift＋p`]
> * 输入`install`, 选择`install package`回车
> * 在跳出的输入框中输入`GoSublime`, 选择`GoSublime`回车
> * 输入`Go build`选中回车（这个属于可选）

- 下载GoCode，在iTerm中输入：
```bash
go get -u github.com/nsf/gocode
go install github.com/nsf/gocode
```

- 修改sublime配置，选择菜单Preferences -> Package Settings -> Package Controll -> Settings-User。打开文件，配置如下：
```json
{
	"in_process_packages":
	[
	],
	"installed_packages":
	[
		"Go Build",
		"GoSublime",
		"Package Control"
	]
}
```

重启之后，尝试编辑Go吧

⚠ 代码编写完成后，可以按command＋b呼出命令行
