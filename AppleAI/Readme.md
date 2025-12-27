
# Apple Intelligence 分流规则使用指南

**规则集简述：**

* 本规则集旨在对 **Apple Intelligence (苹果智能)** 进行精准分流 。
* **核心目标：** 让 Siri 能够调用 **ChatGPT (海外AI)**，而不是 文心一言 (国产AI) 。
* **适用设备：**
    * 已解锁的 🇨🇳 国行 Mac 。
    * 非国行 (🇺🇸🇯🇵🇭🇰🇹🇼🇨🇦🇪🇺) 的 iPhone、iPad、Mac 。

> ⚠️ **注意：** 🇨🇳 国行 iOS 设备目前无法使用，设备已被锁死，或者请尝试使用 misaka26 。

<br>

<br>

------

# 核心原理：解除“三把锁”

要使用美区苹果智能 (ChatGPT for Siri)，需根据设备版本解除以下限制：

| 锁类型 | 限制描述 | 解锁方式 | 备注 |
| :--- | :--- | :--- | :--- |
| **1. 设备锁** | 仅针对 **🇨🇳 中国大陆国行** 设备 | 运行脚本 | 仅 Mac 可解，iOS 无法解除 。 |
| **2. 位置锁** | GPS 位于中国大陆时无法使用 | 系统设置 | 需关闭 Siri 定位服务。 |
| **3. IP 锁** | IP 归属地为中国大陆时无法使用 | 分流规则 | 需使用本规则集 + 境外节点 [cite: 5]。 |

<br>
<br>

## 🔓 第一步：解除 “设备锁” (仅国行 Mac)

**非国行设备请跳过此步。**

只有 **🇨🇳 国行 Mac** 可以通过脚本解除此锁。国行 iPhone/iPad 无法解除。

1.  **准备工作：**
    * **系统账号：** 必须登录 **非中国区** 的苹果账号 (iCloud + AppStore 缺一不可) [cite: 4]。
    * **系统地区：** 设置 -> 通用 -> 语言与地区 -> 地区 -> **美国** [cite: 4]。

2.  **运行脚本：**
    * 下载并运行 `enableAppleAI` 脚本：[Github 项目地址](https://github.com/kanshurichard/enableAppleAI) 。
    * *注意：运行前需关闭 SIP，运行后可重新开启。*

<br>

## 🌍 第二步：解除 “IP 锁” (网络环境)

必须确保 Siri 和 ChatGPT 的流量走海外代理。

* **操作方法：** 在您的代理软件中引用 **本分流规则**。

* **验证标准：** 您必须能在 **浏览器** 和 **ChatGPT APP** 中正常访问并登录 ChatGPT。如果官网都打不开，说明您的节点 IP 有问题或被封锁 。

<br>

## 📍 第三步：解除 “位置锁” (LBS 限制)

即使是非国行机，如果 Siri 检测到 GPS 在中国大陆，仍会强制调用“文心一言”。

* **操作方法：** 禁用 Siri 的地理位置权限。
    * 路径：`设置` -> `隐私与安全性` -> `定位服务` -> `Siri` -> **关闭**。

* **激活：** 完成后，需手动在 Siri 对话框输入“请调用 ChatGPT”以激活功能。

<br>
<br>

------

# 引用配置范例

请在您的 Clash / Stash 配置文件中参考以下格式引入：

```yaml
# ---------------------------------------------------
#  AppleAI 分流规则 - 引用示例
# ---------------------------------------------------

     AppleAI_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI_No_Resolve.yaml)'                                , path: ./ruleset/AppleAI_No_Resolve.yaml                  }

     AppleAI                              : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI.yaml)'                                           , path: ./ruleset/AppleAI.yaml                             }
           
     AppleAI_Domain                       : {type: http, behavior: domain    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI_Domain.yaml)'                                    , path: ./ruleset/AppleAI_Domain.yaml                      }

```

## 规则版本选择建议

> 本项目提供三组规则，请 **任选其一**，不要重复引用：

| 后缀类型 | 说明 | 适用场景 |
| --- | --- | --- |
| **No_Resolve** | 包含 `no-resolve` 策略 | 适用于不需要解析 DNS 的场景 |
| **(无后缀)** | 标准 Classical 格式 | 不推荐 |
| **Domain** | 纯域名列表 | **🔥🔥🔥 推荐**  |

> **💡 推荐：** 优先选择 **Domain** 版本。在移动端（如 Stash for iOS）能极大增加匹配速度并减少内存占用。

<br>

<br>

---

# 🛠 常见问题与故障排查

如果您配置了规则但仍无法连接（Siri 无法调用 ChatGPT 或无法登录），请按以下步骤自查：

### 1. 基础连接检查

* ❌ **节点检测：** 确保浏览器和 ChatGPT App 能正常工作。如果不行，请更换节点（ChatGPT 会封杀流氓代理节点）。


* ❌ **黑名单检查：** 确保已添加 ChatGPT 的分流规则。
* ❌ **协议检查：** 苹果智能和 ChatGPT 大量使用 **Quic** 协议。请检查您的 VPN 或链式代理是否支持 Quic 。



### 2. IPv6 问题 (⚠️ 重点)

Siri 在调用苹果智能时会 **优先使用 IPv6 解析**。如果规则允许 IPv6 解析结果，但您的节点或软件（如 Stash）关闭了 IPv6 路由，会导致连接失败 。

**表现：** 无法调用 ChatGPT，或在设置界面登录时显示“无法登录，登录账户时出现问题”。

**解决方案 (二选一)：**

* **方法 A (Stash 用户)：启用 IPv6 路由**
    * 设置：`Stash` -> `设置` -> `网络设置` -> `启用 Tunnel IPV6 路由`。
    * *副作用：* 开启后可能导致局域网内 Apple Homekit 无法查看实时视频。


* **方法 B (通用)：彻底关闭 DNS 的 IPv6 解析**
    * 在配置文件中修改 DNS 设置：


        ```yaml
        dns:
            enable: true
            ipv6: false        # ⚠️ 设置为 false，关闭基于 IPV6 的 DNS 查询
        ```


* *注意：* Stash 3.x 版本不支持手动关闭 IPv6 解析 (开发者未修复 BUG)，Stash 用户请使用方法 A。



