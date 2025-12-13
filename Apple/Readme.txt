
# -------------------------------------------------------
# 此规则集 ： 对 苹果分流
# -------------------------------------------------------
#
#   用于 ：对 苹果分流

#   注意：
#       1. 苹果公司经过40年的发展，曾用过的域名，高达1500个。其中大量都废弃了。本规则，只保留目前iphone、macbook、ipad 等苹果公司，还在使用的域名
#       2. 不收录 云上贵州、中国区苹果 的分流，那些直接走geosite:cn

################################################################
# 本分流规则 用法 ：
################################################################
#
#	访问 Apple 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    Apple_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple_No_Resolve.yaml'                                    , path: ./ruleset/Apple_No_Resolve.yaml                    }    
#
#    Apple                              : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple.yaml'                                               , path: ./ruleset/Apple.yaml                               }                 
#
#    Apple_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple_Domain.yaml'                                        , path: ./ruleset/Apple_Domain.yaml                        }   
#    Apple_IP                           : {type: http, behavior: ipcidr    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Apple/Apple_IP.yaml'                                            , path: ./ruleset/Apple_IP.yaml                            }   

#

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
