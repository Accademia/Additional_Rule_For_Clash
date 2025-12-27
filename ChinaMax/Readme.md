
# ChinaMax 修正版规则集

**项目简述：**

* 本规则集旨在对 **🇨🇳 中国境内网站** 进行精准分流。
* 基于 `blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaMax` 进行深度清洗。
* **核心改进：** 移除了其中被错误收录的非中国服务器域名。

**数据统计：**

* **原版问题：** 原版 ChinaMax 包含超过 **19,000** 条错误规则，错误率高达 **17%**。

* **当前版本：** 整理后的规则总数约 **98,500** 条（数据截至 2025-12-20）。

<br>
<br>

------

# 核心痛点与修正逻辑

<br>

为什么原版 Geosite 和 ChinaMax 会有错误？到底什么样的域名才算 **🇨🇳 “中国域名”**？

在构建分流规则时，我们需要明确收录标准。以下是五种常见的判定维度：

1.  **在中国大陆有根 DNS 的域名**
    * *包含风险：* 包含 🌍 境外域名，甚至是被 GFW 阻断的境外域名。
2.  **在中国大陆能直连的域名**
    * *包含风险：* 包含 🌍 境外域名（未被 GFW 封锁的）。
3.  **中国公司的域名**
    * *包含风险：* 包含中国公司运营的 🌍 境外域名（如快手国际版 Kwai、抖音国际版 TikTok）。
4.  **IP 归属地为中国的域名**
    * *包含风险：* 包含在中国有 CDN 服务器的 🌍 境外域名。
5.  **（本项目的理想标准）同时满足以下严苛条件**
    * **条件 1：** 域名 IP 归属地为 🇨🇳 中国。
    * **条件 2：** 非 `.us` / `.hk` / `.tw` 等其他国家地区顶级域名。
    * **条件 3：** 域名不带有 `-us-west` / `.eu.east` / `oversea` 等明显的境外地理位置标识。
    * **条件 4：** 即使满足上述条件，但添加后会导致境外 APP（如 TikTok）无法使用的域名，需排除。

<br>

## 各版本规则精度对比

| 规则版本 | 精度评级 | 说明 |
| :--- | :--- | :--- |
| **原版 ChinaMax** | ❌ 精度最差 | 仅满足上述类别 1，包含大量错误。 |
| **原版 Geosite:cn** | ⚠️ 精度较差 | 仅满足上述类别 3，会导致 TikTok 等无法登录。 |
| **修正版 GeositeCN** | ✅ 100% 正确 | 完美满足上述类别 5 的所有条件（本项目推荐搭配使用）。 |
| **修正版 ChinaMax** | ⚠️ 局部修正 | **本项目（当前规则集）**。虽然未达到 100% 完美，但已大幅优化。 |

<br>

## 本修正版 ChinaMax 的详细状态：

* ✅ **条件 1 (IP归属)：** 准确度 99.9% (仍有极少量漏网的境外 IP 域名)。
* ✅ **条件 2 (顶级域名)：** 准确度 100%。
* ❌ **条件 3 (地理标识)：** 暂未处理。
* ❌ **条件 4 (服务冲突)：** 暂未处理。

<br>
<br>

------

# 引用配置范例

<br>

请在您的 Clash / Stash 配置文件中参考以下格式引入：

```yaml
# ---------------------------------------------------
#  ChinaMax 修正版 - 引用示例
# ---------------------------------------------------

     ChinaMax_No_Resolve                  : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/ChinaMax_No_Resolve.yaml'                                , path: ./ruleset/ChinaMax_No_Resolve.yaml                  }

     ChinaMax                             : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/ChinaMax.yaml'                                           , path: ./ruleset/ChinaMax.yaml                             }
           
     ChinaMax_Domain                      : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/ChinaMax_Domain.yaml'                                    , path: ./ruleset/ChinaMax_Domain.yaml                      }
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
| **(无后缀)** | 标准 Classical 格式 |  |
| **Domain** | 纯域名列表 | **🔥推荐** |

<br>

**💡 推荐：**

- 以上三组，优先选择最后一组 **（Domain + IP）**。

- 特别是在移动端（如 **Stash for iOS**），这种写法能 **极大增加匹配速度** 和 **减少内存占用**。

<br>
<br>

---

# 💡 最佳使用建议

<br>

**特别重要‼️ 必看‼️ 如果想达到最佳使用效果，请务必遵循以下逻辑：**

使用时，优先在 DNS分流策略（ nameserver-policy ） 中引用 ，而不是优先在 分流规则（ rule ） 中引用。最佳引用方式，范例如下：

```yaml
# 禁用FakeIP + 禁用Fallback DNS
dns : 
  enable                          : true     
  enhanced-mode                   : redir-host
  fake-ip-filter-mode             : blacklist
  fake-ip-filter                  : [ '+.*' ] 

# DNS分流 ：获得 🇨🇳中国IP
nameserver-policy : 
   # 中国域名解析， 调用 国内DNS服务器
   'RULE-SET:ChinaMax_Domain'     :  [ 'https://dns.alidns.com/dns-query#🇨🇳.<Country>—CN'  , 'https://doh.pub/dns-query#🇨🇳.<Country>—CN'    ] 
   # 其余所有域名解析， 通过 “兜底策略”的VPN节点 ，转发给海外DNS服务器 
   '+.*'                          :  [ 'https://cloudflare-dns.com/dns-query#♾️.<Final>'   , 'https://dns.google/dns-query#♾️.<Final>'     ]
     
# Rule分流：直连 中国IP     
rules :
  # 中国直连
  - GEOIP , cn , 🇨🇳.<Country>—CN
  # 兜底：其余流量，转发VPN （白名单模式）
  - MATCH      , ♾️.<Final> 

# 远程规则集
rule-providers : 
   ChinaMax_Domain                : { type : 'http'  , behavior : 'domain'  , format : 'yaml'  , url : 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@latest/ChinaMax/ChinaMax_Domain.yaml' , path : './ruleset/ChinaMax_Domain.yaml' }                              

```
<br>

✅✅✅ 上述这种写法，可以几乎100%避免 由于本规则集合极个别不精准（比如，域名所有者，更换了IP，从指向国内IP，变成了指向境外IP），而导致的分流错误。并且100%防止了，DNS泄漏！

<br>

上述过程，核心原理：

  - 通过中国规则集，让中国域名 只在中国本土的DNS 进行域名解析。从而确保 获取的IP地址 100%是中国的。（避免 中国域名解析请求，通过VPN节点转发到外国DNS解析，那样对于很多使用了全球CDN的大网站、顶流APP，99%会获得🌍外国IP地址）。只要获得的是中国IP地址，就可以使用GeoIP:cn，让中国IP地址直连（或走回国代理）。 其余的域名，统统通过VPN节点，转发给海外DNS进行解析（避免DNS泄漏）
  
  - ‼️‼️‼️ 必须明白 ‼️‼️‼️ ：DNS策略分流（ nameserver-policy ），比普通分流规则（ rule ）重要十倍以上。因为当你通过 nameserver-policy，让哪个国家的VPN节点转发“域名解析请求”的时候，其解析后的IP所在国家就已经确定了，你后面再怎么写rule分流规则，都改变不了这个IP的地理位置。所以，在你写clash分流规则时，尤其是在基于地理位置（如 国家）的分离规则时，如果你的DNS的策略分流规则（ nameserver-policy ），弱于 你的 普通分流规则 （ Rule ），100%完全就是本末倒置  ‼️‼️‼️ ‼️‼️‼️ ‼️‼️‼️

<br>

更多范例（如：上述过程中，如何 100% 避免 美国VPN节点 请求日本CDN 等 绕路行为），可以看 如下：

 - 《 超级省电 Clash 分流规则模版》：https://github.com/Accademia/Clash_Configuration_Template
 
 -  建议直接使用上述模版
 
 
 
 