
# -----------------------------------------
# 此规则集：用于，“Parsec“，进行分流
# -----------------------------------------

# 用途：
#	访问 Parsec 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    Parsec_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Parsec/Parsec_No_Resolve.yaml'                                   , path: ./ruleset/Parsec_No_Resolve.yaml                    }      
#            
#    Parsec                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Parsec/Parsec.yaml'                                              , path: ./ruleset/Parsec.yaml                               }       