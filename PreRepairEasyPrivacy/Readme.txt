
# -----------------------------------------
# 此规则集：用于，对“EasyPrivacy“和“AdvertisingLite”分流规则，进行修复（避免出现不连通的情况）
# -----------------------------------------

# 用途：
#	在EasyPrivacy和AdvertisingLite规则前，使用本规则！！！！

#
# 使用说明：
#
#  + 单独使用：
#       PreRepairEasyPrivacy_No_Resolve             # 要配置上代理！！（具体请看规则内部！）

#
# 配合规则：
#	在本规则后，建议直接启用：
#		EasyPrivacy_Classical_No_Resolve           https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/EasyPrivacy			（3万条规则）
#		AdvertisingLite_Classical_No_Resolve       https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/AdvertisingLite		（4万条规则）
#
# 引用范例 ：
#
#   PreRepairEasyPrivacy_No_Resolve                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairEasyPrivacy/PreRepairEasyPrivacy_No_Resolve.yaml'                                , path: ./ruleset/PreRepairEasyPrivacy_No_Resolve.yaml          }
#   PreRepairEasyPrivacy                                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairEasyPrivacy/PreRepairEasyPrivacy.yaml'                                           , path: ./ruleset/PreRepairEasyPrivacy.yaml                     }
#
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

