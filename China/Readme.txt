
# -----------------------------------------
# 此规则集：用于，对中国境内网站，进行分流
# -----------------------------------------

# 用途：
#
#	与 https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/China 相同，但是注释掉了非中国服务器的域名。错误包括但不限于如下：
#		- 像什么联合国总部的域名、美国ACM论文库、牛津大学…… 都归类到中国域名当中，
#		- 还混入了tiktok相关的域名。干扰太大了😄
#		- 还有更离谱的，把人家国家的国家顶级域名，都当成中国域名的 😂 ，如 +.ms 规则 。
#		- 包括xbox.com、sony.com 此类的 ，也是同样的问题。导致美服索尼和美服xbox分流受影响。
#		- 有些域名，如工商银行美国 🇺🇸、工商银行德国🇩🇪 的域名， 你在中国连是中国，在当地国家连接就是当地国家服务器，这种明显就是CDN的。在这样的情况下，既然域名都用了当地国家的顶级域名（非CN域名），也不应该加入到中国规则中。
#
#   
#	因为 china 中，有超过 18%的规则是错误规则 ，总数占3700个分流规则中的650个是错误规则。
#   
#	目前整理后，规则总数：3070个：2025-12-03
#
#	目前这个规则的完备性，没有 GeositeCN 好，只是其子集。GeostieCN 规则链接
#
#		https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/GeositeCN	
#
#
# 引用范例 ：
#
#    China_No_Resolve                  : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/China_No_Resolve.yaml'                                , path: ./ruleset/China_No_Resolve.yaml                  }
#
#    China                             : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/China.yaml'                                           , path: ./ruleset/China.yaml                             }
#           
#    China_Domain                      : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/China_Domain.yaml'                                    , path: ./ruleset/China_Domain.yaml                      }
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

