
# -----------------------------------------
# 此规则集：用于，全球主流的“虚拟银行”+“移动支付“，进行分流
# -----------------------------------------

# 用途：
#	Paypal
#	Wise
#	Monzo
#	Revolut
#
# 引用范例 ：
#
#   Paypal_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Paypal_No_Resolve.yaml'                           , path: ./ruleset/Paypal_No_Resolve.yaml                    }
#   Wise_No_Resolve                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Wise_No_Resolve.yaml'                             , path: ./ruleset/Wise_No_Resolve.yaml                      }
#   Monzo_No_Resolve                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Monzo_No_Resolve.yaml'                            , path: ./ruleset/Monzo_No_Resolve.yaml                     }
#   Revolut_No_Resolve                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Revolut_No_Resolve.yaml'                          , path: ./ruleset/Revolut_No_Resolve.yaml                   } 
#
#
#   Paypal                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Paypal.yaml'                                      , path: ./ruleset/Paypal.yaml                               }
#   Wise                                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Wise.yaml'                                        , path: ./ruleset/Wise.yaml                                 }
#   Monzo                               : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Monzo.yaml'                                       , path: ./ruleset/Monzo.yaml                                }
#   Revolut                             : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/VirtualFinance/Revolut.yaml'                                     , path: ./ruleset/Revolut.yaml                              } 

#
# ----------------------------------
# 使用说明 ：⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️
# ----------------------------------
# 
# 本项目，包括 以下三组规则，“三选一”，选其中一个即可:
# 
# 三组的后缀，分别为：
# 
#   + 后缀：No_Resolve	（第一组）
# 
#   + 后缀：无		（第二组）
# 
#   + 后缀：Doamin		（第三组）
#   + 后缀：IP
# 
# 以上三组，三选一，优先选择最后一组（Domain + IP），在移动端（Stash for iOS），这种写法极大增加匹配速度和减少内存占用。
#
#

