1. 在IIS上为站点 http://servername 配置了SSL证书后，假设站点可以通过 https://servername.domain 来访问，
但带来的问题是：站点默认仍可以通过 http://servername 访问；在浏览器中输入 http://servername.domain 或 servername.domain，
浏览器无法直接被定向到https的URI上去。要解决这两点，首先，把站点Binding上的80端口的http绑定移除掉；
第二，查看 servername.domain 或 http://servername.domain 默认定向到的站点（比如IIS上还安装了Sharepoint，那这将指向Sharepoint的默认地址），
在那个站点上（如果没有这样的站点，那应该在根结点上）创建URL Rewrite规则
（需要在[这里](https://www.iis.net/downloads/microsoft/url-rewrite)下载相应的组件)，规则配置中的重点有：Match URL为*，Action Type为Redirect，
Action中的Redirect URL为https://{HTTP_HOST}{REQUEST_URI}，Redirect type为302。
