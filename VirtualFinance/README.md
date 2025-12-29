
# 虚拟银行与移动支付（Virtual Finance）Clash 分流规则集


## 用途

- 用于 **全球主流的“虚拟银行”+“移动支付”** 进行分流
- 包含：**Paypal, Wise, Monzo, Revolut**

<br>

## 引用范例

```yaml
    Paypal_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Paypal_No_Resolve.yaml'                           , path: ./ruleset/Paypal_No_Resolve.yaml                    }
    Wise_No_Resolve                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Wise_No_Resolve.yaml'                             , path: ./ruleset/Wise_No_Resolve.yaml                      }
    Monzo_No_Resolve                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Monzo_No_Resolve.yaml'                            , path: ./ruleset/Monzo_No_Resolve.yaml                     }
    Revolut_No_Resolve                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Revolut_No_Resolve.yaml'                          , path: ./ruleset/Revolut_No_Resolve.yaml                   } 
 
 
    Paypal                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Paypal.yaml'                                      , path: ./ruleset/Paypal.yaml                               }
    Wise                                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Wise.yaml'                                        , path: ./ruleset/Wise.yaml                                 }
    Monzo                               : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Monzo.yaml'                                       , path: ./ruleset/Monzo.yaml                                }
    Revolut                             : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Revolut.yaml'                                     , path: ./ruleset/Revolut.yaml                              } 
```

## 使用说明

本项目，包括 以下三组规则，“二选一”，选其中一个即可:

| 分组 | 后缀 | 建议 |
| --- | --- | --- |
| 第一组 | No_Resolve |  |
| 第一组 | 无 |  |


## 验证说明与相关阅读

⚠️ 注意， no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

* [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88)
