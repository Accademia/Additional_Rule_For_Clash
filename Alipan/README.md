# 阿里云盘 / 阿里网盘（Alipan）Clash 分流规则集


## 用途

- 访问 **阿里网盘 / 阿里云盘** 所需要的 **Clash 分流规则**

<br>

## 注意

>     强烈不建议使用阿里云盘，这是我见过最流氓的云盘，没有之一。每次启动会 强制将云盘加入启动项，后台静默扫描硬盘，而且数据无加密明文存储在云盘，总之，除了网速比百度网盘快之外，其他任何一个方面，都比百度网盘还流氓一百倍！！ 强烈不建议使用。

<br>

## 引用范例

```yaml
   Alipan_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Alipan/Alipan_No_Resolve.yaml'                                      , path: ./ruleset/Alipan_No_Resolve.yaml                    }

   Alipan                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Alipan/Alipan.yaml'                                                 , path: ./ruleset/Alipan.yaml                               }

   Alipan_Domain                       : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Alipan/Alipan_Domain.yaml'                                             , path: ./ruleset/Alipan_Domain.yaml                           }
```

<br>

## 使用说明

本项目，包括 以下三组规则，“三选一”，选其中一个即可:

| 分组 | 后缀 | 建议 |
|--|--|--|
|第一组  | No_Resolve    | |
|第一组  | 无  | |
|第一组  | Doamin \ IP| 🔥 最优|

优先选择，最后一组（Domain + IP），极大增加匹配速度 + 减少内存占用。

<br>

## 验证说明与相关阅读

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

 - [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88)
