
# -----------------------------------------
# 此规则集：用于，“AppleAI“ \ 苹果智能 ，进行分流
# -----------------------------------------

# 注意：⚠️ 对🇨🇳国行机，单纯应用本规则，无法使用 AppleAI
# 对于 中国大陆 国行设备，必须解除 以下四把锁，才能使用上 国外的AppleAI （ChatGPT for Siri）
#  1. 账号锁 （ 仅针对 中国大陆 国行机 ）
#  2. 设置锁 （ 仅针对 中国大陆 国行机 ）
#  3. LBS锁 （ 🇨🇳 中国大陆 GPS位置，无法使用ChatGPT for Siri）
#  4. IP锁 （ 🇨🇳 中国大陆 IP归属地 ，无法使用 ChatGPT for Siri）

# Github 项目，enableAppleAI，可以解除 第1、2把锁 （ 针对Mac请移步：https://github.com/kanshurichard/enableAppleAI）
# 用户自己 通过设置页面，可以解除 第3把锁
# 本规则，可以解除，第4把锁

################################################################
#  在运行 enableAppleAI 脚本前，需完成以下设置：
################################################################
#  1. 【目标：解除 账号锁】 苹果账号 必须美区ID（不能不登录ID⚠️） = iCloud 美区ID + AppStore 美区ID （两者必须同时部署非国区，缺一不可⚠️） 	
#  2. 【目标：解除 设置锁】 系统地区选择美国（至少非中国） 
#  注意： 每次大版本升级（如v26 -> v27 ），需要重新跑一遍本脚本

################################################################
# 如何强行让Siri 绑定 ChatGPT？
################################################################
# 	4. 【目标：解除 IP锁】苹果在绑定chatgpt操作过程中，是有IP锁的。只有你应用了本页面内的规则（或等价规则），才能在苹果智能扩展中正常登录Chatgpt。

################################################################
# 如何强行让Siri 调用 ChatGPT？
################################################################
#  3. 【目标：解除 LBS锁】将Siri地理位置禁用：在Mac OS中，必须在 设置 -> 隐私与安全性 -> 定位服务 -> Siri ，关闭其获取位置的能力。

# ✅✅✅✅ 只有完成上述四步，才能让Mac无缝调用ChatGPT （需要在siri输入框，敲入 “调用ChatGPT”），不然即便是非国行设备，也会调用“文心一言”。

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

