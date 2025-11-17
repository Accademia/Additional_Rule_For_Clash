
# -----------------------------------------
# 此规则集：用于，“Grok“和 ”xAI“，进行分流
# -----------------------------------------


+ xAI Grok 分流规则 ❗️❗️❗️❗️❗️

特别注意： 由于 Grok APP for iOS 存在BUG，导致 你需要在 你的yaml配置文件上，做特殊处理。请看如下

BUG根源： 由于 Grok APP for iOS ，在获得域名解析后，只会尝试连接IPV6，而不会同时尝试IPv6和IPv4，所以，只要你的DNS解析中存在IPV6解析结果，但是IPv6代理又走不通，就会导致Grok APP 在提问环节卡死，并且用户登录也登不上。（⚠️⚠️⚠️希望能有人将这个BUG反馈给 Grok APP 开发团队⚠️⚠️⚠️）。注意：web端不受影响、X客户端内的Grok也不受影响、只有在Grok APP内用文字交互受影响，如果是实时语音问答，也不受影响。

解决方案：


方法 1. 坐等xAI Grok自己修复BUG 


方法 2. 可以在Stash面板中，手动开启Tun IPv6 分流，则秒解决此问题。开启方法：

  - 开启路径为： Stash -> 设置 -> 网络设置 -> 启用 Tunnel IPV6 路由

  - ⚠️ 惩罚：在Stash上，开启IPV6支持后，会导致 手机在局域网内 观看 Apple Homekit摄像头 时，无法观看实时视频（手机在公网时 则不受影响）。且在Stash上，无论怎么设置 局域网直连规则，都无法解此问题。在Clash Meta中，可以通过 内网分流规则 从而绕开此问题。


方法 3. 如果你没有任何第三方APP依赖IPV6。也可以通过在yaml的配置文件中，关闭DNS的IPv6解析，来解决此问题。在yaml的dns模块中，修改如下配置：
  dns                       :
    enable                  : true         # 如果配置为关闭，则将仅仅使用系统 DNS    : true \ false
    ipv6                    : false        # 设置：关闭 基于IPV6的DNS查询 ✅✅✅✅✅ （这里是要更改的地方！！！！）    让DNS不返回IPV6结果，即可解决此问题。 


⚠️ 注意：方法3，无法使用在Stash 3.x中，因为这个APP不支持手动关闭IPV6解析。已经向开发者反馈多次，压根没人回复，这是服了。希望其他人看见了，向开发者反馈。 在2025年，我反馈了N次BUG向他们，居然都不回复。也不知道在想什么。




# 用途：
#	访问 Grok 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    Grok_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_No_Resolve.yaml'                                    , path: ./ruleset/Grok_No_Resolve.yaml                    }    
#
#    Grok                              : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok.yaml'                                               , path: ./ruleset/Grok.yaml                               }                 
#
#    Grok_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_Domain.yaml'                                        , path: ./ruleset/Grok_Domain.yaml                        }   
#
#    Grok_IP	                       : {type: http, behavior: ipcidr    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Grok/Grok_IP.yaml'                   	                        , path: ./ruleset/Grok_IP.yaml       	                  }   
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

