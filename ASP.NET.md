1. 运行`C:\Windows\Microsoft.NET\Framework\<version>\aspnet_regsql.exe`创建一系列微软官方推荐的用户管理的数据库表。   
2. `C:\Windows\Microsoft.NET\Framework\<version>\Config\machine.config`保存了本机所有的.net程序的默认配置参数。
3. 新建一个MVC项目，当选择了“Windows Authentication”时，项目做了什么？项目在Web.config文件的system.web节点下插入了authentication节点，其mode属性的值被设置为了windows，另外，默认情况下，项目将使用IISExpress来运行和调试，项目的csproj文件中存在一个节点IISExpressWindowsAuthentication，它的值被设置为了enabled，而IISExpressAnonymousAuthentication的值为设置为了disabled。
4. `C:\Program Files(x86)\Microsoft SDKs\Windows\v8.1A\bin\NETFX 4.5.1 Tools\下的clrver.exe`可以用于查看本机已安装的CLR版本。加上-all参数用于查看正在运行于CLR上的所有进程。 - 读《CLR Via C# 4th Edition》
