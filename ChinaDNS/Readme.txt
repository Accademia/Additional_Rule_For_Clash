
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
