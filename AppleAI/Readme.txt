
# -----------------------------------------
# 此规则集：用于，“AppleAI“ \ 苹果智能 ，进行分流
# -----------------------------------------


# ⚠️⚠️ 特别注意：在Mac OS中，必须在 设置 -> 隐私与安全性 -> 定位服务 -> Siri ，关闭其获取位置的能力，才能让AppleAI的IP代理生效 ！！！！！！！


# 关于 国行 Mac OS 强行启用Apple AI，请移步这个项目，https://github.com/kanshurichard/enableAppleAI
# 此项目配置 ，需满足：
# 	1. 必须美区ID（不能不登录ID） + 系统地区选择美国（至少非中国） 
#	2. 将Siri地理位置禁用（如上述）
#	3. 每次大版本升级（如v26 -> v27 ），需要重新跑一遍本脚本

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
#    AppleAI_IP	                       : {type: http, behavior: ipcidr    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleAI/AppleAI_IP.yaml'                   	                        , path: ./ruleset/AppleAI_IP.yaml       	                  }   
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

