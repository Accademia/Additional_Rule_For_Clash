
# -----------------------------------------
# 此规则集：屏蔽 中国大陆的DNS、HttpDNS（被GFW污染波及的DNS和中国区私有DNS）
# -----------------------------------------

# 提示：
# 	主要屏蔽私有DNS（以防止被跟踪）
#


# 引用范例：
#
#    PrivateDNS_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PrivateDNS/PrivateDNS_No_Resolve.yaml'                   , path: ./ruleset/PrivateDNS_No_Resolve.yaml   }
#    PrivateDNS                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PrivateDNS/PrivateDNS.yaml'                              , path: ./ruleset/PrivateDNS.yaml              }
#