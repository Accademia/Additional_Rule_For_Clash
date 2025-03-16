
# -----------------------------------------
# 此规则集：屏蔽 HttpDNS
# -----------------------------------------


# 使用说明：
#	建议与如下规则一起使用：(本规则，可作为如下规则的补充)
#	https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/BlockHttpDNS


# 引用范例：
#
#    HttpDNS_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BlockHttpDNSPlus/BlockHttpDNSPlus_No_Resolve.yaml'                   , path: ./ruleset/BlockHttpDNSPlus_No_Resolve.yaml   }
#    HttpDNS                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BlockHttpDNSPlus/BlockHttpDNSPlus.yaml'                              , path: ./ruleset/BlockHttpDNSPlus.yaml              }
#