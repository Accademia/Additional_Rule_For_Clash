
# -----------------------------------------
# 此规则集：用于，加速访问 网速极慢的站点的，进行分流
# -----------------------------------------

# 用途：
#	有些网站，虽然没有被GFW屏蔽，但是网速访问极慢，这会导致 Brew Upgrade 或 WinGet 在自动更新时，因网速过慢，而导致卡住（下载等待时间过长）。所以，将此类网站归类，使用分流规则进行加速（注意，此列表仅仅针对中国地区的用户）
#
#
# 本规则通过Mac的批处理脚本生成（脚本编写来自 xAI Grok DeepThink）：
# 	- usercmd_brewlist_to_ruleset_parallel		# 并行执行
# 	- usercmd_brewlist_to_ruleset_serial		# 串行执行
# 两个程序效果是相同的，建议优先使用并行执行，500个Mac App串行执行需30分钟，而并行执行只需要2分钟。
# 执行结果会生成在 ～/Downloads/clash_rules.yaml
#
#
#
# 引用范例 ：
#
#    MacAppDownload_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MacAppDownload/MacAppDownload_No_Resolve.yaml'                                      , path: ./ruleset/MacAppDownload_No_Resolve.yaml                    }       
#           
#    MacAppDownload                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MacAppDownload/MacAppDownload.yaml'                                                 , path: ./ruleset/MacAppDownload.yaml    	                       }    
#           
#    MacAppDownload_Domain                       : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MacAppDownload/MacAppDownload_Domain.yaml'                                             , path: ./ruleset/MacAppDownload_Domain.yaml    		               }    
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