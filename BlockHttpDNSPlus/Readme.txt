
# -----------------------------------------
# 此规则集：屏蔽 APP通过“私有DNS”窥探用户隐私（地理位置），对 BlockHttpDNS 规则进行补充
# -----------------------------------------

# 提示：
# 	主要屏蔽来自中国大陆的DNS，原因： 所有中国大陆DNS，
#	 1. 都存在DNS污染
#	 2. 都100%存在隐私泄漏风险
#

# 使用说明：
#	建议与如下规则一起使用：(本规则作为如下规则的补充)
#	https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/BlockHttpDNS


# 引用范例：
#
#    BlockHttpDNSPlus_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BlockHttpDNSPlus/BlockHttpDNSPlus_No_Resolve.yaml'                   , path: ./ruleset/BlockHttpDNSPlus_No_Resolve.yaml   }
#    BlockHttpDNSPlus                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BlockHttpDNSPlus/BlockHttpDNSPlus.yaml'                              , path: ./ruleset/BlockHttpDNSPlus.yaml              }
#