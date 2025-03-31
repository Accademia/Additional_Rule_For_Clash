
# -----------------------------------------
# 此规则集：用于补充Hijacking规则
# -----------------------------------------

# 屏蔽了什么？
#	中国反诈中心 相关网址

#  使用说明：
#	本规则可以与如下规则一起使用：
#	https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Hijacking


# 引用范例：
#
#    HijackingPlus_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HijackingPlus/HijackingPlus_No_Resolve.yaml'                   , path: ./ruleset/HijackingPlus_No_Resolve.yaml   }
#    HijackingPlus                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HijackingPlus/HijackingPlus.yaml'                              , path: ./ruleset/HijackingPlus.yaml              }
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

