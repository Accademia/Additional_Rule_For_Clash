
# -----------------------------------------
# 此规则集：用于，对“EasyPrivacy“和“AdvertisingLite”分流规则，进行修复（避免出现不连通的情况）
# -----------------------------------------

# 用途：
#	1. 在EasyPrivacy和AdvertisingLite规则前，使用本规则！！！！
#	2. PreRepairEasyPrivacy_Reject_No_Resolve (建议拒绝)：用于补充EasyPrivacy_Classical_No_Resolve + AdvertisingLite_Classical_No_Resolve 未拦截（但必要的）隐私保护规则
#	3. PreRepairEasyPrivacy_Direct_No_Resolve (建议直连)：用户放行EasyPrivacy_Classical_No_Resolve + AdvertisingLite_Classical_No_Resolve 误拦截的规则
#	4. PreRepairEasyPrivacy_Proxy_No_Resolve  (建议代理)：用户放行EasyPrivacy_Classical_No_Resolve + AdvertisingLite_Classical_No_Resolve 误拦截的规则，但必须套上代理
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
#   PreRepairEasyPrivacy_Direct_No_Resolve              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairEasyPrivacy/PreRepairEasyPrivacy_Direct_No_Resolve.yaml'                         , path: ./ruleset/PreRepairEasyPrivacy_Direct_No_Resolve.yaml  }
#   PreRepairEasyPrivacy_Proxy_No_Resolve               : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairEasyPrivacy/PreRepairEasyPrivacy_Proxy_No_Resolve.yaml'                          , path: ./ruleset/PreRepairEasyPrivacy_Proxy_No_Resolve.yaml   }
#                                             
#
#   PreRepairEasyPrivacy_Reject                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairEasyPrivacy/PreRepairEasyPrivacy_Reject.yaml'                                    , path: ./ruleset/PreRepairEasyPrivacy_Reject.yaml             }
#   PreRepairEasyPrivacy_Direct                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairEasyPrivacy/PreRepairEasyPrivacy_Direct.yaml'                                    , path: ./ruleset/PreRepairEasyPrivacy_Direct.yaml             }
#   PreRepairEasyPrivacy_Proxy                          : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairEasyPrivacy/PreRepairEasyPrivacy_Proxy.yaml'                                     , path: ./ruleset/PreRepairEasyPrivacy_Proxy.yaml              }



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



#  这里要特别声明一下： 
#  宁波上官科技有限公司，此公司，是我见见过的最恶心的中国MAC软件公司之一，区别对待中国人和外国人，其homebrew更新和安装，只能外国人使用。对所有中国用户进行屏蔽。妥妥的中国人与狗不得入内。而且还窥探用户隐私！无耻至极！！！！不信的可以执行这条命令试试：
#    brew reinstall --force --cask flykey
#  结果必然是403错误，也就意味着中国IP不能使用Homebrew下载他们的APP。。妥妥的中国人与狗不得入内。
# 
#  这也就是为什么规则中会有如下规则 ：  - DOMAIN-SUFFIX ,  better365.cn  

