
# Zigbee 通信，基于cc2652p

## 开发与部署

使用[simplelink_cc13xx_cc26xx_sdk_7_10_00_98 sdk](https://www.ti.com/tool/download/SIMPLELINK-LOWPOWER-F2-SDK/7.10.00.98)开发\
IDE为IAR EWARM 9.20.1\
[EWARM新版本破解注册方法](https://blog.csdn.net/xue_nuo/article/details/124661894) \
部署方法：需要使用backup内对应源文件替换sdk安装目录下的sample_sw工程的源文件

## 说明

使用了Zstack的sample_sw集群，利用了例程的属性回报事件实现了地面端与机器人端的通信

### 协调器 Coordinator

接收来自上位机的回报属性，通过串口发送给机器人遥控信息（部署在机器人端）

### 终端 EndDevice

组网成功后LED会闪红灯。新版上位机直接从遥控器的JR仓读取ppm信号，获得每个通道的数据后上报给协调器。
