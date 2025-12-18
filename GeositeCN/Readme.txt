
# -----------------------------------------
# 此规则集：用于，对中国境内网站，进行分流
# -----------------------------------------

# 用途：
#
#	与 geosite:cn （ https://github.com/v2fly/domain-list-community/blob/master/data/cn ）相同，但是注释掉了非中国服务器（不满足GeoIP:CN）的域名  以及注释了 cn后缀的二级域名（只保留 “*.cn” 一条规则）。
#
#	- 错误包括但不限于如下：
#		- 像什么各种美国、香港、欧盟的域名…… 都归类到中国域名当中，
#		- 还混入了tiktok相关的域名。干扰太大了😄
#		- 有些域名，如工商银行美国 🇺🇸、工商银行德国🇩🇪 的域名， 你在中国连是中国，在当地国家连接就是当地国家服务器，这种明显就是CDN的。在这样的情况下，既然域名都用了当地国家的顶级域名（非CN域名），也不应该加入到中国规则中。
#
#	- 数据汇总：
#		- geosite:cn 中，有超过 8%的规则是指向境外IP的域名 ，总数占6800个分流规则中的530多个是错误规则。
#		- geosite:cn 中，有超过 19%的规则是冗余的（都是cn后缀域名） ，总数占6800个分流规则中的1300多个是错误规则。
#		- 也就是说，接近 27%的规则（接近1900条规则）是错误的、冗余的，是需要被删除（被注释）的！
#
#		-   修正后，已包括 China规则（ https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/China ）内 97% 的规则。而 频度极低 + 完全冷门 的约100个规则，没有被包括在内。可以检查源代码，结尾处，注释掉的规则。
#   
#	目前整理后，规则总数：4800余行 ：2025-12-03
#	
#

为什么geosite和 chinamax 会有错误？ 精准的标准是什么？ 到底什么叫🇨🇳 中国分流规则？ 到底怎么定义 🇨🇳 中国规则？

1. 在中国大陆，有根dns的域名 
    - 包括境外域名，甚至被gfw阻断的境外域名

2. 在中国大陆，能直连的域名 
    - 包含境外域名，但只包括没有被gfw封锁的境外域名

3. 中国公司的域名
    - 包含境外域名，但只包括中国公司自己运营的境外域名 ，如快手国际版 kwai、 抖音国际版 tiktok

4. 被中国GEOIP命中的域名 
    - 包括境外域名。但只包括 在中国cdn服务器的境外域名。


对上述四种，

- 最精准的 = 类别 4  （ 本项目 ）

- 原版 geosite cn = 类别 3

- 原版 chinamax = 类别 1

#
# 用法：
#
#	如果想达到最佳使用效果，一定要，先在 “DNS分流” 阶段，启用GeositeCN（指向国内DNS服务器）❕❕❕❕ 然后在 “分流规则” 阶段，再启用GeositeCN。
#
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

