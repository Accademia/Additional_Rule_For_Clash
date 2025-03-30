
# -----------------------------------------
# 此规则集：用于，“RustDesk“，进行分流
# -----------------------------------------

# 用途：
#	访问 RustDesk 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    RustDesk_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/RustDesk/RustDesk_No_Resolve.yaml'                                   , path: ./ruleset/RustDesk_No_Resolve.yaml                    }       
#
#    RustDesk                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/RustDesk/RustDesk.yaml'                                              , path: ./ruleset/RustDest.yaml                               }                             
#
#    RustDesk_Domain                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/RustDesk/RustDesk_Domain.yaml'                                       , path: ./ruleset/RustDesk_Domain.yaml                        }       
#