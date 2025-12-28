
# Geosite:cn 修正版规则集
<br>

**项目简述：**

* 本规则集旨在对 **🇨🇳 中国境内网站** 进行精准分流。
* **用途：** 与官方 `geosite:cn` 相同，但进行了深度清洗。
* **核心改进：** 注释掉了非中国服务器（不满足 GeoIP:CN）的域名，以及冗余的 cn 后缀二级域名（只保留 `*.cn` 一条规则）。

<br>

**数据统计（截至 2025-12-03）：**

* **原版问题：**
    * 原版 `geosite:cn` 中，超过 **8%** 的规则是指向境外 IP 的域名（6800 条中约 530 条错误）。
    * 超过 **19%** 的规则是冗余的（均为 cn 后缀域名，约 1300 条）。
    * **合计：** 接近 **27%** 的规则（近 1900 条）是错误或冗余的，需要被删除！

* **当前版本：**
    * 整理后的规则总数：**4800 余行**。
    * 已包含 blackmatrix7/China （ 非ChinaMax ）规则集内 **97%** 的规则
        * 剩余未包含的 3% ，基本都是 野鸡个人站 和 无效网站。
    * 本魔改版 = **100% 精准优先**，宁可错漏，不可错配！！

* **更新计划：** 
    * 每年年底与官方同步一次（中国互联网生态非常稳定，年更足以满足需求）。

<br>
<br>

---

# 核心痛点与修正逻辑

<br>

为什么原版 Geosite、原版 ChinaMax 会有错误？**精准的标准是什么？** 到底什么叫 🇨🇳 中国分流规则？

在构建分流规则时，我们需要明确收录标准。以下是五种常见的判定维度：

### 1. 在中国大陆，有根 DNS 的“域名”

* *包含风险：* 会包含 🌍 境外域名，甚至被 GFW 阻断的境外域名。

### 2. 在中国大陆，能直连的“域名”

* *包含风险：* 会包含 🌍 境外域名（如：没有被 GFW 封锁的境外域名）。

### 3. 中国公司的“域名”

* *包含风险：* 会包含 🌍 境外域名。例如中国公司自己运营的境外域名（如快手国际版 Kwai、抖音国际版 TikTok）。

### 4. 被中国 GeoIP 命中的“域名”（IP 归属地是中国的域名）

* *包含风险：* 依然会包含 🌍 境外域名。例如在中国有 CDN 服务器的任意境外域名。

### 5. （本项目的标准）同时满足以下严苛条件

* **条件 1 ：** 域名 IP 归属地为 🇨🇳 中国。
* **条件 2 ：** 非 `.us` / `.hk` / `.tw` 等其它国家地区顶级域名。
* **条件 3 ：** 域名非带有 `-us-west`  / `.eu.east` / `oversea` 等地理位置的 CDN 域名。
* **条件 4 ：** 排除掉虽然满足以上三点，但添加后会导致境外 APP 服务被屏蔽的域名（如 TikTok、Kwai）。

<br>

## 各版本规则精度对比

| 规则版本 | 对应类别 | 精度评级 | 说明 |
| :--- | :--- | :--- | :--- |
| **原版 ChinaMax** | 类别 1 | ❌❌❌❌❌ 精度最差 | 包含大量错误。 |
| **原版 geosite:cn** | 类别 3 | ⚠️⚠️⚠️ 精度比较差 | 会导致 TikTok 等无法登陆。 |
| **本规则集** | **类别 5** | ✅ **精度 100% 正确** | 完美修正，无误杀。 |



<br>
<br>

---

# 引用配置范例

<br>

请在您的 Clash / Stash 配置文件中参考以下格式引入：

```yaml
# ---------------------------------------------------
#  GeositeCN 修正版 - 引用示例
# ---------------------------------------------------

    GeositeCN_No_Resolve                  : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/GeositeCN_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/GeositeCN_No_Resolve.yaml)'                                , path: ./ruleset/GeositeCN_No_Resolve.yaml             }

    GeositeCN                             : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/GeositeCN.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/GeositeCN.yaml)'                                           , path: ./ruleset/GeositeCN.yaml                        }
           
    GeositeCN_Domain                      : {type: http, behavior: domain    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/GeositeCN_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/GeositeCN_Domain.yaml)'                                    , path: ./ruleset/GeositeCN_Domain.yaml                 }

```

---

# 使用说明

本项目包括以下三组规则，**“三选一”**，选其中一个即可：

| 后缀类型 | 说明 | 适用场景 |
| --- | --- | --- |
| **No_Resolve** | 第一组 | 包含 `no-resolve` 策略，不进行 DNS 解析。 |
| **(无后缀)** | 第二组 |  |
| **Domain** | 第三组 | **🔥推荐** |

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
   'RULE-SET:GeositeCN_Domain'    :  [ 'https://dns.alidns.com/dns-query#🇨🇳.<Country>—CN'  , 'https://doh.pub/dns-query#🇨🇳.<Country>—CN'    ]   
   # 其余所有域名解析， 通过 “♾️.<Final>”的VPN节点 ，转发给海外DNS服务器 
   '+.*'                          :  [ 'https://cloudflare-dns.com/dns-query#♾️.<Final>'   , 'https://dns.google/dns-query#♾️.<Final>'     ] 
     
# Rule分流：直连 中国IP     
rules :  
  # 中国直连
  - GEOIP , cn , 🇨🇳.<Country>—CN
  # 兜底：其余流量，转发VPN （白名单模式）
  - MATCH      , ♾️.<Final> 

# 远程规则集
rule-providers : 
   GeositeCN_Domain               : { type : 'http'  , behavior : 'domain'  , format : 'yaml'  , url : 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@latest/GeositeCN/GeositeCN_Domain.yaml' , path : './ruleset/GeositeCN_Domain.yaml' }                              

```
<br>

✅✅✅ 上述这种写法，可以几乎100%避免  由于本规则集合极个别不精准（比如，域名所有者，更换了IP，从指向国内IP，变成了指向境外IP），而导致的分流错误。并且100%防止了，DNS泄漏！并且，拥有 100% 满血版DNS解析能力（全程无需调用 no-resolve ）

<br>

上述过程，核心原理：

  - 通过中国规则集，让中国域名 只在中国本土的DNS 进行域名解析。从而确保 获取的IP地址 100%是中国的。（避免 中国域名解析请求，通过VPN节点转发到外国DNS解析，那样对于很多使用了全球CDN的大网站、顶流APP，99%会获得🌍外国IP地址）。只要获得的是中国IP地址，就可以使用GeoIP:cn，让中国IP地址直连（或走回国代理）。其余的域名，统统通过VPN节点，转发给海外DNS进行解析（避免DNS泄漏）
  
  - ‼️‼️‼️ 必须明白 ‼️‼️‼️ ：DNS策略分流（ nameserver-policy ），比普通分流规则（ rule ）重要十倍以上。因为当你通过 nameserver-policy，让哪个国家的VPN节点转发“域名解析请求”的时候，其解析后的IP所在国家就已经确定了，你后面再怎么写rule分流规则，都改变不了这个IP的地理位置。所以，在你写clash分流规则时，尤其是在基于地理位置（如 国家）的分离规则时，如果你的DNS的策略分流规则（ nameserver-policy ），弱于 你的 普通分流规则 （ Rule ），100%完全就是本末倒置  ‼️‼️‼️‼️‼️‼️‼️‼️‼️ 记住，DNS策略分流（ nameserver-policy ） vs  普通分流规则（ rule ），两者之间 1:1 复刻！两者互为镜像！才能达到最佳最完美（ 0绕路 + 0 DNS泄漏 + 满血版DNS解析）的分流 ‼️‼️‼️  （ 具体实施范例，可以看《 超级省电 Clash 分流规则模版》 ）

  - ‼️‼️‼️ 必须 禁用FakeIP + 禁用Fallback DNS ‼️‼️‼️  这技术压根就不应该被发明出来。100%垃圾中的垃圾。具体原因在 《 超级省电 Clash 分流规则模版 》内，如下章节已有阐述： [ 为什么必须禁用 ，官方推荐的 “ Fake IP + Fallback DNS + no-resolve ” 组合？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%E4%B8%BA%E4%BB%80%E4%B9%88%E6%9C%AC%E6%A8%A1%E7%89%88-%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E4%BA%86%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%9A%84%E7%BB%84%E5%90%88) 

<br>

更多范例（如：上述过程中，如何 100% 避免 美国VPN节点 请求日本CDN 等 绕路行为），可以看 如下：

 - 《 超级省电 Clash 分流规则模版》：https://github.com/Accademia/Clash_Configuration_Template
 
 -  建议直接使用上述模版