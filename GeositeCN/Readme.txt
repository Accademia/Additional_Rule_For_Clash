
# -----------------------------------------
# 此规则集：用于，对中国境内网站，进行分流
# -----------------------------------------

# 用途：
#
#	与 geosite:cn （ https://github.com/v2fly/domain-list-community/blob/master/data/cn ）相同，但是注释掉了非中国服务器的域名。错误包括但不限于如下：
#		- 像什么联合国总部的域名、美国ACM论文库、牛津大学…… 都归类到中国域名当中，
#		- 还混入了tiktok相关的域名。干扰太大了😄
#		- 还有更离谱的，把人家国家的国家顶级域名，都当成中国域名的 😂 ，如 +.ms 规则 。
#		- 包括xbox.com、sony.com 此类的 ，也是同样的问题。导致美服索尼和美服xbox分流受影响。
#		- 有些域名，如工商银行美国 🇺🇸、工商银行德国🇩🇪 的域名， 你在中国连是中国，在当地国家连接就是当地国家服务器，这种明显就是CDN的。在这样的情况下，既然域名都用了当地国家的顶级域名（非CN域名），也不应该加入到中国规则中。
#
#	因为 Geosite:cn 中，有超过 25%的规则是错误规则 ，总数占6800个分流规则中的1700个是错误规则。
#	因为 Geosite:cn 中，有超过 19%的规则是冗余的（都是cn后缀域名） ，总数占6800个分流规则中的1300个是错误规则。
#	也就是说，接近 45%的规则（接近3000条规则）是错误的、冗余的，是需要被删除（被注释）的！
#   
#	目前整理后，规则总数：3792个 ：2025-12-03
#	
#
# 引用范例 ：
#
#    GeositeCN_No_Resolve                  : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/GeositeCN_No_Resolve.yaml'                                , path: ./ruleset/GeositeCN_No_Resolve.yaml                  }
#
#    GeositeCN                             : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/GeositeCN.yaml'                                           , path: ./ruleset/GeositeCN.yaml                             }
#           
#    GeositeCN_Domain                      : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeositeCN/GeositeCN_Domain.yaml'                                    , path: ./ruleset/GeositeCN_Domain.yaml                      }
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

