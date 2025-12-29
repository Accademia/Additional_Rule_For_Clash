
# 各国银行（Bank）Clash 分流规则集

## 用途

- 访问 **各国银行（Bank）** 所需要的 **Clash 分流规则** [cite: 1]
- 在反洗钱、反欺诈 0容忍的欧美国家，连接银行账户的IP，**必须是本国IP** [cite: 1]

<br>

## 注意

> ⚠️ **离岸账户**（如香港、新加坡的所有账户，以及非开放口岸国家的离岸账户）**无需特定IP，建议直连**！！注意，各国银行的离岸账户的保底存款，都会要求20～30万美金或英镑起步。 [cite: 1]

> **加拿大的银行**，可以使用 **美国IP** 访问，而不被封控。 [cite: 1]

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

