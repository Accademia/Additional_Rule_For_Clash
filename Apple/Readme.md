
# Apple 苹果服务分流规则

### 项目简述

* **用途：** 针对 Apple 苹果设备（iPhone, MacBook, iPad 等）及相关服务的分流规则 
* **精简策略：** 苹果公司在 40 年发展中曾使用过高达 1500 个域名，其中大量已废弃。本规则集**只保留**目前仍在使用的活跃域名 

<br>

### ⚠️ 核心说明与排除项

在使用本规则前，请注意以下策略细节：

 **排除中国区服务**：本规则 **不收录** “云上贵州”及中国区苹果特有的服务域名。这些流量通常直接走 `geosite:cn` 规则即可 


<br>
<br>

---

# 引用配置范例
<br>

请在您的 Clash / Stash 配置文件中参考以下格式引入。
<br>

### 📦 规则文件后缀说明 (三选一)

本项目提供三组不同后缀的规则文件，请根据您的客户端和需求，**任选其一**即可 

| 后缀类型 | 说明 | 适用场景 |
| :--- | :--- | :--- |
| **Domain + IP** | **🔥🔥🔥 推荐** | 极大增加匹配速度并减少内存占用 |
| **No_Resolve** | 包含 `no-resolve` 策略 | 适用于不需要 DNS 解析的场景 |
| **(无后缀)** | 标准 Classical 格式 |  |

<br>
<br>

### 1. Domain + IP 策略引用 (🔥 推荐)
<br>

```yaml
# ---------------------------------------------------
#  Apple - 引用示例 (Domain + IP 版)
# ---------------------------------------------------

Apple_Domain : {type: http, behavior: domain, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple_Domain.yaml)', path: ./ruleset/Apple_Domain.yaml }
Apple_IP     : {type: http, behavior: ipcidr, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple_IP.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple_IP.yaml)',     path: ./ruleset/Apple_IP.yaml     }

```
<br>

### 2. No-Resolve 策略引用
<br>

```yaml
# ---------------------------------------------------
#  Apple - 引用示例 (No-Resolve 版)
# ---------------------------------------------------

Apple_No_Resolve : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple_No_Resolve.yaml)', path: ./ruleset/Apple_No_Resolve.yaml }

```
<br>

### 3. 标准策略引用 (Classical)
<br>

```yaml
# ---------------------------------------------------
#  Apple - 引用示例 (标准版)
# ---------------------------------------------------

Apple : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple.yaml)', path: ./ruleset/Apple.yaml }

```

<br>

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

 - [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88) 