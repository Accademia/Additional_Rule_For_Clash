
# xAI Grok 分流规则使用指南

**规则集简述：**

* 本规则集旨在对 **xAI (Grok)** 相关服务进行精准分流。
* **适用场景：** 解决 Grok AI 在国内网络环境下的访问问题。
* **特别说明：** 针对 iOS 客户端存在的 IPv6 连接 Bug 提供了详细解决方案。

<br>
<br>

------

# ⚠️ iOS 客户端严重 BUG 说明
<br>

**现象描述：**
由于 **Grok APP for iOS** 存在网络连接逻辑缺陷，在获得域名解析后，只会尝试连接 IPv6 地址。如果您的网络环境（DNS 解析）返回了 IPv6 结果，但代理节点不支持或未开启 IPv6 转发，会导致：
* ❌ Grok APP 在提问环节卡死。
* ❌ 用户无法登录。
* *注：Web 端、X 客户端内的 Grok 及实时语音功能不受影响，仅 APP 文字交互受影响。*

<br>

## 🛠️ 解决方案 (三选一)

如果您遇到上述卡死问题，请尝试以下修复方案：
<br>

### 方法 1：等待官方修复 (被动)
坐等 xAI Grok 开发团队自行修复此网络请求逻辑 BUG。
<br>

### 方法 2：开启 IPv6 隧道 (Stash 用户推荐)
在 Stash 面板中手动开启 TUN IPv6 分流，通常可秒解决此问题。

* **操作路径：** `Stash` -> `设置` -> `网络设置` -> `启用 Tunnel IPV6 路由`
* **⚠️ 副作用警告：** 开启后，手机在**局域网内**观看 Apple Homekit 摄像头时可能无法查看实时视频（公网访问不受影响）。且在 Stash 上设置局域网直连规则也无法规避此问题。
* *注：Clash Meta 用户可通过内网分流规则绕开此副作用。*
<br>

### 方法 3：关闭 DNS 的 IPv6 解析 (通用推荐)
如果您没有任何第三方 APP 依赖 IPv6，可以通过修改配置文件，彻底关闭 DNS 的 IPv6 查询，从而避开此 BUG。

**配置修改范例：**
请在您的配置文件 `dns` 模块中，修改或添加以下设置：

```yaml
dns:
  enable: true      # 保持开启
  ipv6: false       # ❌ 设置为 false。关闭基于 IPv6 的 DNS 查询
                    # 让 DNS 不返回 IPv6 结果，强制 APP 使用 IPv4 连接。

```

<br>

> **❌ 特别注意：** 此方法在 **Stash 3.x** 版本中可能无效，因为该 APP 存在不支持手动关闭 IPv6 解析的 BUG（开发者尚未回复反馈）。Stash 用户请优先尝试“方法 2”。
> 
<br>
<br>

---

# 引用配置范例
<br>

请在您的 Clash / Stash 配置文件中参考以下格式引入：

```yaml
# ---------------------------------------------------
#  Grok / xAI 分流规则 - 引用示例
# ---------------------------------------------------

     Grok_No_Resolve                      : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_No_Resolve.yaml)'                                    , path: ./ruleset/Grok_No_Resolve.yaml                    }

     Grok                                 : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok.yaml)'                                               , path: ./ruleset/Grok.yaml                               }
           
     Grok_Domain                          : {type: http, behavior: domain    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_Domain.yaml)'                                        , path: ./ruleset/Grok_Domain.yaml                        }
    
     Grok_IP                              : {type: http, behavior: ipcidr    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_IP.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_IP.yaml)'                                            , path: ./ruleset/Grok_IP.yaml                            }

```

<br>
<br>

---

# 使用说明与建议
<br>

本项目提供多组不同后缀的规则文件，请根据您的客户端和需求，**任选其一**即可，不要重复引用。

| 后缀类型 | 说明 | 适用场景 |
| --- | --- | --- |
| **No_Resolve** | 包含 `no-resolve` 策略 | 适用于不需要解析 DNS 的场景。 |
| **(无后缀)** | 标准 Classical 格式 | 通用场景。 |
| **Domain** | 纯域名列表 | **🔥 移动端推荐 (搭配 IP 列表使用)** |
| **IP** | 纯 IP CIDR 列表 | **🔥 移动端推荐 (搭配 Domain 列表使用)** |
<br>

## 💡 最佳实践建议

* **推荐方案：** 优先选择 **Domain + IP** 组合引用的方式。
* **理由：** 特别是在移动端（如 **Stash for iOS**），将域名规则与 IP 规则分开引用，能**极大增加匹配速度**并**减少内存占用**。
