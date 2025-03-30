
# -----------------------------------------
# 此规则集：用于，“腾讯微云“，进行分流
# -----------------------------------------

# 用途：
#	访问 腾讯微云 所需要的Clash分流规则
#
#

#
#
# 引用范例 ：
#
#    WeiYun_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/WeiYun/WeiYun_No_Resolve.yaml'                                      , path: ./ruleset/WeiYun_No_Resolve.yaml                    }       
#           
#    WeiYun                              : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/WeiYun/WeiYun.yaml'                                                 , path: ./ruleset/WeiYun.yaml                               }       
#
#    WeiYun_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/WeiYun/WeiYun_Domain.yaml'                                           , path: ./ruleset/WeiYun_Domain.yaml                       }    
#
#    WeiYun_IP                           : {type: http, behavior: ipcidr    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/WeiYun/WeiYun_IP.yaml'                                               , path: ./ruleset/WeiYun.yaml    		                    }    
#
#