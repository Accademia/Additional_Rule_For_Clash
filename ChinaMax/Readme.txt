
# -----------------------------------------
# 此规则集：用于，对中国境内网站，进行分流
# -----------------------------------------

# 用途：
#
#	与 https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaMax 相同，但是注释掉了非中国服务器的域名。。
#
#   
#	因为 ChinaMax 中，有超过 19000 规则是错误规则 ，总数占 117014 个分流规则中的 17% 是错误规则。
#   
#	目前整理后，规则总数：98500 个  ： 2025-12-20
#
#
#


为什么 原版 geosite 、 原版 ChinaMaxmax 会有错误？ 精准的标准是什么？ 到底什么叫🇨🇳 中国分流规则？ 到底怎么定义 🇨🇳 中国规则？

或者说，到底什么样的域名，才能被放进中国规则当中？

1. 在中国大陆，有根dns的 “域名” ？
    - 这里面会包含 境外域名，甚至被gfw阻断的境外域名

2. 在中国大陆，能直连的 “域名” ？
    - 这里面也会包含 境外域名，但只包含没有被gfw封锁的境外域名

3. 中国公司的 “域名” ？
    - 这里面也会包含 境外域名，但只包含中国公司自己运营的境外域名 ，如快手国际版 kwai、 抖音国际版 tiktok

4. 被中国GEOIP命中的 “域名” ？ 
    - 这里面也会包含 境外域名。但只包含 在中国cdn服务器的境外域名。


对上述四种，

  - 最精准的 = 类别 4  （ 本项目 ）

  - 原版 geosite cn = 类别 3

  - 原版 ChinaMaxmax = 类别 1




#
# 引用范例 ：
#
#    ChinaMax_No_Resolve                  : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/ChinaMax_No_Resolve.yaml'                                , path: ./ruleset/ChinaMax_No_Resolve.yaml                  }
#
#    ChinaMax                             : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/ChinaMax.yaml'                                           , path: ./ruleset/ChinaMax.yaml                             }
#           
#    ChinaMax_Domain                      : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/ChinaMax_Domain.yaml'                                    , path: ./ruleset/ChinaMax_Domain.yaml                      }
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

