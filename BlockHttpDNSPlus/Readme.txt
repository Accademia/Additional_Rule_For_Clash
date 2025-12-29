
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



⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

 - [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88) 