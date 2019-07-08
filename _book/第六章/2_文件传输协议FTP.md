
### 文件传输协议FTP
```
TCP控制连接：用来告诉FTP服务器是下载，上传，删除, 端口为21
TCP数据连接：
    主动模式：FTP服务器从20端口主动向客户端发起连接
    被动模式(默认): FTP服务器打开一个端口被动的等待客户端发起连接

FTP服务器端如果有防火墙, 需要在防火墙开启20和21端口, 通信使用主动模式进行数据连接
win10系统FTP服务器架设:
    <1> 控制面板 => 程序 => 启动或关闭windows功能 => Intenet Information Service
         => 选中FTP服务器以及Web管理工具中的ISS管理控制台
    <2> 开始 => windows管理工具 => Intenet Information Service => 左边找到网站右键添加FTP站点
    <3> window防火墙 => 允许应用通过防火墙 => 选中FTP服务器 => 允许其他应用 
        => C:\Windows\System32\svchost  
    <4> 此时客户端即可连接, 如果客户端选择了FTP主动模式(IE浏览器=>Intenet选项=>高级=>不勾选被动FTP),
        那么客户端在连接FTP时会弹出防火墙已经阻止资源管理器打开FTP的功能(即用文件夹的方式打开不了), 
        此时应该选择允许, 如果忘记选了是登陆不上的, 需要在防火墙的允许应用通过中勾选Windows资源管理器

命令行添加用户和密码/修改密码: net user 用户名 密码 [/add]
将用户加入管理员组: net localgroup administrators 用户 /add
```