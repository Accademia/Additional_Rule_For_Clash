
# -----------------------------------------
# 此规则集：用于，“Pornhub“，进行分流
# -----------------------------------------

# 用途：
#	访问 Pornhub 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    Pornhub_No_Resolve                  : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Pornhub/Pornhub_No_Resolve.yaml'                                , path: ./ruleset/Pornhub_No_Resolve.yaml                  }
#
#    Pornhub                             : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Pornhub/Pornhub.yaml'                                           , path: ./ruleset/Pornhub.yaml                             }
#           
#    Pornhub_Domain                      : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Pornhub/Pornhub_Domain.yaml'                                    , path: ./ruleset/Pornhub_Domain.yaml                      }
#                                  