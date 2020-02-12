### 中国地区访问 GitHub 为什么很慢？
>Q：为什么访问速度会很慢？

A：GitHub 的CDN域名遭到DNS污染。GitHub 在中国大陆访问速度慢的问题原因有很多，但最直接和最主要的原因是 GitHub 的分发加速网络的域名遭到 DNS 污染。由于 GitHub 的加速分发 CDN 域名 assets-cdn.github.com 遭到 DNS 污染，导致无法连接使用 GitHub 的加速分发服务器，才使得中国大陆访问速度很慢。

>Q：如何解决 DNS 污染？

A：通过修改 Hosts 解决污染问题。一般的 DNS 问题都可以通过修改 Hosts 文件来解决，GitHub 的 CDN 域名被污染问题也不例外，同样可以通过修改 Hosts 文件解决。将域名解析直接指向 IP 地址来绕过 DNS 的解析，以此解决污染问题。

### 如何加速访问GitHub？
>1、打开IPAddress.com网站，查询下面 3 个网址对应的 IP 地址
```
github.com
assets-cdn.github.com
global.ssl.fastly.net
```

>2、修改本地电脑系统 hosts 文件（PS：路径一般都是 C:\Windows\System32\drivers\etc），直接在最后加入查询的dns节点
```
# GitHub访问加速节点
140.82.113.4 github.com
151.101.184.133 assets-cdn.github.com
185.199.108.153 assets-cdn.github.com
185.199.109.153 assets-cdn.github.com
185.199.110.153 assets-cdn.github.com
185.199.111.153 assets-cdn.github.com
199.232.5.194 github.global.ssl.fastly.net
```

![](https://github.com/sj13271473920/picture/blob/mater//20200212162509.png?raw=true)
![](https://github.com/sj13271473920/picture/blob/mater//20200212162625.png?raw=true)
![](https://github.com/sj13271473920/picture/blob/mater//20200212162724.png?raw=true)

> 4、用“WIN +Ｒ”快捷键打开运行窗口，输入命令：cmd 并回车进入命令行窗口，接着输入命令：ipconfig /flushdns 回车后执行刷新本地 DNS 缓存数据即可。
