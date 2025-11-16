
# -------------------------------------------------------
# 此规则集 ：
# -------------------------------------------------------
#
#   用于 ：对 苹果智能 Microsoft Copilot 进行 clash 分流




################################################################
# 本分流规则 用法 ：
################################################################
#
#	访问 Copilot 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    Copilot_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Copilot/Copilot_No_Resolve.yaml'                                    , path: ./ruleset/Copilot_No_Resolve.yaml                    }    
#
#    Copilot                              : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Copilot/Copilot.yaml'                                               , path: ./ruleset/Copilot.yaml                               }                 
#
#    Copilot_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Copilot/Copilot_Domain.yaml'                                        , path: ./ruleset/Copilot_Domain.yaml                        }   

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

