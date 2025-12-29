
# Aqara 智能家居分流规则集 (Global & CN)

### 项目简述

* **用途：** 针对 Aqara (绿米) 智能家居设备流量进行精细化分流。
* **功能：** 支持区分 **Aqara Global (境外)** 与 **Aqara CN (国内)** 的流量，满足不同区域服务器的连接需求或隐私隔离需求。

<br>

### ⚠️ 核心配置建议

本项目提供多组规则文件，请根据您的设备性能和需求，**任选其一**引用即可。

| 后缀类型 | 说明 | 适用场景 |
| :--- | :--- | :--- |
| **Domain + IP** | **🔥🔥🔥 推荐** | 极大提升匹配速度并降低内存占用 |
| **No_Resolve** | 包含 `no-resolve` 策略 | 适用于不需要 DNS 解析的场景 |
| **(无后缀)** | 标准 Classical 格式 | |

<br>
<br>

---

#  引用配置范例
<br>


请将以下规则复制到您的 Clash / Stash 配置文件中。

### 🌍 境外规则 (Aqara Global)

> 适用于连接 Aqara 国际版服务器 (AWS)，实现数据出境。

```yaml
# ---------------------------------------------------
#  Aqara Global - 引用示例
# ---------------------------------------------------

# No-Resolve 版
AqaraGlobal_No_Resolve : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal_No_Resolve.yaml)', path: ./ruleset/AqaraGlobal_No_Resolve.yaml }

# 标准版
AqaraGlobal            : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal.yaml)',            path: ./ruleset/AqaraGlobal.yaml            }

# Domain + IP 版 (推荐)
AqaraGlobal_Domain     : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal_Domain.yaml)',     path: ./ruleset/AqaraGlobal_Domain.yaml     }
AqaraGlobal_IP         : {type: http, behavior: ipcidr,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal_IP.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal_IP.yaml)',         path: ./ruleset/AqaraGlobal_IP.yaml         }

```

<br>


### 🇨🇳 国内规则 (Aqara CN)

> 适用于连接 Aqara 中国大陆服务器。

```yaml
# ---------------------------------------------------
#  Aqara CN - 引用示例
# ---------------------------------------------------

# No-Resolve 版
AqaraCN_No_Resolve     : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN_No_Resolve.yaml)',     path: ./ruleset/AqaraCN_No_Resolve.yaml     }

# 标准版
AqaraCN                : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN.yaml)',                 path: ./ruleset/AqaraCN.yaml                 }

# Domain + IP 版 (推荐)
AqaraCN_Domain         : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN_Domain.yaml)',          path: ./ruleset/AqaraCN_Domain.yaml          }
AqaraCN_IP             : {type: http, behavior: ipcidr,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN_IP.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN_IP.yaml)',              path: ./ruleset/AqaraCN_IP.yaml              }

```

<br>

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

 - [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88) 
 
<br>

<br>


---

#  场景化使用策略
<br>


根据您对 **隐私安全** 和 **连接速度** 的不同追求，建议采取以下不同策略：

### 🛡️ 追求绝对安全性 (推荐)

* **部署位置：** 路由器
* **策略设置：** **REJECT (拒绝)** 所有 Aqara 规则（包括 Global 和 CN）。
* **效果：** 阻断 Aqara 设备连接厂商服务器，强制其仅通过本地局域网连接 **Apple HomeKit**。
* **优势：** 实现摄像头数据的最大安全性，避免数据上传至任何第三方服务器。
* **注意：** 固件升级时需临时手动放行。

<br>

### 🌏 追求避开区域审查

* **部署位置：** 路由器
* **策略设置：** **REJECT (拒绝)** `AqaraCN` 规则，放行 `AqaraGlobal` 规则。
* **效果：** 仅屏蔽中国区连接。

<br>

### 🚀 追求官方 App 响应速度

* **部署位置：** 手机端
* **策略设置：** **DIRECT (直连)** 所有规则。
* **效果：** 确保 Aqara App 操作无延迟。

<br>

<br>

---

#  ⚠️ 硬件版本与隐私安全警告

### 国际版 vs 国内版

| 特性 | 🇺🇸 Aqara 国际版 | 🇨🇳 Aqara 国内版 |
| --- | --- | --- |
| **服务器** | 境外亚马逊云 (AWS) | 中国境内 Aqara 服务器 |
| **隐私风险** | **低** (数据隔离，避开审查) | **高** (存在数据被调取风险) |
| **互刷固件** | - | **不可** 刷成国际版 |

### 🔒 最佳安全实践 (HomeKit 摄像头)

如果您追求极致的隐私安全，请遵循以下配置：

1. **硬件选择**：使用 Aqara 国际版设备。

2. **存储设置**：**不要插入 TF 存储卡**。

3. **云端设置**：
    * 配置数据仅上传至 **🇺🇸 美国 iCloud 云端**。
    * 开启苹果 iCloud **"高级数据保护" (Advanced Data Protection)**。
    * **切断** Aqara 所有自家服务器的连接（见上文策略）。

4. **结果**：除了您自己，没有任何人（包括厂商和执法机构）能查看您的监控视频。其安全性远高于本地 NAS 存储。

> **参考资料：**
> * [Aqara 官方 API 文档 (部分)](https://opendoc-test.aqara.cn/en/docs/developmanual/apiIntroduction/APIUsageGuide.html)
> * *注：官方 API 文档不全，未包含 AWS 相关规则，本规则集已通过 Keyword 和 IP 规则补全。*
> 

<br>

<br>

---

#  其他

<br>


![20CAD1E5-37D0-459C-A74D-30D66B7184DC](https://github.com/user-attachments/assets/368653f6-115f-4e18-9e0a-a0bb8da3643b)