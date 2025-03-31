
# -----------------------------------------
# 此规则集：用于，对 必须“住宅IP“才能访问的网站 进行分流
# -----------------------------------------

# 用途：
#	各国总有一些网站，限制必须使用住宅IP（双ISP住宅IP），才能正常访问（或购买下单）
#	这里罗列各国此类网站
#	
# 注意：
#	视频音频网站不包含在内
#
#
# 引用范例 ：

#   HomeIPUS_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HomeIP/HomeIPUS_No_Resolve.yaml'                                , path: ./ruleset/HomeIPUS_No_Resolve.yaml                  }
#   HomeIPJP_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/HomeIP/HomeIPJP_No_Resolve.yaml'                                , path: ./ruleset/HomeIPJP_No_Resolve.yaml                  }

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

