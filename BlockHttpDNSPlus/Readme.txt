
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

# 注意： 
#
#  由于使用了关键词匹配，所以不存在Domain规则。

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

