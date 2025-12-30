
# 各国银行（Bank）Clash 分流规则集

## 用途

- 访问 **各国银行（Bank）** 所需要的 **Clash 分流规则** 
- 在反洗钱、反欺诈 0容忍的欧美国家，连接银行账户的IP，**必须是本国IP** 

<br>

## 注意 （一定要看完 ❕❕❕❕ ）

> ⚠️ **离岸账户**（如香港、新加坡的所有账户，以及非开放口岸国家的离岸账户） **无需特定IP，建议直连**！！ 

> 对于大多数 券商（无论 🇺🇸 美国 、🇬🇧 英国 、 🇸🇬 新加坡 、 🇭🇰 香港） **无需特定IP，建议直连**！！

> 美国 英国 加拿大 ，大银行的离岸账户（如 劳埃德、 花旗、加拿大皇家银行 等 ），都是15万美金存款起步的，如果你不是这个标准，那你就不是离岸账户，你就必须要其本国的IP（ 小银行离岸账户除外，如华美银行 ）

> 对大多数国家的银行来说，都不要求 必须本国IP连接。但 美国、英国 除外，这俩国家银行 对跨国洗钱0容忍，像国外IP连接本土银行账户，这大概率会被认为是涉嫌跨国洗钱、或账户被盗，所以会封控你的账户。对于真正的美国人，美国手机号 在任何一个国家，其IP都是美国的，不会因为出差到海外，IP就变成海外。所以，你必须准备美国IP和英国IP（上述银行 对于是否 机房IP、住宅IP 并不敏感）

> ❌❌❌ 对于很多跨国银行，如 花旗银行、汇丰银行、渣打银行，其各国APP的分流规则，100%是交叉的。虽然在本规则集合内，针对不同国家，都把这些银行APP，分流了一部分，但是分流规则并不充分。因为，这些跨国银行在不同国家的APP，都会连接到其美国的服务器上去（但这些银行在中国的账户除外）。好在，如果你能开得起 跨国银行账户，基本上，你用是离岸银行账户，对IP归属地 也不敏感。

> ❌❌❌ 本规则集 ，并不充分，没有把各个银行的子链接全部找出来，并且也很全部难找。因为有些银行APP还是用了公共CDN的链接，非常容易跟其他规则有交叉。（ 也欢迎补充规则 ）

> ⚠️⚠️⚠️⚠️⚠️⚠️⚠️ 对于 美国数字居民 ，最好方式，就是 直接使用 [《 超级省电 clash 分流规则模版 》](https://github.com/Accademia/Clash_Configuration_Template) ，或参考其分流方式（ 白名单模式 + 兜底走美国VPN节点 ）。

> 我目前使用 [《 超级省电 clash 分流规则模版 》](https://github.com/Accademia/Clash_Configuration_Template) ，操作我自己在 🇺🇸美国、🇬🇧英国、🇨🇦加拿大、🇯🇵日本、🇫🇷法国、🇳🇱荷兰、🇸🇬新加坡、🇭🇰香港 的 我自己的各银行账户，是没有出现因为IP被封控的问题的。顺便给一句忠告，非 “英语母语+发达国家 的银行账户” ，最好别开，没意义，而且往往这些国家 对外国人银行账户的友好度都不行（估计也是因为外国人账户太少的缘故）。除非你在那些国家有业务。

> **加拿大的银行**，可以使用 **美国IP** 访问，而不被封控。 

> 

<br>

## 引用范例

```yaml
# ----------------------
# 第一组：No_Resolve
# ----------------------
   BankUS_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUS_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUS_No_Resolve.yaml)', path: ./ruleset/BankUS_No_Resolve.yaml}
   BankUK_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUK_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUK_No_Resolve.yaml)', path: ./ruleset/BankUK_No_Resolve.yaml}
   BankAU_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankAU_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankAU_No_Resolve.yaml)', path: ./ruleset/BankAU_No_Resolve.yaml}
   BankJP_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankJP_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankJP_No_Resolve.yaml)', path: ./ruleset/BankJP_No_Resolve.yaml}
   BankHK_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankHK_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankHK_No_Resolve.yaml)', path: ./ruleset/BankHK_No_Resolve.yaml}
   BankSG_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankSG_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankSG_No_Resolve.yaml)', path: ./ruleset/BankSG_No_Resolve.yaml}
   BankDE_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankDE_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankDE_No_Resolve.yaml)', path: ./ruleset/BankDE_No_Resolve.yaml}
   BankNL_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankNL_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankNL_No_Resolve.yaml)', path: ./ruleset/BankNL_No_Resolve.yaml}
   BankFR_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankFR_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankFR_No_Resolve.yaml)', path: ./ruleset/BankFR_No_Resolve.yaml}

# ----------------------
# 第二组：标准（无后缀）
# ----------------------
   BankUS                              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUS.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUS.yaml)', path: ./ruleset/BankUS.yaml}
   BankUK                              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUK.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUK.yaml)', path: ./ruleset/BankUK.yaml}
   BankAU                              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankAU.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankAU.yaml)', path: ./ruleset/BankAU.yaml}
   BankJP                              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankJP.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankJP.yaml)', path: ./ruleset/BankJP.yaml}
   BankHK                              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankHK.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankHK.yaml)', path: ./ruleset/BankHK.yaml}
   BankSG                              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankSG.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankSG.yaml)', path: ./ruleset/BankSG.yaml}
   BankDE                              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankDE.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankDE.yaml)', path: ./ruleset/BankDE.yaml}
   BankNL                              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankNL.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankNL.yaml)', path: ./ruleset/BankNL.yaml}
   BankFR                              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankFR.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankFR.yaml)', path: ./ruleset/BankFR.yaml}

# ----------------------
# 第三组：Domain
# ----------------------
   BankUS_Domain                       : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUS_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUS_Domain.yaml)', path: ./ruleset/BankUS_Domain.yaml}
   BankUK_Domain                       : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUK_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUK_Domain.yaml)', path: ./ruleset/BankUK_Domain.yaml}
   BankAU_Domain                       : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankAU_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankAU_Domain.yaml)', path: ./ruleset/BankAU_Domain.yaml}
   BankJP_Domain                       : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankJP_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankJP_Domain.yaml)', path: ./ruleset/BankJP_Domain.yaml}
   BankHK_Domain                       : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankHK_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankHK_Domain.yaml)', path: ./ruleset/BankHK_Domain.yaml}
   BankSG_Domain                       : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankSG_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankSG_Domain.yaml)', path: ./ruleset/BankSG_Domain.yaml}
   BankDE_Domain                       : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankDE_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankDE_Domain.yaml)', path: ./ruleset/BankDE_Domain.yaml}
   BankNL_Domain                       : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankNL_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankNL_Domain.yaml)', path: ./ruleset/BankNL_Domain.yaml}
   BankFR_Domain                       : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankFR_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankFR_Domain.yaml)', path: ./ruleset/BankFR_Domain.yaml}

```
<br>

## 使用说明

本项目，包括 以下三组规则，“三选一”，选其中一个即可:

| 分组 | 后缀 | 建议 |
| --- | --- | --- |
| 第一组 | No_Resolve |  |
| 第一组 | 无 |  |
| 第一组 | Domain \ IP | 🔥 最优 |

优先选择，最后一组（Domain + IP），极大增加匹配速度 + 减少内存占用。在移动端（如 Stash for iOS），这种写法优势明显。 

<br>

## 验证说明与相关阅读

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

* [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88) 

