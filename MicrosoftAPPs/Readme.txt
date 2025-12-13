
# -------------------------------------------------------
# 此规则集 ： 对 微软全家桶分流
# -------------------------------------------------------
#
#+ MicrosoftAPPs： 微软APP全家桶 的 Clash分流规则 
#    + 已包含 ：Windows 全家桶（ Win10、Win11 系统升级、内置应用商店下载 ）
#    + 已包含 ：Office 2019+ 、Office 365 全家桶
#        + Word、Excel、PowerPoint、Visio
#        + OneNote、OneDrive、OutLook、
#        + Hotmail、SharePoint、Skype 
#        + …
#    + 不包含 ：
#        + ❌ Copilot ：必须翻墙
#        + ❌ Bing ：建议翻墙
#        + ❌ Edge ：建议翻墙
#        + ❌ Azure微软云：包含大量第三方公司
#        + ❌ Xbox：独立业务 
#        + ❌ Github：独立业务 + 必须翻墙
#        + 建议：上述单独分流。
#        + 建议：本分流规则 不建议前置，建议安排在上述未包含的分流规则之后。
#		因为上述服务中，有些APP（如Copilot）会存在大量的子链接。
#		而本规则 使用全家桶的顶级域名，存在覆盖冲突。
#
#
#

################################################################
# 本分流规则 用法 ：
################################################################
#
#	访问 MicrosoftAPPs 所需要的Clash分流规则
#
#
# 引用范例 ：
#
#    MicrosoftAPPs_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MicrosoftAPPs/MicrosoftAPPs_No_Resolve.yaml'                                    , path: ./ruleset/MicrosoftAPPs_No_Resolve.yaml                    }    
#
#    MicrosoftAPPs                              : {type: http, behavior: classical , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MicrosoftAPPs/MicrosoftAPPs.yaml'                                               , path: ./ruleset/MicrosoftAPPs.yaml                               }                 
#
#    MicrosoftAPPs_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MicrosoftAPPs/MicrosoftAPPs_Domain.yaml'                                        , path: ./ruleset/MicrosoftAPPs_Domain.yaml                        }   
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
