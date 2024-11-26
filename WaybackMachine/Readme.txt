
# -----------------------------------------
# 此规则集：用于，基于“网络时光机（ WaybackMachine \ archive.org ）“ 进行分流
# -----------------------------------------

# 用途：
#	中国大陆由于GFW，无法直连 archive.org
#
#
# 引用范例 ：
#
#   WaybackMachine_No_Resolve              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/WaybackMachine/WaybackMachine_No_Resolve.yaml'                         , path: ./ruleset/WaybackMachine_No_Resolve.yaml  }
#   WaybackMachine                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/WaybackMachine/WaybackMachine.yaml'                                    , path: ./ruleset/WaybackMachine.yaml             }
#
                                             