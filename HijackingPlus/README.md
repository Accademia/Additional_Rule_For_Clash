
# HijackingPlus Clash 分流规则集


## 用途

- 用于补充 **Hijacking** 规则
- 屏蔽 **中国国家反诈中心** 相关网址
- 可配合 [Blackmatrix7 Hijacking 规则](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Hijacking) 一起使用

<br>

## 引用范例

```yaml
     HijackingPlus_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HijackingPlus/HijackingPlus_No_Resolve.yaml'                   , path: ./ruleset/HijackingPlus_No_Resolve.yaml   }
     HijackingPlus                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HijackingPlus/HijackingPlus.yaml'                              , path: ./ruleset/HijackingPlus.yaml              }
 ```
<br>

## 使用说明

本项目，包括 以下三组规则，“三选一”，选其中一个即可:

| 分组 | 后缀 | 建议 |
| --- | --- | --- |
| 第一组 | No_Resolve |  |
| 第一组 | 无 | 🔥 最优 |


<br>

## 验证说明与相关阅读

⚠️ 注意，仅优先保证 ： no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

* [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88)

