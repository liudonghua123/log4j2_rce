# Apache Log4j 2 
Apache log4j2 开源日志组件远程代码执行

> 攻击者通过构造恶意请求，触发服务器log4j 2 日志组件的远程代码执行漏洞。漏洞无需特殊配置，经验证，最新版的补丁可以防护此问题

[官方最新补丁： log4j-2.15.0-rc2](https://github.com/apache/logging-log4j2/releases/tag/log4j-2.15.0-rc2)

## 紧急处置方案
1. 修改配置  log4j2.formatMsgNoLookups=True
2. 修改jvm参数 -Dlog4j2.formatMsgNoLookups=true
3. 通过防火墙自定义规则，限制`jndi` 、`ldap` 等恶意payload
4. 漏洞探测大多采用dnslog 等带外方式，可以禁掉服务器主动外联权限

## 漏洞复现
[详细复现步骤参考](https://github.com/dbgee/fastjson-rce)   ，与fastjson 的复现一致，只是使用的pom 文件不同而已

* 需要注意2.14.1 不能稳定复现，建议采用2.8.x 版本

## 环境下载
[log4j2_rce-0.0.1.jar](https://github.com/dbgee/log4j2_rce/releases/tag/0.0.1) 