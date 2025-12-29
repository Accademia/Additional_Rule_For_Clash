
# ChinaDNS Clash 分流规则集


## 用途

- [cite_start]屏蔽 **中国大陆的DNS、HttpDNS**（被GFW污染波及的DNS和中国区私有DNS）[cite: 1]
- [cite_start]**原因**：所有中国大陆DNS，**都存在DNS污染**，且 **100%存在隐私泄漏风险** [cite: 1]

<br>

## 引用范例

```yaml
     ChinaDNS_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/ChinaDNS/ChinaDNS_No_Resolve.yaml'                   , path: ./ruleset/ChinaDNS_No_Resolve.yaml   }
     ChinaDNS                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/ChinaDNS/ChinaDNS.yaml'                              , path: ./ruleset/ChinaDNS.yaml              }
 
     ChinaDNS_Domain                    : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/ChinaDNS/ChinaDNS_Domian.yaml'                          , path: ./ruleset/ChinaDNS_Domian.yaml       }
     ChinaDNS_IP                        : {type: http, behavior: ipcidr, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/ChinaDNS/ChinaDNS_IP.yaml'                              , path: ./ruleset/ChinaDNS_IP.yaml           }
```
<br>

## 使用说明

本项目，包括 以下三组规则，“三选一”，选其中一个即可:

| 分组 | 后缀 | 建议 |
| --- | --- | --- |
| 第一组 | No_Resolve |  |
| 第一组 | 无 |  |
| 第一组 | Domain \ IP | 🔥 最优 |

优先选择，最后一组（Domain + IP），在移动端（Stash for iOS），这种写法极大增加匹配速度和减少内存占用 。
<br>

## 验证说明与相关阅读

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

* [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88)
