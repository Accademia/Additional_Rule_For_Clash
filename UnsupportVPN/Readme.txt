
# -----------------------------------------
# 此规则集：面向 不支持VPN的网站（除 银行、HomeIP 分流规则以外的 网站）
# -----------------------------------------


# 引用范例：
#
#    UnsupportVPN_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/UnsupportVPN/UnsupportVPN_No_Resolve.yaml'                   , path: ./ruleset/UnsupportVPN_No_Resolve.yaml   }
#    UnsupportVPN                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/UnsupportVPN/UnsupportVPN.yaml'                              , path: ./ruleset/UnsupportVPN.yaml              }
#
#    UnsupportVPN_Domain                    : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/UnsupportVPN/UnsupportVPN_Domian.yaml'                          , path: ./ruleset/UnsupportVPN_Domian.yaml       }


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


  + 与HomeIP分流规格的区别，如 ： 
     - HomeIPUS     = 必须 🇺🇸 美国住宅IP 才能访问的网站
     - UnsupportVPN = 只要是 非机房IP / 非VPN IP ，都能访问的网站（无论是否是住宅IP，无论是否是对方国家的IP，只要是非机房IP，直连也能访问）

<br>

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

 - [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88) 