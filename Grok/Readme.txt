
# -----------------------------------------
# 此规则集：用于，“Grok“和 ”xAI“，进行分流
# -----------------------------------------


+ xAI Grok 分流规则 ❗️❗️❗️❗️❗️

	如果在 Stash For iOS 上使用 Grok分流规则，必须在Stash面板中，手动开启IPv6分流，不然Grok APP for iOS 会非常难以连接。甚至无法连接 ！！！！！！！ 




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
#    Grok_IP	                       : {type: http, behavior: ipcidr    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_IP.yaml'                   	                        , path: ./ruleset/Grok_IP.yaml       	                  }   
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

