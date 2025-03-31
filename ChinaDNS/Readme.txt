
# -----------------------------------------
# 此规则集：屏蔽 中国大陆的DNS、HttpDNS（被GFW污染波及的DNS和中国区私有DNS）
# -----------------------------------------

# 提示：
# 	主要筛选来自中国大陆的DNS，原因： 所有中国大陆DNS，
#	 1. 都存在DNS污染
#	 2. 都100%存在隐私泄漏风险
#


# 引用范例：
#
#    ChinaDNS_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/ChinaDNS/ChinaDNS_No_Resolve.yaml'                   , path: ./ruleset/ChinaDNS_No_Resolve.yaml   }
#    ChinaDNS                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/ChinaDNS/ChinaDNS.yaml'                              , path: ./ruleset/ChinaDNS.yaml              }
#
#    ChinaDNS_Domain                    : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/ChinaDNS/ChinaDNS_Domian.yaml'                          , path: ./ruleset/ChinaDNS_Domian.yaml       }
#    ChinaDNS_IP                        : {type: http, behavior: ipcidr, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/ChinaDNS/ChinaDNS_IP.yaml'                              , path: ./ruleset/ChinaDNS_IP.yaml           }


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

