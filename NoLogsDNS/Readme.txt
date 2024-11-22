
# -----------------------------------------
# 此规则集：用于，基于“可信DNS”，进行分流
# -----------------------------------------

# 以下DNS被排除在本列表之外：
# 	- 中国大陆DNS（DNS污染：GFW是万恶之源）
#	- 记录隐私DNS（隐私泄漏：用户行为分析）
#	- 私有DNS（隐私泄漏：用户地理位置）


# 引用范例：
#
#    NoLogsDNS_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/NoLogsDNS/NoLogsDNS_No_Resolve.yaml'                   , path: ./ruleset/NoLogsDNS_No_Resolve.yaml   }
#
#    NoLogsDNS                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/NoLogsDNS/NoLogsDNS.yaml'                              , path: ./ruleset/NoLogsDNS.yaml              }
#