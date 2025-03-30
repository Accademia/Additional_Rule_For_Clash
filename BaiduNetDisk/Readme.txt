
# -----------------------------------------
# 此规则集：用于，“百度网盘“，进行分流
# -----------------------------------------

# 用途：
#	访问 百度网盘 所需要的Clash分流规则
#
#

#
#
# 引用范例 ：
#
#    BaiduNetDisk_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BaiduNetDisk/BaiduNetDisk_No_Resolve.yaml'                                      , path: ./ruleset/BaiduNetDisk_No_Resolve.yaml                 }       
#           
#    BaiduNetDisk                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BaiduNetDisk/BaiduNetDisk.yaml'                                                 , path: ./ruleset/BaiduNetDisk.yaml    		                }    
#
#    BaiduNetDisk_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BaiduNetDisk/BaiduNetDisk_Domain.yaml'                                           , path: ./ruleset/BaiduNetDisk_Domain.yaml                    }       
