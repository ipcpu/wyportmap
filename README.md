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
    
    告诉wyportmap.py你的扫描目标，开始扫描
    python wyportmap.py 42.62.78.70-100
    
#### Example样例
   `
    [root@s102.ipcpu.com wyportmap]#./wyportmap.py 10.1.1.4-6 id0
--------------------------------------------------
* Starting id:(id0) [10.1.1.4-6] portmap scan
--------------------------------------------------
running[0s]: /usr/bin/nmap -oX - -sT -P0 -sV -O --script=banner -p T:21-25,2233,3306 10.1.1.4-6
running[5s]: /usr/bin/nmap -oX - -sT -P0 -sV -O --script=banner -p T:21-25,2233,3306 10.1.1.4-6
running[10s]: /usr/bin/nmap -oX - -sT -P0 -sV -O --script=banner -p T:21-25,2233,3306 10.1.1.4-6
running[15s]: /usr/bin/nmap -oX - -sT -P0 -sV -O --script=banner -p T:21-25,2233,3306 10.1.1.4-6
--------------------------------------------------
/home/wyportmap/libnmap/process.py:546: DeprecationWarning: data collected from finished events are deprecated.Use NmapParser.parse()
  "Use NmapParser.parse()", DeprecationWarning)

--------------------------------------------------


Result:


NmapHost: [10.1.1.4 (a4.ipcpu.idc) - up] NmapService: [open 2233/tcp ssh (product: OpenSSH version: 5.3 extrainfo: protocol 2.0)]
NmapHost: [10.1.1.5 (a5.ipcpu.idc) - up] NmapService: [open 2233/tcp ssh (product: OpenSSH version: 5.3 extrainfo: protocol 2.0)]
NmapHost: [10.1.1.6 (a6.ipcpu.idc) - up] NmapService: [open 2233/tcp ssh (product: OpenSSH version: 5.3 extrainfo: protocol 2.0)]
NmapHost: [10.1.1.6 (a6.ipcpu.idc) - up] NmapService: [open 3306/tcp mysql (product: MySQL version: 5.5.41-log)]
None
    `
