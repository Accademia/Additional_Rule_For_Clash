
# -----------------------------------------
# 此规则集：用于，“AppleAI“ \ 苹果智能 \ apple intelligence ，进行 clash 分流
# -----------------------------------------

# 注意：⚠️ 对🇨🇳国行机，单纯调用本规则，无法切换到 美区苹果智能 （ 🇺🇸 apple intelligence ）
# 对于 中国大陆 国行设备，必须解除 以下四把锁，才能使用上 🇺🇸 美国的苹果智能 （ChatGPT for Siri）
#  1. 账号锁 （ 仅针对 中国大陆 国行机 ）
#  2. 设置锁 （ 仅针对 中国大陆 国行机 ）
#  3. LBS锁 （ 设备监测到，GPS位置 位于 🇨🇳 中国大陆 ，则无法使用 ChatGPT for Siri ）
#  4. IP锁 （ 设备监测到，IP归属地 位于 🇨🇳 中国大陆 ，则无法使用 ChatGPT for Siri ）

# 第1、2把锁 ：通过 enableAppleAI，可以解除 （ 移步：https://github.com/kanshurichard/enableAppleAI ）
# 第3把锁 ：通过 系统设置，可以解除 
# 第4把锁 ：通过 分流规则，可以解除，

# 如果你是 非国行机，只需要关注 第3、4把锁的解除。

################################################################
#  在运行 enableAppleAI 脚本前，需完成以下设置：
################################################################
#  1. 【目标：解除 账号锁】 苹果账号 必须美区ID（不能不登录ID⚠️） 
#        美区ID = iCloud 美区ID + AppStore 美区ID （两者 缺一不可⚠️） 
#  2. 【目标：解除 设置锁】 系统地区选择美国（至少非中国） 
#        设置 -> 通用 -> 语言与地区 -> 地区 ->  美国
#
#  完成上述两步设置后，运行 按照enableAppleAI的规范，去运行脚本（注意，运行前必须关闭SIP，运行后可重新开启）
#
#  注意： 每次大版本升级（如v26 -> v27 ），需要重新跑一遍本脚本
#        ⚠️ 非国行mac、iPhone、iPad，无需 这一步操作
#        ❌ 国行iOS、iPadOS，无法解除这两把锁（无法切换到🇺🇸苹果智能）

################################################################
# 如何强行让Siri 绑定 ChatGPT？
################################################################
# 	4. 【目标：解除 IP锁】 应用 “本分流规则 + chatgpt分流规则” 后，即可绑定

################################################################
# 如何强行让Siri 调用 ChatGPT？
################################################################
#  3. 【目标：解除 LBS锁】将Siri地理位置禁用：
#        设置 -> 隐私与安全性 -> 定位服务 -> Siri （关闭）
#
#  注意 ⚠️ ：即便是非国行机，哪怕已使用了本分流规则，如果不进行这一步操作，Siri仍然会调用“文心一言”，而不是ChatGPT。


# ✅✅✅✅ 全部完成 上述 所有四步，才能让 🇨🇳 国行Mac ，无缝调用 🇺🇸 美区 AppleAI （苹果智能） 

# ✅✅✅✅ 只要做完 上述 最后两步，就可让 非国行 Mac 、iPhone ，无缝调用 🇺🇸 美区AppleAI （ ChatGPT for Siri ）

# ❌❌❌❌ 没有方法，能让 🇨🇳 国行iOS ， 调用 🇺🇸 美区 AppleAI（苹果智能）

# 规则已经被命中，但是连接不上怎么办？
#   1. 你要检查，你的VPN是否使用了链式代理（或者不健全的节点协议），因为苹果智能大量使用了Quic。如果你VPN链路不支持Quic，可能会引发问题。（ 实际上Grok AI也是一样的，由于Grok APP 反复尝试IPV6连接，导致不支持IPv6的网络，会数分钟都连接不上Grok ）

# 本分流规则 用法：
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

