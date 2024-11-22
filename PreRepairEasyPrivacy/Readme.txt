
# -----------------------------------------
# 此规则集：用于，对“EasyPrivacy“和“AdvertisingLite”分流规则，进行修复（避免出现不连通的情况）
# -----------------------------------------

# 用途：
#	1. 在EasyPrivacy和AdvertisingLite规则前，使用本规则！！！！
#	2. PreRepairEasyPrivacy_Reject_No_Resolve 用于补充EasyPrivacy_Classical_No_Resolve未拦截（但必要的）隐私保护规则
#	3. PreRepairEasyPrivacy_Direct_No_Resolve 用户放行EasyPrivacy_Classical_No_Resolve误拦截的规则
#
# 使用说明：
#	PreRepairEasyPrivacy_Reject_No_Resolve 和 PreRepairEasyPrivacy_Direct_No_Resolve 建议同行使用，
#
#
# 配合规则：
#	在本规则后，建议直接启用：
#		EasyPrivacy_Classical_No_Resolve           https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/EasyPrivacy			（3万条规则）
#		AdvertisingLite_Classical_No_Resolve       https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/AdvertisingLite		（4万条规则）
#
# 引用范例 ：
#
#   PreRepairEasyPrivacy_Reject_No_Resolve              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairEasyPrivacy/PreRepairEasyPrivacy_Reject_No_Resolve.yaml'                         , path: ./ruleset/PreRepairEasyPrivacy_Reject_No_Resolve.yaml  }
#
#   PreRepairEasyPrivacy_Direct_No_Resolve              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairEasyPrivacy/PreRepairEasyPrivacy_Direct_No_Resolve.yaml'                         , path: ./ruleset/PreRepairEasyPrivacy_Direct_No_Resolve.yaml  }
                                             