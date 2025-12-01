
# -----------------------------------------
# 此规则集：用于，“PreRepairChina“，进行分流
# -----------------------------------------

# 用途：
#
#	由于 https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/China 中存在大量的非中国服务器的域名，所以需要额外的分流规则，来修复这些非中国域名带来的分流错误
#   
#   另外，强烈不推荐使用 geosite:cn 作为🇨🇳中国域名的分流方案！！此规则包含了更多的非中国域名，甚至包括了Tiktok域名😂。如果要修复，排除规则，必须包含上千条域名规则，所以放弃使用geosite:cn
#
#
# 引用范例 ：
#
#    PreRepairChina_No_Resolve                  : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairGeositeCN/PreRepairChina_No_Resolve.yaml'                                , path: ./ruleset/PreRepairChina_No_Resolve.yaml                  }
#
#    PreRepairChina                             : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairGeositeCN/PreRepairChina.yaml'                                           , path: ./ruleset/PreRepairChina.yaml                             }
#           
#    PreRepairChina_Domain                      : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/PreRepairGeositeCN/PreRepairChina_Domain.yaml'                                    , path: ./ruleset/PreRepairChina_Domain.yaml                      }
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

