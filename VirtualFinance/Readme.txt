
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