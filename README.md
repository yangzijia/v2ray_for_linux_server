因为不熟悉v2ray配置方法，这里直接使用windows上的配置文件，直接copy到linux服务器上进行使用的方法。

## 一、安装配置windows v2rayN服务
### 1.下载:[客户端](https://download.csdn.net/download/qq_20265187/88571581)
下载安装后从桌面打开
或在目录中打开 v2rayN.exe
![在这里插入图片描述](https://img-blog.csdnimg.cn/bd1f74adb95848f79ecd968683bef561.png)

### 2. 设置订阅地址
 
一键复制V2ray或V2Ray-VLESS节点订阅到V2rayN
这里需要使用代理

点击 订阅设置 填入备注信息，把订阅信息黏贴到地址（ulr）
点击更新订阅可以得到节点信息，剩余流量与过期时间
如果弹出配置错误提示，请重启客户端并重新操作一遍
![请添加图片描述](https://img-blog.csdnimg.cn/57e63dbf9cf74c0bb2f5d32d69277c88.png)

### 3. 选择节点

系统托盘找到图标，鼠标右击 点击服务器
根据规则链路选择相应的节点
![请添加图片描述](https://img-blog.csdnimg.cn/db1ce3c92cd84a889a62af950631792b.png)

### 4. 开启代理

点击 系统代理 选项自动配置系统代理
打开 路由 选择全局；其他保持默认即可。
可以起飞了~~~

![请添加图片描述](https://img-blog.csdnimg.cn/a43cac4a8a0743929a269342d14e198c.png)
### 5. 寻找配置文件
找到`zz_v2rayN-With-Core-SelfContained\guiConfigs` 下的`config.json`备用，一会上传到linux server上
## 二、下载linux v2ray
从[这里](https://github.com/v2fly/v2ray-core/releases/download/v5.12.1/v2ray-linux-64.zip)下载v2ray-linux-64.zip
上传到linux服务器上，解压缩
将刚才准备的config.json覆盖掉v2ray目录下的config.json，然后通过下面的命令启动服务（使用nohup创建了一个后台进程）
```shell
# 将后台日志输出到 v2ray_run.log
nohup v2ray run -config config.json > v2ray_run.log 2>&1 &

# 什么也不输出
nohup v2ray run -config config.json >/dev/null 2>&1 &
```
