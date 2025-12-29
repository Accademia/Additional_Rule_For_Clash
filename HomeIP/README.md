
# 住宅IP（HomeIP）Clash 分流规则集


## 用途

- 对 必须 **“住宅IP”**（双ISP住宅IP）才能访问的网站进行分流
- 适用于各国限制必须使用住宅IP才能正常访问（或购买下单）的网站

<br>

## 注意

> ⚠️ **注意**：**视频、音频网站** 不包含在此规则集中。

<br>

## 引用范例

```yaml
    HomeIPUS_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HomeIP/HomeIPUS_No_Resolve.yaml'                                , path: ./ruleset/HomeIPUS_No_Resolve.yaml                  }
    HomeIPJP_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HomeIP/HomeIPJP_No_Resolve.yaml'                                , path: ./ruleset/HomeIPJP_No_Resolve.yaml                  }




    HomeIPUS                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HomeIP/HomeIPUS.yaml'                                           , path: ./ruleset/HomeIPUS.yaml                             }
    HomeIPJP                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HomeIP/HomeIPJP.yaml'                                           , path: ./ruleset/HomeIPJP.yaml                             }

```

## 使用说明

本项目，包括 以下三组规则，“三选一”，选其中一个即可:

| 分组 | 后缀 | 建议 |
| --- | --- | --- |
| 第一组 | No_Resolve |  |
| 第一组 | 无 | 🔥 最优 |


## 验证说明与相关阅读

⚠️ 注意，no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

* [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88)

