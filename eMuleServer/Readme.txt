
# -----------------------------------------
# 此规则集：用于，基于“eMule目录服务器“，进行分流
# -----------------------------------------

# 用途：
#	1. 用于隐秘的连接盗版网络（避免被运营商追责）
#	2. 用于避免GFW不定时掐断与“eMule目录服务器“的连接
#
# 缺点：
#	启用此规则后，会导致只能获得 Low ID
#   
# 注意：
#   本规则，只会代理 eMule的 目录服务器，不会涉及P2P下载
#
#
# 引用范例 ：
#
#   eMuleServer_No_Resolve              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/eMuleServer/eMuleServer_No_Resolve.yaml'                         , path: ./ruleset/eMuleServer_No_Resolve.yaml  }
#
#   eMuleServer                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/eMuleServer/eMuleServer.yaml'                                    , path: ./ruleset/eMuleServer.yaml             }
#
#   eMuleServer_IP                      : {type: http, behavior: ipcidr   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/eMuleServer/eMuleServer_IP.yaml'                                 , path: ./ruleset/eMuleServer_IP.yaml          }
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

