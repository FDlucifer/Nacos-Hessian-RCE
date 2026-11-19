# Nacos-Hessian-RCE PoC

> **阅读定位：Nacos 历史安全研究归档。** 核对实际部署版本、厂商公告和审计记录时，可先读[防御阅读说明](DEFENSIVE-NOTES.md)。旧内容不代表当前产品的修复状态。原提交署名为 X1r0z。

分析文章

[https://t.zsxq.com/0f5hOnVRN](https://t.zsxq.com/0f5hOnVRN)

[https://exp10it.io/2023/06/nacos-jraft-hessian-反序列化-rce-分析/](https://exp10it.io/2023/06/nacos-jraft-hessian-%E5%8F%8D%E5%BA%8F%E5%88%97%E5%8C%96-rce-%E5%88%86%E6%9E%90/)

一些 Hessian 反序列化链子

1. BCEL ClassLoader (jdk<8u251)
2. JNDI LDAP 反序列化 + POJONode 触发 TemplatesImpl
3. POJONode 触发 UnixPrintService
4. JavaUtils.writeBytesToFilename + System.load
5. SerializationUtils 二次反序列化 + POJONode 触发 TemplatesImpl
