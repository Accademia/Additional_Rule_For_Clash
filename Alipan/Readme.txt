
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
#    Alipan_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Alipan/Alipan_No_Resolve.yaml'                                      , path: ./ruleset/Alipan_No_Resolve.yaml                    }       
#           
#    Alipan                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Alipan/Alipan.yaml'                                                 , path: ./ruleset/Alipan.yaml    	                       }    
#           
#    Alipan_Domain                       : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Alipan/Alipan_Domain.yaml'                                             , path: ./ruleset/Alipan_Domain.yaml    		               }    
#
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