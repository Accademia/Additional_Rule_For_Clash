


# MicrosoftAPPs 微软全家桶分流规则

**规则集简述：**

* 本规则集旨在对 **Microsoft 微软全家桶** 业务进行分流。
* **覆盖范围：** 
    * Windows 系统更新、应用商店
    * Office 365 核心办公套件
    * 其他微软APP（但不包括：AI、github、linkedin、bing 等对中国阉割的服务）
* **核心策略：** 针对常用微软服务进行直连优化（或特定分流），同时明确剥离了需要特殊处理（翻墙）的业务。

<br>

------

# ✅ 收录与 ❌ 排除清单
<br>


为了避免规则冲突，本规则集对微软复杂的业务线进行了拆分。

### ✅ 已收录内容 (通常建议直连)
* **Windows 全家桶：** Win10 / Win11 系统更新、内置应用商店下载。
* **Office 全家桶 (2019+ / 365)：**
    * Word, Excel, PowerPoint, Visio
    * OneNote, OneDrive, OutLook
    * Hotmail, SharePoint, Skype 等

<br>

### ❌ 未收录内容 (建议单独处理)
以下服务因包含大量第三方域名、独立业务逻辑或必须翻墙，**未包含**在本规则集中：

| 服务名称 | 建议策略 | 原因/备注 |
| :--- | :--- | :--- |
| **Copilot** | 🌍 必须代理 | 包含大量子链接，需独立规则。 |
| **Bing** | 🌍 建议代理 | 避免国内版审查或功能缺失。 |
| **Edge** | 🌍 建议代理 | 浏览器同步及插件服务。 |
| **GitHub** | 🌍 必须代理 | 独立业务，必须走代理。 |
| **Azure** | ⚠️ 视情况而定 | 包含大量第三方公司域名，容易误杀。 |
| **Xbox** | 🎮 独立分流 | 游戏联机业务，建议单独分流。 |

<br>

### ⚠️ 规则排序警告 (重要)

> **请务必注意规则的引用顺序：**
>
> 由于本规则集包含微软的 **顶级域名 (Top-Level Domains)**，如果放置位置过高，可能会覆盖 Copilot 或 GitHub 的分流规则。
>
> **建议顺序：**
> 1. Copilot / GitHub / Bing (细分规则，优先匹配)
> 2. **MicrosoftAPPs (本规则集，兜底匹配)**

<br>
<br>

------

# 引用配置范例

请在您的 Clash / Stash 配置文件中参考以下格式引入：
<br>


```yaml
# ---------------------------------------------------
#  MicrosoftAPPs - 引用示例
# ---------------------------------------------------

     # 1. 不解析策略 (No Resolve)
     MicrosoftAPPs_No_Resolve             : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MicrosoftAPPs/MicrosoftAPPs_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MicrosoftAPPs/MicrosoftAPPs_No_Resolve.yaml)'          , path: ./ruleset/MicrosoftAPPs_No_Resolve.yaml      }

     # 2. 标准策略 (Classical)
     MicrosoftAPPs                        : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MicrosoftAPPs/MicrosoftAPPs.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MicrosoftAPPs/MicrosoftAPPs.yaml)'                     , path: ./ruleset/MicrosoftAPPs.yaml                 }
           
     # 3. 域名策略 (推荐移动端)
     MicrosoftAPPs_Domain                 : {type: http, behavior: domain    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MicrosoftAPPs/MicrosoftAPPs_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MicrosoftAPPs/MicrosoftAPPs_Domain.yaml)'               , path: ./ruleset/MicrosoftAPPs_Domain.yaml          }

```

<br>
<br>

---

# 使用说明与建议
<br>


本项目提供三组不同后缀的规则文件，请根据您的客户端和需求，**任选其一**即可，不要重复引用。

| 后缀类型 | 说明 | 适用场景 |
| --- | --- | --- |
| **No_Resolve** | 包含 `no-resolve` 策略 | 适用于不需要解析 DNS 的场景。 |
| **(无后缀)** | 标准 Classical 格式 | 通用场景。 |
| **Domain** | 纯域名列表 | **🔥 移动端推荐 (Stash / Clash Meta)** |

**💡 最佳实践：**

* 推荐优先选择最后一组 **（Domain 纯域名版）**。
* 特别是在移动端（如 **Stash for iOS**），这种写法能 **极大增加匹配速度** 和 **减少内存占用**。


