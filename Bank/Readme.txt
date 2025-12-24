
# -----------------------------------------
# 此规则集：用于，对 “各国银行“ 进行分流
# -----------------------------------------

# 用途：
#	在反洗钱、反欺诈 0容忍的欧美国家，连接银行账户的IP，必须是本国IP
#
#	注意：
#	  1. ⚠️⚠️⚠️ 离岸账户（如香港、新加坡的所有账户，以及非开放口岸国家的离岸账户）无需本国IP，建议本国IP直连！！注意，各国 银行的离岸账户的保底存款，会要求20～30万美金或英镑起步
#	  2. 加拿大的银行，可以使用美国IP访问，而不被封控。
#
#
# 引用范例 ：
#   BankUS_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUS_No_Resolve.yaml'                                      , path: ./ruleset/BankUS_No_Resolve.yaml                   }
#   BankUK_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUK_No_Resolve.yaml'                                      , path: ./ruleset/BankUK_No_Resolve.yaml                   }
#   BankAU_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankAU_No_Resolve.yaml'                                      , path: ./ruleset/BankAU_No_Resolve.yaml                   }
#   BankJP_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankJP_No_Resolve.yaml'                                      , path: ./ruleset/BankJP_No_Resolve.yaml                   }
#   BankHK_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankHK_No_Resolve.yaml'                                      , path: ./ruleset/BankHK_No_Resolve.yaml                   }
#   BankSG_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankSG_No_Resolve.yaml'                                      , path: ./ruleset/BankSG_No_Resolve.yaml                   }
#   BankDE_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankDE_No_Resolve.yaml'                                      , path: ./ruleset/BankDE_No_Resolve.yaml                   }
#   BankNL_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankNL_No_Resolve.yaml'                                      , path: ./ruleset/BankNL_No_Resolve.yaml                   }
#   BankFR_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankFR_No_Resolve.yaml'                                      , path: ./ruleset/BankFR_No_Resolve.yaml                   }
#
#
#   BankUS                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUS.yaml'                                                 , path: ./ruleset/BankUS.yaml                              }
#   BankUK                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUK.yaml'                                                 , path: ./ruleset/BankUK.yaml                              }
#   BankAU                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankAU.yaml'                                                 , path: ./ruleset/BankAU.yaml                              }
#   BankJP                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankJP.yaml'                                                 , path: ./ruleset/BankJP.yaml                              }
#   BankHK                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankHK.yaml'                                                 , path: ./ruleset/BankHK.yaml                              }
#   BankSG                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankSG.yaml'                                                 , path: ./ruleset/BankSG.yaml                              }
#   BankDE                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankDE.yaml'                                                 , path: ./ruleset/BankDE.yaml                              }
#   BankNL                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankNL.yaml'                                                 , path: ./ruleset/BankNL.yaml                              }
#   BankFR                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankFR.yaml'                                                 , path: ./ruleset/BankFR.yaml                              }
#
#
#   BankUS_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUS_Domain.yaml'                                          , path: ./ruleset/BankUS_Domain.yaml                       }
#   BankUK_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankUK_Domain.yaml'                                          , path: ./ruleset/BankUK_Domain.yaml                       }
#   BankAU_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankAU_Domain.yaml'                                          , path: ./ruleset/BankAU_Domain.yaml                       }
#   BankJP_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankJP_Domain.yaml'                                          , path: ./ruleset/BankJP_Domain.yaml                       }
#   BankHK_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankHK_Domain.yaml'                                          , path: ./ruleset/BankHK_Domain.yaml                       }
#   BankSG_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankSG_Domain.yaml'                                          , path: ./ruleset/BankSG_Domain.yaml                       }
#   BankDE_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankDE_Domain.yaml'                                          , path: ./ruleset/BankDE_Domain.yaml                       }
#   BankNL_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankNL_Domain.yaml'                                          , path: ./ruleset/BankNL_Domain.yaml                       }
#   BankFR_Domain                       : {type: http, behavior: domain   , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Bank/BankFR_Domain.yaml'                                          , path: ./ruleset/BankFR_Domain.yaml                       }
#
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

