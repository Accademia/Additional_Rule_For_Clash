
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