
# -----------------------------------------
# 此规则集：用于，“AppleAI“ \ 苹果智能 ，进行分流
# -----------------------------------------


# 本规则需要与苹果AI捆绑使用，国行Mac没有苹果AI，如何强行开启苹果AI 请看项目enableAppleAI

# 关于 国行 Mac OS 强行启用Apple AI，请移步这个项目，https://github.com/kanshurichard/enableAppleAI
# 此项目配置 ，需满足：
# 	1. 必须美区ID（不能不登录ID） + 系统地区选择美国（至少非中国） 
#         美区ID = iCloud 美区ID + AppStore 美区ID （两者同时部署） 	
#	  2. 将Siri地理位置禁用（如上述）
#	  3. 每次大版本升级（如v26 -> v27 ），需要重新跑一遍本脚本


# 如何强行让Siri绑定ChatGPT？
# 	1. 苹果在绑定chatgpt操作过程中，是有IP锁的。只有你应用了本页面内的规则（或等价规则），才能在苹果智能扩展中正常登录Chatgpt。

# 如何强行让Siri强行调用ChatGPT？而不是文心一言？
#	1. 苹果在搜索和Siri过程中，是否调用chatgpt，是有LBS锁的。苹果会通过GPS等位置来判定你是否在中国，如果在，则不会调用ChatGPT。只会调用文心一言。所以仅仅即便配置 本规则+登录Chat GPT，但如果你GPS在中国，苹果AI也不会调用ChatGPT，而是会调用百度文心一言。
#	2.如何解决上述限制？此时必须禁用siri的地理位置获取，才能让苹果AI调用ChatGPT。
#	3.如何禁用Siri地理位置获取？ 操作如下：在Mac OS中，必须在 设置 -> 隐私与安全性 -> 定位服务 -> Siri ，关闭其获取位置的能力，才能让AppleAI默认调用chatGPT （配合代AppleAI理规则 ！！！！！！！

# 规则已经被命中，但是连接不上怎么办？
#   1. 你要检查，你的VPN是否使用了链式代理（或者不健全的节点协议），因为苹果智能大量使用了Quic。如果你VPN链路不支持Quic，可能会引发问题。（ 实际上Grok AI也是一样的，由于Grok APP 反复尝试IPV6连接，导致不支持IPv6的网络，会数分钟都连接不上Grok ）

# 用途：
#	访问 AppleAI 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    AppleAI_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI_No_Resolve.yaml'                                    , path: ./ruleset/AppleAI_No_Resolve.yaml                    }    
#
#    AppleAI                              : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI.yaml'                                               , path: ./ruleset/AppleAI.yaml                               }                 
#
#    AppleAI_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI_Domain.yaml'                                        , path: ./ruleset/AppleAI_Domain.yaml                        }   

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

