
# -----------------------------------------
# 此规则集：Homebrew App Install \ Upgrade  Clash 分流规则
# -----------------------------------------

# 用途：
#	通过homebrew 更新安装常用的 Mac App 软件 （仅包含常用的 Mac APP）
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
#    MacAppUpgrade_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MacAppUpgrade/MacAppUpgrade_No_Resolve.yaml'                                      , path: ./ruleset/MacAppUpgrade_No_Resolve.yaml                    }       
#           
#    MacAppUpgrade                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MacAppUpgrade/MacAppUpgrade.yaml'                                                 , path: ./ruleset/MacAppUpgrade.yaml    	                       }    
#           
#    MacAppUpgrade_Domain                       : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MacAppUpgrade/MacAppUpgrade_Domain.yaml'                                             , path: ./ruleset/MacAppUpgrade_Domain.yaml    		               }    
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