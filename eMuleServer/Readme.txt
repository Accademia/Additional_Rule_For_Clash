
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
#
# 引用范例 ：
#
#   eMuleServer_No_Resolve              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/eMuleServer/eMuleServer_No_Resolve.yaml'                         , path: ./ruleset/eMuleServer_No_Resolve.yaml  }
#
#   eMuleServer                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/eMuleServer/eMuleServer.yaml'                                    , path: ./ruleset/eMuleServer.yaml             }
#
                                             