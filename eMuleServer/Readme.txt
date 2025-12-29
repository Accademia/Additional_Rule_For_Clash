
# -----------------------------------------
# 此规则集：用于，基于“eMule目录服务器“，进行分流
# -----------------------------------------

# 用途：
#	1. 用于隐秘的连接盗版网络（避免被运营商追责）
#	2. 用于避免GFW不定时掐断与“eMule目录服务器“的连接
#
# 缺点：
#	启用此规则后，会导致只能获得 Low ID
#   
# 注意：
#   本规则，只会代理 eMule的 目录服务器，不会涉及P2P下载
#
#
# 引用范例 ：
#
#   eMuleServer_No_Resolve              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/eMuleServer/eMuleServer_No_Resolve.yaml'                         , path: ./ruleset/eMuleServer_No_Resolve.yaml  }
#
#   eMuleServer                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/eMuleServer/eMuleServer.yaml'                                    , path: ./ruleset/eMuleServer.yaml             }
#
#   eMuleServer_IP                      : {type: http, behavior: ipcidr   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/eMuleServer/eMuleServer_IP.yaml'                                 , path: ./ruleset/eMuleServer_IP.yaml          }
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


<br>

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

 - [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88) 