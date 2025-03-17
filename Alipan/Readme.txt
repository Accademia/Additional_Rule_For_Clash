
# -----------------------------------------
# 此规则集：用于，“阿里云盘、阿里网盘“，进行分流
# -----------------------------------------

# 用途：
#	访问 阿里网盘 所需要的Clash分流规则
#
#
# 注意：
#	强烈不建议使用阿里云盘，这是我见过最流氓的云盘，没有之一。每次启动会 强制将云盘加入启动项，后台静默扫描硬盘，而且数据无加密明文存储在云盘，总之，除了网速比百度网盘快之外，其他任何一个方面，都比百度网盘还流氓一百倍！！ 强烈不建议使用。
#
#
#
# 引用范例 ：
#
#    Alipan_No_Resolve                   : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Alipan/Alipan_No_Resolve.yaml'                                      , path: ./ruleset/Alipan_No_Resolve.yaml                    }       
#           
#    Alipan                              : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Alipan/Alipan.yaml'                                                 , path: ./ruleset/Alipan.yaml    		                }    