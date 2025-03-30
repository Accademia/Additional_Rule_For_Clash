
# -----------------------------------------
# 此规则集：用于，“Grok“和 ”xAI“，进行分流
# -----------------------------------------

# 用途：
#	访问 Grok 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    Grok_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_No_Resolve.yaml'                                    , path: ./ruleset/Grok_No_Resolve.yaml                    }    
#
#    Grok                              : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok.yaml'                                               , path: ./ruleset/Grok.yaml                               }                 
#
#    Grok_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_Domain.yaml'                                        , path: ./ruleset/Grok_Domain.yaml                        }    
#