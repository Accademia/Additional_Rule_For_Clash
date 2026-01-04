
# Gemini Clash 分流规则集


## 用途

- 访问 **Gemini** 所需要的 **Clash 分流规则**

<br>

## 注意

  - Google Gemini 是全球 前四大AI（ChatGPT Grok Gemini Claude）中，唯一一个不提供足量隐私功能的APP。即，在 “完整功能” 的模式下，你与Gemini的对话 会100%拿去用于训练谷歌AI，并且可以被谷歌的人工，是可以随时手动审查你与AI的所有对话内容。（ 这个问题 在Reddit上 已经被 🇺🇸美国网友 骂疯了 ）
 
  - 而其他三家，针对上述情况，都提供了手动开关。开启后，你与AI的对话内容，即不会被官方人员审查、 也不会用于训练AI（不会泄密）

  - 而 🇨🇳 国产AI，如 腾讯元宝、字节豆包，压根不提供任何隐私选项。所以，诸如公司财务报表、人事安排、或自己电子邮箱内容，等敏感信息，不要发送（或链接）到这些AI上面去。


<br>

## 引用范例

```yaml
     Gemini_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Gemini/Gemini_No_Resolve.yaml'                                    , path: ./ruleset/Gemini_No_Resolve.yaml                    }    
 
     Gemini                              : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Gemini/Gemini.yaml'                                               , path: ./ruleset/Gemini.yaml                               }                 
 
     Gemini_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Gemini/Gemini_Domain.yaml'                                        , path: ./ruleset/Gemini_Domain.yaml                        }    
```

<br>

## 使用说明

本项目，包括 以下三组规则，“三选一”，选其中一个即可:

| 分组 | 后缀 | 建议 |
| --- | --- | --- |
| 第一组 | No_Resolve |  |
| 第一组 | 无 |  |
| 第一组 | Domain \ IP | 🔥 最优 |

优先选择，最后一组（Domain + IP），在移动端（Stash for iOS），这种写法极大增加匹配速度和减少内存占用。

<br>

## 验证说明与相关阅读

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

* [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88)
