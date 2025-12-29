
# -----------------------------------------
# 此规则集：用于，“Signal“，进行分流
# -----------------------------------------

# 用途：
#	访问 Signal 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    Signal_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Signal/Signal_No_Resolve.yaml'                                    , path: ./ruleset/Signal_No_Resolve.yaml                    }    
#
#    Signal                              : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Signal/Signal.yaml'                                               , path: ./ruleset/Signal.yaml                               }                 
#
#    Signal_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Signal/Signal_Domain.yaml'                                        , path: ./ruleset/Signal_Domain.yaml                        }    
#

<br>

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

 - [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88) 