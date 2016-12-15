##说明

forked  from https://github.com/ring04h/wyportmap

删除了数据库功能，便于日常调用

## wyportmap
目标端口扫描+协议识别

运行流程
-----------------------------------
* 为wyportmap指定扫描目标
* 调用nmap启动后台扫描任务
* NmapParser处理扫描结果
* 后台插件自动分析扫描结果

使用说明
-----------------------------------
    要先安装git & nmap(v6以上版本) 
    
#### 下载wyportmap项目
    git clone https://github.com/ring04h/wyportmap.git
    
#### 命令行使用
    usage: wyportmap.py targets taskid
    
    告诉wyportmap.py你的扫描目标，扫描结果如下
    python wyportmap.py 42.62.78.70-100
    
