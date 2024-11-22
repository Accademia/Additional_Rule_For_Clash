
# -----------------------------------------
# 此规则集：用于，对 “各国银行“ 进行分流
# -----------------------------------------

# 用途：
#	在反洗钱、反欺诈 0容忍的欧美国家，连接银行账户的IP，必须是本国IP
#	注意：离岸账户无需本国IP，所以，可以不引用HK、SG规则。
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