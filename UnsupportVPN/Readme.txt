
# -----------------------------------------
# 此规则集：面向 不支持VPN的网站（除 银行、HomeIP 分流规则以外的 网站）
# -----------------------------------------


# 引用范例：
#
#    UnsupportVPN_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/UnsupportVPN/UnsupportVPN_No_Resolve.yaml'                   , path: ./ruleset/UnsupportVPN_No_Resolve.yaml   }
#    UnsupportVPN                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/UnsupportVPN/UnsupportVPN.yaml'                              , path: ./ruleset/UnsupportVPN.yaml              }
#
#    UnsupportVPN_Domain                    : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/UnsupportVPN/UnsupportVPN_Domian.yaml'                          , path: ./ruleset/UnsupportVPN_Domian.yaml       }
#    UnsupportVPN_IP                        : {type: http, behavior: ipcidr, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/UnsupportVPN/UnsupportVPN_IP.yaml'                              , path: ./ruleset/UnsupportVPN_IP.yaml           }


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

