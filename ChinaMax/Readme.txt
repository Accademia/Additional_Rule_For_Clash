
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


为什么 原版 geosite 、 原版 chinamax 会有错误？ 精准的标准是什么？ 到底什么叫🇨🇳 中国分流规则？ 到底怎么定义 🇨🇳 中国规则？

或者说，到底什么样的域名，才能被放进中国规则当中？

1. 在中国大陆，有根dns的 “域名” ，是否应该被收录到 🇨🇳 “中国域名”分流规则中  ？
    - 这里面，会包含 🌍 境外域名，甚至被gfw阻断的境外域名

2. 在中国大陆，能直连的 “域名”，是否应该被收录到 🇨🇳 “中国域名”分流规则中 ？
    - 这里面，也会包含 🌍 境外域名，如：没有被gfw封锁的境外域名

3. 中国公司的 “域名” ，是否应该被收录到 🇨🇳 “中国域名”分流规则中  ？
    - 这里面，也会包含 🌍 境外域名，如：中国公司自己运营的境外域名 ，如快手国际版 kwai、 抖音国际版 tiktok

4. 被中国GEOIP命中的 “域名” （IP归属地 是中国的域名），是否应该被收录到 🇨🇳 “中国域名”分流规则中 ？ 
    - 这里面，依然会包含 🌍 境外域名 。如：在中国有cdn服务器的，任意境外域名

5. 同时满足 以下三大条件的域名，是否应该被收录到 🇨🇳 “中国域名”分流规则中 ？
   条件 1 ： 域名是 ip归属地🇨🇳中国
   条件 2 ： 域名是 非 .us \ .hk \ .tw 等 其它国家地区等级域名
   条件 3 ： 域名是 非 带有 -us-west / -eu-east 等地理位置的cdn域名
   条件 4 ： 域名虽同时满足以上三点，但添加后，境外app服务，会被屏蔽的域名（如tiktok、kwai）
    - 这里面，依然会包含 🌍 境外域名 🤣🤣 。 如：在中国cdn服务器的，任意境外域名。


对上述四种，

- 原版 chinamax = 类别 1 （精度最差）❌❌❌❌❌

- 原版 geosite:cn = 类别 3 (精度比较差） ⚠️⚠️⚠️ （会导致 tiktok等无法登陆）

- 修正后的GeositeCN = 类别 5  （ 精度 100% 正确 ）✅

- 修正后的ChinaMax（本规则集） = 只能满足 类别5 中的 条件1 + 条件2 ⚠️



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

