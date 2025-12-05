
# -----------------------------------------
# 此规则集：用于，基于GeoIP的地理位置，进行分流
# -----------------------------------------
#
# 用途：根据目的网站的IP，选取最近国家的VPS代理节点进行分流（通过GeoIP） 
#
# 使用建议：
#
# 	1. 不建议使用_No_Resolve版本		（不做域名解析，则无法充分分流）
# 	2. 安排在Final兜底规则前，做最后的分流	（以避免影响到其他网站的专属分流控制）
#	3. 安排在Gfwlist分流后。			（以防止敏感域名请求中国大陆DNS解析，而导致泄漏）
#   4, 对于白名单分流来说，不可替代Final （有些IP并没有包括在GeoIP当中，还需要Final做最后的兜底）
#
# 引用范例：
#
#  GeoRouting_America_North_GeoIP                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_America_North_GeoIP.yaml'                     , path: ./ruleset/GeoRouting_America_North_GeoIP.yaml                 }
#  GeoRouting_America_South_GeoIP                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_America_South_GeoIP.yaml'                     , path: ./ruleset/GeoRouting_America_South_GeoIP.yaml                 }
#  GeoRouting_Europe_West_GeoIP                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Europe_West_GeoIP.yaml'                       , path: ./ruleset/GeoRouting_Europe_West_GeoIP.yaml                   }
#  GeoRouting_Europe_East_GeoIP                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Europe_East_GeoIP.yaml'                       , path: ./ruleset/GeoRouting_Europe_East_GeoIP.yaml                   }
#  GeoRouting_Oceania_GeoIP                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Oceania_GeoIP.yaml'                           , path: ./ruleset/GeoRouting_Oceania_GeoIP.yaml                       }
#  GeoRouting_Antarctica_GeoIP                        : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Antarctica_GeoIP.yaml'                        , path: ./ruleset/GeoRouting_Antarctica_GeoIP.yaml                    }
#  GeoRouting_Asia_East_GeoIP                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_East_GeoIP.yaml'                         , path: ./ruleset/GeoRouting_Asia_East_GeoIP.yaml                     }
#  GeoRouting_Asia_EastSouth_GeoIP                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_EastSouth_GeoIP.yaml'                    , path: ./ruleset/GeoRouting_Asia_EastSouth_GeoIP.yaml                }
#  GeoRouting_Asia_South_GeoIP                        : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_South_GeoIP.yaml'                        , path: ./ruleset/GeoRouting_Asia_South_GeoIP.yaml                    }
#  GeoRouting_Asia_Central_GeoIP                      : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_Central_GeoIP.yaml'                      , path: ./ruleset/GeoRouting_Asia_Central_GeoIP.yaml                  }
#  GeoRouting_Asia_West_GeoIP                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_West_GeoIP.yaml'                         , path: ./ruleset/GeoRouting_Asia_West_GeoIP.yaml                     }
#  GeoRouting_Africa_North_GeoIP                      : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_North_GeoIP.yaml'                      , path: ./ruleset/GeoRouting_Africa_North_GeoIP.yaml                  }
#  GeoRouting_Africa_South_GeoIP                      : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_South_GeoIP.yaml'                      , path: ./ruleset/GeoRouting_Africa_South_GeoIP.yaml                  }
#  GeoRouting_Africa_West_GeoIP                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_West_GeoIP.yaml'                       , path: ./ruleset/GeoRouting_Africa_West_GeoIP.yaml                   }
#  GeoRouting_Africa_East_GeoIP                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_East_GeoIP.yaml'                       , path: ./ruleset/GeoRouting_Africa_East_GeoIP.yaml                   }
#  GeoRouting_Africa_Central_GeoIP                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_Central_GeoIP.yaml'                    , path: ./ruleset/GeoRouting_Africa_Central_GeoIP.yaml                }
#
#  GeoRouting_America_North_GeoIP                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_America_North_GeoIP_No_Resolve.yaml'          , path: ./ruleset/GeoRouting_America_North_GeoIP_No_Resolve.yaml      }
#  GeoRouting_America_South_GeoIP                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_America_South_GeoIP_No_Resolve.yaml'          , path: ./ruleset/GeoRouting_America_South_GeoIP_No_Resolve.yaml      }
#  GeoRouting_Europe_West_GeoIP                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Europe_West_GeoIP_No_Resolve.yaml'            , path: ./ruleset/GeoRouting_Europe_West_GeoIP_No_Resolve.yaml        }
#  GeoRouting_Europe_East_GeoIP                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Europe_East_GeoIP_No_Resolve.yaml'            , path: ./ruleset/GeoRouting_Europe_East_GeoIP_No_Resolve.yaml        }
#  GeoRouting_Oceania_GeoIP                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Oceania_GeoIP_No_Resolve.yaml'                , path: ./ruleset/GeoRouting_Oceania_GeoIP_No_Resolve.yaml            }
#  GeoRouting_Antarctica_GeoIP                        : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Antarctica_GeoIP_No_Resolve.yaml'             , path: ./ruleset/GeoRouting_Antarctica_GeoIP_No_Resolve.yaml         }
#  GeoRouting_Asia_East_GeoIP                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_East_GeoIP_No_Resolve.yaml'              , path: ./ruleset/GeoRouting_Asia_East_GeoIP_No_Resolve.yaml          }
#  GeoRouting_Asia_EastSouth_GeoIP                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_EastSouth_GeoIP_No_Resolve.yaml'         , path: ./ruleset/GeoRouting_Asia_EastSouth_GeoIP_No_Resolve.yaml     }
#  GeoRouting_Asia_South_GeoIP                        : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_South_GeoIP_No_Resolve.yaml'             , path: ./ruleset/GeoRouting_Asia_South_GeoIP_No_Resolve.yaml         }
#  GeoRouting_Asia_Central_GeoIP                      : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_Central_GeoIP_No_Resolve.yaml'           , path: ./ruleset/GeoRouting_Asia_Central_GeoIP_No_Resolve.yaml       }
#  GeoRouting_Asia_West_GeoIP                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_West_GeoIP_No_Resolve.yaml'              , path: ./ruleset/GeoRouting_Asia_West_GeoIP_No_Resolve.yaml          }
#  GeoRouting_Africa_North_GeoIP                      : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_North_GeoIP_No_Resolve.yaml'           , path: ./ruleset/GeoRouting_Africa_North_GeoIP_No_Resolve.yaml       }
#  GeoRouting_Africa_South_GeoIP                      : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_South_GeoIP_No_Resolve.yaml'           , path: ./ruleset/GeoRouting_Africa_South_GeoIP_No_Resolve.yaml       }
#  GeoRouting_Africa_West_GeoIP                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_West_GeoIP_No_Resolve.yaml'            , path: ./ruleset/GeoRouting_Africa_West_GeoIP_No_Resolve.yaml        }
#  GeoRouting_Africa_East_GeoIP                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_East_GeoIP_No_Resolve.yaml'            , path: ./ruleset/GeoRouting_Africa_East_GeoIP_No_Resolve.yaml        }
#  GeoRouting_Africa_Central_GeoIP                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Africa_Central_GeoIP_No_Resolve.yaml'         , path: ./ruleset/GeoRouting_Africa_Central_GeoIP_No_Resolve.yaml     }


#
# 注意： 上述洲际规则中，并没有包含 🇨🇳中国 ，中国需要使用单独规则：
#
#  GeoRouting_Asia_China_GeoIP                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_China_GeoIP.yaml'                         , path: ./ruleset/GeoRouting_Asia_China_GeoIP.yaml                     }
#  GeoRouting_Asia_China_GeoIP                         : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_IP/GeoRouting_Asia_China_GeoIP_No_Resolve.yaml'              , path: ./ruleset/GeoRouting_Asia_China_GeoIP_No_Resolve.yaml          }
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





###################################################################################
#
# GeoIP 地址代码 ( GeoNames ) ，对照表
#
# ISO规范：对照表：
# https://www.geonames.org/countries/
#
# GeoIP - 国家 城市 ：对照表
# https://www.maxmind.com/download/geoip/misc/region_codes.csv
#
###################################################################################


# 特别注意：特别注意：特别注意：特别注意：特别注意：特别注意：
#
# 洲际编码（continent_code、即，顶级域名），不能直接作为GeoIP的索引 !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!! （例如：af非洲，会与阿富汗重名 !!!!!!!!!! ）



#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------  
#        |               |               |                  |                                |                                        |            
#        |   地理序号     |   本地编码     |    洲际编码                  国家编码                             国家名称                         洲际名称          国家名称     
# Order  |   geoname_id  |  locale_code  |  continent_code  |   country_iso_cod ISO-3166     |            country_name                |   continent_name    country_name
#        |               |               |                  |  alpha-2 / alpha-3 / numeric   |                                        |            
#        |               |               |                  |                                |                                        |            
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------  
#        |               |               |                  |                                |                                        |                                        
#   1    |    6255149    |     zh-CN     |        NA        |     NA / NAM /                 |    North America                       |     北美洲            (北美洲 所有国家)  
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------                 
#   1    |    3374084    |     zh-CN     |        NA        |     BB / BRB / 2               |    Barbados                            |     北美洲            巴巴多斯                                
#   1    |    3424932    |     zh-CN     |        NA        |     PM / SPM / 66              |    Saint Pierre and Miquelon           |     北美洲            圣皮埃尔和密克隆群岛                  
#   1    |    3425505    |     zh-CN     |        NA        |     GL / GRL / 04              |    Greenland                           |     北美洲            格陵兰                 
#   1    |    3489940    |     zh-CN     |        NA        |     JM / JAM / 88              |    Jamaica                             |     北美洲            牙买加                 
#   1    |    3508796    |     zh-CN     |        NA        |     DO / DOM / 14              |    Dominican Republic                  |     北美洲            多米尼加                    
#   1    |    3562981    |     zh-CN     |        NA        |     CU / CUB / 92              |    Cuba                                |     北美洲            古巴                  
#   1    |    3570311    |     zh-CN     |        NA        |     MQ / MTQ / 74              |    Martinique                          |     北美洲            马提尼克                    
#   1    |    3572887    |     zh-CN     |        NA        |     BS / BHS / 4               |    Bahamas                             |     北美洲            巴哈马                 
#   1    |    3573345    |     zh-CN     |        NA        |     BM / BMU / 0               |    Bermuda                             |     北美洲            百慕大                 
#   1    |    3573511    |     zh-CN     |        NA        |     AI / AIA / 60              |    Anguilla                            |     北美洲            安圭拉                 
#   1    |    3573591    |     zh-CN     |        NA        |     TT / TTO / 80              |    Trinidad and Tobago                 |     北美洲            特立尼达和多巴哥                    
#   1    |    3575174    |     zh-CN     |        NA        |     KN / KNA / 59              |    St Kitts and Nevis                  |     北美洲            圣基茨和尼维斯                 
#   1    |    3575830    |     zh-CN     |        NA        |     DM / DMA / 12              |    Dominica                            |     北美洲            多米尼克                    
#   1    |    3576396    |     zh-CN     |        NA        |     AG / ATG / 8               |    Antigua and Barbuda                 |     北美洲            安提瓜和巴布达                 
#   1    |    3576468    |     zh-CN     |        NA        |     LC / LCA / 62              |    Saint Lucia                         |     北美洲            圣卢西亚                    
#   1    |    3576916    |     zh-CN     |        NA        |     TC / TCA / 96              |    Turks and Caicos Islands            |     北美洲            特克斯和凯科斯群岛                   
#   1    |    3577279    |     zh-CN     |        NA        |     AW / ABW / 33              |    Aruba                               |     北美洲            阿鲁巴                 
#   1    |    3577718    |     zh-CN     |        NA        |     VG / VGB / 2               |    British Virgin Islands              |     北美洲            英属维尔京群岛                 
#   1    |    3577815    |     zh-CN     |        NA        |     VC / VCT / 70              |    St Vincent and Grenadines           |     北美洲            圣文森特和格林纳丁斯                  
#   1    |    3578097    |     zh-CN     |        NA        |     MS / MSR / 00              |    Montserrat                          |     北美洲            蒙特塞拉特                   
#   1    |    3578421    |     zh-CN     |        NA        |     MF / MAF / 63              |    Saint Martin                        |     北美洲            法属圣马丁                   
#   1    |    3578476    |     zh-CN     |        NA        |     BL / BLM / 52              |    Saint Barthélemy                    |     北美洲            圣巴泰勒米                   
#   1    |    3579143    |     zh-CN     |        NA        |     GP / GLP / 12              |    Guadeloupe                          |     北美洲            瓜德罗普                    
#   1    |    3580239    |     zh-CN     |        NA        |     GD / GRD / 08              |    Grenada                             |     北美洲            格林纳达                    
#   1    |    3580718    |     zh-CN     |        NA        |     KY / CYM / 36              |    Cayman Islands                      |     北美洲            开曼群岛                    
#   1    |    3582678    |     zh-CN     |        NA        |     BZ / BLZ / 4               |    Belize                              |     北美洲            伯利兹                 
#   1    |    3585968    |     zh-CN     |        NA        |     SV / SLV / 22              |    El Salvador                         |     北美洲            萨尔瓦多                    
#   1    |    3595528    |     zh-CN     |        NA        |     GT / GTM / 20              |    Guatemala                           |     北美洲            危地马拉                    
#   1    |    3608932    |     zh-CN     |        NA        |     HN / HND / 40              |    Honduras                            |     北美洲            洪都拉斯                    
#   1    |    3617476    |     zh-CN     |        NA        |     NI / NIC / 58              |    Nicaragua                           |     北美洲            尼加拉瓜                    
#   1    |    3624060    |     zh-CN     |        NA        |     CR / CRI / 88              |    Costa Rica                          |     北美洲            哥斯达黎加                   
#   1    |    3703430    |     zh-CN     |        NA        |     PA / PAN / 91              |    Panama                              |     北美洲            巴拿马                 
#   1    |    3723988    |     zh-CN     |        NA        |     HT / HTI / 32              |    Haiti                               |     北美洲            海地                  
#   1    |    3996063    |     zh-CN     |        NA        |     MX / MEX / 84              |    Mexico                              |     北美洲            墨西哥                 
#   1    |    4566966    |     zh-CN     |        NA        |     PR / PRI / 30              |    Puerto Rico                         |     北美洲            波多黎各                    
#   1    |    4796775    |     zh-CN     |        NA        |     VI / VIR / 50              |    U.S. Virgin Islands                 |     北美洲            美属维尔京群岛                 
#   1    |    6251999    |     zh-CN     |        NA        |     CA / CAN / 24              |    Canada                              |     北美洲            加拿大                 
#   1    |    6252001    |     zh-CN     |        NA        |     US / USA / 40              |    United States                       |     北美洲            美国                  
#   1    |    7609695    |     zh-CN     |        NA        |     SX / SXM / 34              |    Sint Maarten                        |     北美洲            圣马丁岛                    
#   1    |    7626836    |     zh-CN     |        NA        |     CW / CUW / 31              |    Curaçao                             |     北美洲            库拉索                 
#   1    |    7626844    |     zh-CN     |        NA        |     BQ / BES / 35              |    Bonaire, Sint Eustatius, and Saba   |     北美洲            博奈尔岛、圣尤斯达蒂斯和萨巴 
#        |               |               |                  |                                |                                        |                          
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
#        |               |               |                  |                                |                                        |                     
#   2    |    6255148    |     zh-CN     |        EU        |     EU / EUR /                 |    Europe                              |     欧洲             (欧洲 所有国家)      
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+------------------------------------------- 
#   2    |    146669     |     zh-CN     |        EU        |     CY / CYP / 196             |    Cyprus                              |     欧洲             塞浦路斯                    
#   2    |    390903     |     zh-CN     |        EU        |     GR / GRC / 300             |    Greece                              |     欧洲             希腊                  
#   2    |    453733     |     zh-CN     |        EU        |     EE / EST / 233             |    Estonia                             |     欧洲             爱沙尼亚                    
#   2    |    458258     |     zh-CN     |        EU        |     LV / LVA / 428             |    Latvia                              |     欧洲             拉脱维亚                    
#   2    |    597427     |     zh-CN     |        EU        |     LT / LTU / 440             |    Lithuania                           |     欧洲             立陶宛                 
#   2    |    607072     |     zh-CN     |        EU        |     SJ / SJM / 744             |    Svalbard and Jan Mayen              |     欧洲             斯瓦尔巴岛和扬马延岛                  
#   2    |    617790     |     zh-CN     |        EU        |     MD / MDA / 498             |    Moldova                             |     欧洲             摩尔多瓦                    
#   2    |    630336     |     zh-CN     |        EU        |     BY / BLR / 112             |    Belarus                             |     欧洲             白俄罗斯                    
#   2    |    660013     |     zh-CN     |        EU        |     FI / FIN / 246             |    Finland                             |     欧洲             芬兰                  
#   2    |    661882     |     zh-CN     |        EU        |     AX / ALA / 248             |    Åland                               |     欧洲             奥兰群岛                    
#   2    |    690791     |     zh-CN     |        EU        |     UA / UKR / 804             |    Ukraine                             |     欧洲             乌克兰                 
#   2    |    718075     |     zh-CN     |        EU        |     MK / MKD / 807             |    North Macedonia                     |     欧洲             前南马其顿                   
#   2    |    719819     |     zh-CN     |        EU        |     HU / HUN / 348             |    Hungary                             |     欧洲             匈牙利                 
#   2    |    732800     |     zh-CN     |        EU        |     BG / BGR / 100             |    Bulgaria                            |     欧洲             保加利亚                    
#   2    |    783754     |     zh-CN     |        EU        |     AL / ALB / 8               |    Albania                             |     欧洲             阿尔巴尼亚                   
#   2    |    798544     |     zh-CN     |        EU        |     PL / POL / 616             |    Poland                              |     欧洲             波兰                  
#   2    |    798549     |     zh-CN     |        EU        |     RO / ROU / 642             |    Romania                             |     欧洲             罗马尼亚                    
#   2    |    831053     |     zh-CN     |        EU        |     XK / XKX / 0               |    Kosovo                              |     欧洲             科索沃                 
#   2    |    2017370    |     zh-CN     |        EU        |     RU / RUS / 643             |    Russia                              |     欧洲             俄罗斯联邦                   
#   2    |    2264397    |     zh-CN     |        EU        |     PT / PRT / 620             |    Portugal                            |     欧洲             葡萄牙                 
#   2    |    2411586    |     zh-CN     |        EU        |     GI / GIB / 292             |    Gibraltar                           |     欧洲             直布罗陀                    
#   2    |    2510769    |     zh-CN     |        EU        |     ES / ESP / 724             |    Spain                               |     欧洲             西班牙                 
#   2    |    2562770    |     zh-CN     |        EU        |     MT / MLT / 470             |    Malta                               |     欧洲             马耳他                 
#   2    |    2622320    |     zh-CN     |        EU        |     FO / FRO / 234             |    Faroe Islands                       |     欧洲             法罗群岛                    
#   2    |    2623032    |     zh-CN     |        EU        |     DK / DNK / 208             |    Denmark                             |     欧洲             丹麦                  
#   2    |    2629691    |     zh-CN     |        EU        |     IS / ISL / 352             |    Iceland                             |     欧洲             冰岛                  
#   2    |    2635167    |     zh-CN     |        EU        |     GB / GBR / 826             |    United Kingdom                      |     欧洲             英国                  
#   2    |    2658434    |     zh-CN     |        EU        |     CH / CHE / 756             |    Switzerland                         |     欧洲             瑞士                  
#   2    |    2661886    |     zh-CN     |        EU        |     SE / SWE / 752             |    Sweden                              |     欧洲             瑞典                  
#   2    |    2750405    |     zh-CN     |        EU        |     NL / NLD / 528             |    Netherlands                         |     欧洲             荷兰                  
#   2    |    2782113    |     zh-CN     |        EU        |     AT / AUT / 40              |    Austria                             |     欧洲             奥地利                 
#   2    |    2802361    |     zh-CN     |        EU        |     BE / BEL / 56              |    Belgium                             |     欧洲             比利时                 
#   2    |    2921044    |     zh-CN     |        EU        |     DE / DEU / 276             |    Germany                             |     欧洲             德国                  
#   2    |    2960313    |     zh-CN     |        EU        |     LU / LUX / 442             |    Luxembourg                          |     欧洲             卢森堡                 
#   2    |    2963597    |     zh-CN     |        EU        |     IE / IRL / 372             |    Ireland                             |     欧洲             爱尔兰                 
#   2    |    2993457    |     zh-CN     |        EU        |     MC / MCO / 492             |    Monaco                              |     欧洲             摩纳哥                 
#   2    |    3017382    |     zh-CN     |        EU        |     FR / FRA / 250             |    France                              |     欧洲             法国                  
#   2    |    3041565    |     zh-CN     |        EU        |     AD / AND / 20              |    Andorra                             |     欧洲             安道尔                 
#   2    |    3042058    |     zh-CN     |        EU        |     LI / LIE / 438             |    Liechtenstein                       |     欧洲             列支敦士登                   
#   2    |    3042142    |     zh-CN     |        EU        |     JE / JEY / 832             |    Jersey                              |     欧洲             泽西岛                 
#   2    |    3042225    |     zh-CN     |        EU        |     IM / IMN / 833             |    Isle of Man                         |     欧洲             英国属地曼岛                  
#   2    |    3042362    |     zh-CN     |        EU        |     GG / GGY / 831             |    Guernsey                            |     欧洲             根西岛                 
#   2    |    3057568    |     zh-CN     |        EU        |     SK / SVK / 703             |    Slovakia                            |     欧洲             斯洛伐克                    
#   2    |    3077311    |     zh-CN     |        EU        |     CZ / CZE / 203             |    Czechia                             |     欧洲             捷克                  
#   2    |    3144096    |     zh-CN     |        EU        |     NO / NOR / 578             |    Norway                              |     欧洲             挪威                  
#   2    |    3164670    |     zh-CN     |        EU        |     VA / VAT / 336             |    Vatican City                        |     欧洲             梵蒂冈                 
#   2    |    3168068    |     zh-CN     |        EU        |     SM / SMR / 674             |    San Marino                          |     欧洲             圣马力诺                    
#   2    |    3175395    |     zh-CN     |        EU        |     IT / ITA / 380             |    Italy                               |     欧洲             意大利                 
#   2    |    3190538    |     zh-CN     |        EU        |     SI / SVN / 705             |    Slovenia                            |     欧洲             斯洛文尼亚                   
#   2    |    3194884    |     zh-CN     |        EU        |     ME / MNE / 499             |    Montenegro                          |     欧洲             黑山                  
#   2    |    3202326    |     zh-CN     |        EU        |     HR / HRV / 191             |    Croatia                             |     欧洲             克罗地亚                    
#   2    |    3277605    |     zh-CN     |        EU        |     BA / BIH / 70              |    Bosnia and Herzegovina              |     欧洲             波黑                 
#   2    |    6290252    |     zh-CN     |        EU        |     RS / SRB / 688             |    Serbia                              |     欧洲             塞尔维亚               
#        |               |               |                  |                                |                                        |                     
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+------------------------------------------- 
#        |               |               |                  |                                |                                        |                              
#   3    |    6255151    |     zh-CN     |        OC        |     OC / OCE /                 |    Oceania                             |    大洋洲             (大洋洲 所有国家)      
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
#   3    |    1559582    |     zh-CN     |        OC        |     PW / PLW / 85              |    Palau                               |    大洋洲             帕劳                  
#   3    |    1899402    |     zh-CN     |        OC        |     CK / COK / 84              |    Cook Islands                        |    大洋洲             库克群岛                    
#   3    |    1966436    |     zh-CN     |        OC        |     TL / TLS / 26              |    Timor-Leste                         |    大洋洲             东帝汶                 
#   3    |    2077456    |     zh-CN     |        OC        |     AU / AUS / 6               |    Australia                           |    大洋洲             澳大利亚                    
#   3    |    2078138    |     zh-CN     |        OC        |     CX / CXR / 62              |    Christmas Island                    |    大洋洲             圣诞岛                 
#   3    |    2080185    |     zh-CN     |        OC        |     MH / MHL / 84              |    Marshall Islands                    |    大洋洲             马绍尔群岛                   
#   3    |    2081918    |     zh-CN     |        OC        |     FM / FSM / 83              |    Micronesia                          |    大洋洲             密克罗尼西亚联邦                    
#   3    |    2088628    |     zh-CN     |        OC        |     PG / PNG / 98              |    Papua New Guinea                    |    大洋洲             巴布亚新几内亚                 
#   3    |    2103350    |     zh-CN     |        OC        |     SB / SLB / 0               |    Solomon Islands                     |    大洋洲             所罗门群岛                   
#   3    |    2110297    |     zh-CN     |        OC        |     TV / TUV / 98              |    Tuvalu                              |    大洋洲             图瓦卢                 
#   3    |    2110425    |     zh-CN     |        OC        |     NR / NRU / 20              |    Nauru                               |    大洋洲             瑙鲁                  
#   3    |    2134431    |     zh-CN     |        OC        |     VU / VUT / 48              |    Vanuatu                             |    大洋洲             瓦努阿图                    
#   3    |    2139685    |     zh-CN     |        OC        |     NC / NCL / 40              |    New Caledonia                       |    大洋洲             新喀里多尼亚                  
#   3    |    2155115    |     zh-CN     |        OC        |     NF / NFK / 74              |    Norfolk Island                      |    大洋洲             诺福克岛                    
#   3    |    2186224    |     zh-CN     |        OC        |     NZ / NZL / 54              |    New Zealand                         |    大洋洲             新西兰                 
#   3    |    2205218    |     zh-CN     |        OC        |     FJ / FJI / 42              |    Fiji                                |    大洋洲             斐济                  
#   3    |    4030656    |     zh-CN     |        OC        |     PF / PYF / 58              |    French Polynesia                    |    大洋洲             法属波利尼西亚                 
#   3    |    4030699    |     zh-CN     |        OC        |     PN / PCN / 12              |    Pitcairn Islands                    |    大洋洲             皮特凯恩                    
#   3    |    4030945    |     zh-CN     |        OC        |     KI / KIR / 96              |    Kiribati                            |    大洋洲             基里巴斯                    
#   3    |    4031074    |     zh-CN     |        OC        |     TK / TKL / 72              |    Tokelau                             |    大洋洲             托克劳                 
#   3    |    4032283    |     zh-CN     |        OC        |     TO / TON / 76              |    Tonga                               |    大洋洲             汤加                  
#   3    |    4034749    |     zh-CN     |        OC        |     WF / WLF / 76              |    Wallis and Futuna                   |    大洋洲             瓦利斯和富图纳                 
#   3    |    4034894    |     zh-CN     |        OC        |     WS / WSM / 82              |    Samoa                               |    大洋洲             萨摩亚                 
#   3    |    4036232    |     zh-CN     |        OC        |     NU / NIU / 70              |    Niue                                |    大洋洲             纽埃                  
#   3    |    4041468    |     zh-CN     |        OC        |     MP / MNP / 80              |    Northern Mariana Islands            |    大洋洲             北马里亚纳                   
#   3    |    4043988    |     zh-CN     |        OC        |     GU / GUM / 16              |    Guam                                |    大洋洲             关岛                  
#   3    |    5854968    |     zh-CN     |        OC        |     UM / UMI / 81              |    U.S. Outlying Islands               |    大洋洲             美国本土外小岛屿                    
#   3    |    5880801    |     zh-CN     |        OC        |     AS / ASM / 6               |    American Samoa                      |    大洋洲             美属萨摩亚    
#        |               |               |                  |                                |                                        |                      
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
#        |               |               |                  |                                |                                        |                                 
#   4    |    6255147    |     zh-CN     |        SA        |     SA / SAM  /                |    South Americ                        |    南美洲             (南美洲 所有国家)
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+------------------------------------------- 
#   4    |    3378535    |     zh-CN     |        SA        |     GY / GUY /28               |    Guyana                              |    南美洲             圭亚那                 
#   4    |    3381670    |     zh-CN     |        SA        |     GF / GUF /54               |    French Guiana                       |    南美洲             法属圭亚那                   
#   4    |    3382998    |     zh-CN     |        SA        |     SR / SUR /40               |    Suriname                            |    南美洲             苏里南                 
#   4    |    3437598    |     zh-CN     |        SA        |     PY / PRY /00               |    Paraguay                            |    南美洲             巴拉圭                 
#   4    |    3439705    |     zh-CN     |        SA        |     UY / URY /58               |    Uruguay                             |    南美洲             乌拉圭                 
#   4    |    3469034    |     zh-CN     |        SA        |     BR / BRA /6                |    Brazil                              |    南美洲             巴西                  
#   4    |    3474414    |     zh-CN     |        SA        |     FK / FLK /38               |    Falkland Islands                    |    南美洲             福克兰群岛（马尔维纳斯）                    
#   4    |    3625428    |     zh-CN     |        SA        |     VE / VEN /62               |    Venezuela                           |    南美洲             委内瑞拉                    
#   4    |    3658394    |     zh-CN     |        SA        |     EC / ECU /18               |    Ecuador                             |    南美洲             厄瓜多尔                    
#   4    |    3686110    |     zh-CN     |        SA        |     CO / COL /70               |    Colombia                            |    南美洲             哥伦比亚                    
#   4    |    3865483    |     zh-CN     |        SA        |     AR / ARG /2                |    Argentina                           |    南美洲             阿根廷                 
#   4    |    3895114    |     zh-CN     |        SA        |     CL / CHL /52               |    Chile                               |    南美洲             智利                  
#   4    |    3923057    |     zh-CN     |        SA        |     BO / BOL /8                |    Bolivia                             |    南美洲             玻利维亚                    
#   4    |    3932488    |     zh-CN     |        SA        |     PE / PER /04               |    Peru                                |    南美洲             秘鲁        
#        |               |               |                  |                                |                                        |                     
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
#        |               |               |                  |                                |                                        |                                      
#   5    |    6697173    |     zh-CN     |        AN        |     AQ / ATA  /                |    Antarctica                          |    南极洲             (南极洲 所有国家)     
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
#   5    |    1546748    |     zh-CN     |        AN        |     TF / ATF  /60              |    French Southern Territories         |    南极洲             法属南部领地                  
#   5    |    1547314    |     zh-CN     |        AN        |     HM / HMD  /34              |    Heard and McDonald Islands          |    南极洲             赫德岛和麦克唐纳岛                   
#   5    |    3371123    |     zh-CN     |        AN        |     BV / BVT  /4               |    Bouvet Island                       |    南极洲             布维岛                 
#   5    |    3474415    |     zh-CN     |        AN        |     GS / SGS  /39              |    South Georgia and South Sandwich Isl|nds 南极洲             南乔治亚岛和南桑德韦奇岛   
#        |               |               |                  |                                |                                        |                     
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
#        |               |               |                  |                                |                                        |                            
#   6    |    6255147    |     zh-CN     |        AS        |     AS / ASA /                 |    Asia                                |    亚洲              (亚洲 所有国家)      
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
#   6    |    69543      |     zh-CN     |        AS        |     YE / YEM / 887             |    Yemen                               |    亚洲              也门                  
#   6    |    99237      |     zh-CN     |        AS        |     IQ / IRQ / 368             |    Iraq                                |    亚洲              伊拉克                 
#   6    |    102358     |     zh-CN     |        AS        |     SA / SAU / 682             |    Saudi Arabia                        |    亚洲              沙特阿拉伯                   
#   6    |    130758     |     zh-CN     |        AS        |     IR / IRN / 364             |    Iran                                |    亚洲              伊朗                  
#   6    |    163843     |     zh-CN     |        AS        |     SY / SYR / 760             |    Syria                               |    亚洲              叙利亚                 
#   6    |    174982     |     zh-CN     |        AS        |     AM / ARM / 51              |    Armenia                             |    亚洲              亚美尼亚                    
#   6    |    248816     |     zh-CN     |        AS        |     JO / JOR / 400             |    Jordan                              |    亚洲              约旦                  
#   6    |    272103     |     zh-CN     |        AS        |     LB / LBN / 422             |    Lebanon                             |    亚洲              黎巴嫩                 
#   6    |    285570     |     zh-CN     |        AS        |     KW / KWT / 414             |    Kuwait                              |    亚洲              科威特                 
#   6    |    286963     |     zh-CN     |        AS        |     OM / OMN / 512             |    Oman                                |    亚洲              阿曼                  
#   6    |    289688     |     zh-CN     |        AS        |     QA / QAT / 634             |    Qatar                               |    亚洲              卡塔尔                 
#   6    |    290291     |     zh-CN     |        AS        |     BH / BHR / 48              |    Bahrain                             |    亚洲              巴林                  
#   6    |    290557     |     zh-CN     |        AS        |     AE / ARE / 784             |    United Arab Emirates                |    亚洲              阿联酋                 
#   6    |    294640     |     zh-CN     |        AS        |     IL / ISR / 376             |    Israel                              |    亚洲              以色列                 
#   6    |    298795     |     zh-CN     |        AS        |     TR / TUR / 792             |    Turkey                              |    亚洲              土耳其                 
#   6    |    587116     |     zh-CN     |        AS        |     AZ / AZE / 31              |    Azerbaijan                          |    亚洲              阿塞拜疆                     
#   6    |    614540     |     zh-CN     |        AS        |     GE / GEO / 268             |    Georgia                             |    亚洲              格鲁吉亚                    
#   6    |    1149361    |     zh-CN     |        AS        |     AF / AFG / 4               |    Afghanistan                         |    亚洲              阿富汗                 
#   6    |    1168579    |     zh-CN     |        AS        |     PK / PAK / 586             |    Pakistan                            |    亚洲              巴基斯坦                    
#   6    |    1210997    |     zh-CN     |        AS        |     BD / BGD / 50              |    Bangladesh                          |    亚洲              孟加拉国                    
#   6    |    1218197    |     zh-CN     |        AS        |     TM / TKM / 795             |    Turkmenistan                        |    亚洲              土库曼斯坦                   
#   6    |    1220409    |     zh-CN     |        AS        |     TJ / TJK / 762             |    Tajikistan                          |    亚洲              塔吉克斯坦                   
#   6    |    1227603    |     zh-CN     |        AS        |     LK / LKA / 144             |    Sri Lanka                           |    亚洲              斯里兰卡                    
#   6    |    1252634    |     zh-CN     |        AS        |     BT / BTN / 64              |    Bhutan                              |    亚洲              不丹                  
#   6    |    1269750    |     zh-CN     |        AS        |     IN / IND / 356             |    India                               |    亚洲              印度                  
#   6    |    1282028    |     zh-CN     |        AS        |     MV / MDV / 462             |    Maldives                            |    亚洲              马尔代夫                    
#   6    |    1282588    |     zh-CN     |        AS        |     IO / IOT / 86              |    British Indian Ocean Territory      |    亚洲              英属印度洋领地                 
#   6    |    1282988    |     zh-CN     |        AS        |     NP / NPL / 524             |    Nepal                               |    亚洲              尼泊尔                 
#   6    |    1327865    |     zh-CN     |        AS        |     MM / MMR / 104             |    Myanmar                             |    亚洲              缅甸                  
#   6    |    1512440    |     zh-CN     |        AS        |     UZ / UZB / 860             |    Uzbekistan                          |    亚洲              乌兹别克斯坦                  
#   6    |    1522867    |     zh-CN     |        AS        |     KZ / KAZ / 398             |    Kazakhstan                          |    亚洲              哈萨克斯坦                   
#   6    |    1527747    |     zh-CN     |        AS        |     KG / KGZ / 417             |    Kyrgyzstan                          |    亚洲              吉尔吉斯斯坦                  
#   6    |    1547376    |     zh-CN     |        AS        |     CC / CCK / 166             |    Cocos (Keeling) Islands             |    亚洲              科科斯（基林）群岛                   
#   6    |    1562822    |     zh-CN     |        AS        |     VN / VNM / 704             |    Vietnam                             |    亚洲              越南                  
#   6    |    1605651    |     zh-CN     |        AS        |     TH / THA / 764             |    Thailand                            |    亚洲              泰国                  
#   6    |    1643084    |     zh-CN     |        AS        |     ID / IDN / 360             |    Indonesia                           |    亚洲              印度尼西亚                   
#   6    |    1655842    |     zh-CN     |        AS        |     LA / LAO / 418             |    Laos                                |    亚洲              老挝                  
#   6    |    1668284    |     zh-CN     |        AS        |     TW / TWN / 158             |    Taiwan                              |    亚洲              台湾                  
#   6    |    1694008    |     zh-CN     |        AS        |     PH / PHL / 608             |    Philippines                         |    亚洲              菲律宾                 
#   6    |    1733045    |     zh-CN     |        AS        |     MY / MYS / 458             |    Malaysia                            |    亚洲              马来西亚                    
#   6    |    1814991    |     zh-CN     |        AS        |     CN / CHN / 156             |    China                               |    亚洲              中国                  
#   6    |    1819730    |     zh-CN     |        AS        |     HK / HKG / 344             |    Hong Kong                           |    亚洲              香港                  
#   6    |    1820814    |     zh-CN     |        AS        |     BN / BRN / 96              |    Brunei                              |    亚洲              文莱                  
#   6    |    1821275    |     zh-CN     |        AS        |     MO / MAC / 446             |    Macao                               |    亚洲              澳门                  
#   6    |    1831722    |     zh-CN     |        AS        |     KH / KHM / 116             |    Cambodia                            |    亚洲              柬埔寨                 
#   6    |    1835841    |     zh-CN     |        AS        |     KR / KOR / 410             |    South Korea                         |    亚洲              韩国                  
#   6    |    1861060    |     zh-CN     |        AS        |     JP / JPN / 392             |    Japan                               |    亚洲              日本                  
#   6    |    1873107    |     zh-CN     |        AS        |     KP / PRK / 408             |    North Korea                         |    亚洲              朝鲜                  
#   6    |    1880251    |     zh-CN     |        AS        |     SG / SGP / 702             |    Singapore                           |    亚洲              新加坡                 
#   6    |    2029969    |     zh-CN     |        AS        |     MN / MNG / 496             |    Mongolia                            |    亚洲              蒙古                  
#   6    |    6254930    |     zh-CN     |        AS        |     PS / PSE / 275             |    Palestine                           |    亚洲              巴勒斯坦              
#        |               |               |                  |                                |                                        |                      
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
#        |               |               |                  |                                |                                        |                     
#   7    |    7909807    |     zh-CN     |        AF        |     AF / AFR /                 |    Africa                              |    非洲              (非洲 所有国家)  
#        |               |               |                  |                                |                                        |                     
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
#   7    |    49518      |     zh-CN     |        AF        |     RW / RWA / 646             |    Rwanda                              |    非洲              卢旺达                 
#   7    |    51537      |     zh-CN     |        AF        |     SO / SOM / 706             |    Somalia                             |    非洲              索马里                 
#   7    |    149590     |     zh-CN     |        AF        |     TZ / TZA / 834             |    Tanzania                            |    非洲              坦桑尼亚                    
#   7    |    192950     |     zh-CN     |        AF        |     KE / KEN / 404             |    Kenya                               |    非洲              肯尼亚                 
#   7    |    203312     |     zh-CN     |        AF        |     CD / COD / 180             |    DR Congo                            |    非洲              扎伊尔                 
#   7    |    223816     |     zh-CN     |        AF        |     DJ / DJI / 262             |    Djibouti                            |    非洲              吉布提                 
#   7    |    226074     |     zh-CN     |        AF        |     UG / UGA / 800             |    Uganda                              |    非洲              乌干达                 
#   7    |    239880     |     zh-CN     |        AF        |     CF / CAF / 140             |    Central African Republic            |    非洲              中非                  
#   7    |    241170     |     zh-CN     |        AF        |     SC / SYC / 690             |    Seychelles                          |    非洲              塞舌尔                 
#   7    |    337996     |     zh-CN     |        AF        |     ET / ETH / 231             |    Ethiopia                            |    非洲              埃塞俄比亚                   
#   7    |    338010     |     zh-CN     |        AF        |     ER / ERI / 232             |    Eritrea                             |    非洲              厄立特里亚                   
#   7    |    357994     |     zh-CN     |        AF        |     EG / EGY / 818             |    Egypt                               |    非洲              埃及                  
#   7    |    366755     |     zh-CN     |        AF        |     SD / SDN / 729             |    Sudan                               |    非洲              苏丹                  
#   7    |    433561     |     zh-CN     |        AF        |     BI / BDI / 108             |    Burundi                             |    非洲              布隆迪                 
#   7    |    878675     |     zh-CN     |        AF        |     ZW / ZWE / 716             |    Zimbabwe                            |    非洲              津巴布韦                    
#   7    |    895949     |     zh-CN     |        AF        |     ZM / ZMB / 894             |    Zambia                              |    非洲              赞比亚                 
#   7    |    921929     |     zh-CN     |        AF        |     KM / COM / 174             |    Comoros                             |    非洲              科摩罗                 
#   7    |    927384     |     zh-CN     |        AF        |     MW / MWI / 454             |    Malawi                              |    非洲              马拉维                 
#   7    |    932692     |     zh-CN     |        AF        |     LS / LSO / 426             |    Lesotho                             |    非洲              莱索托                 
#   7    |    933860     |     zh-CN     |        AF        |     BW / BWA / 72              |    Botswana                            |    非洲              博茨瓦纳                    
#   7    |    934292     |     zh-CN     |        AF        |     MU / MUS / 480             |    Mauritius                           |    非洲              毛里求斯                    
#   7    |    934841     |     zh-CN     |        AF        |     SZ / SWZ / 748             |    Eswatini                            |    非洲              斯威士兰                    
#   7    |    935317     |     zh-CN     |        AF        |     RE / REU / 638             |    Réunion                             |    非洲              留尼汪                 
#   7    |    953987     |     zh-CN     |        AF        |     ZA / ZAF / 710             |    South Africa                        |    非洲              南非                  
#   7    |    1024031    |     zh-CN     |        AF        |     YT / MYT / 175             |    Mayotte                             |    非洲              马约特                 
#   7    |    1036973    |     zh-CN     |        AF        |     MZ / MOZ / 508             |    Mozambique                          |    非洲              莫桑比克                    
#   7    |    1062947    |     zh-CN     |        AF        |     MG / MDG / 450             |    Madagascar                          |    非洲              马达加斯加                   
#   7    |    2215636    |     zh-CN     |        AF        |     LY / LBY / 434             |    Libya                               |    非洲              利比亚                 
#   7    |    2233387    |     zh-CN     |        AF        |     CM / CMR / 120             |    Cameroon                            |    非洲              喀麦隆                 
#   7    |    2245662    |     zh-CN     |        AF        |     SN / SEN / 686             |    Senegal                             |    非洲              塞内加尔                    
#   7    |    2260494    |     zh-CN     |        AF        |     CG / COG / 178             |    Congo Republic                      |    非洲              刚果                   
#   7    |    2275384    |     zh-CN     |        AF        |     LR / LBR / 430             |    Liberia                             |    非洲              利比里亚                    
#   7    |    2287781    |     zh-CN     |        AF        |     CI / CIV / 384             |    Ivory Coast                         |    非洲              象牙海岸                    
#   7    |    2300660    |     zh-CN     |        AF        |     GH / GHA / 288             |    Ghana                               |    非洲              加纳                  
#   7    |    2309096    |     zh-CN     |        AF        |     GQ / GNQ / 226             |    Equatorial Guinea                   |    非洲              赤道几内亚                   
#   7    |    2328926    |     zh-CN     |        AF        |     NG / NGA / 566             |    Nigeria                             |    非洲              尼日利亚                    
#   7    |    2361809    |     zh-CN     |        AF        |     BF / BFA / 854             |    Burkina Faso                        |    非洲              布基纳法索                   
#   7    |    2363686    |     zh-CN     |        AF        |     TG / TGO / 768             |    Togo                                |    非洲              多哥                  
#   7    |    2372248    |     zh-CN     |        AF        |     GW / GNB / 624             |    Guinea-Bissau                       |    非洲              几内亚比绍                   
#   7    |    2378080    |     zh-CN     |        AF        |     MR / MRT / 478             |    Mauritania                          |    非洲              毛利塔尼亚                   
#   7    |    2395170    |     zh-CN     |        AF        |     BJ / BEN / 204             |    Benin                               |    非洲              贝宁                  
#   7    |    2400553    |     zh-CN     |        AF        |     GA / GAB / 266             |    Gabon                               |    非洲              加蓬                  
#   7    |    2403846    |     zh-CN     |        AF        |     SL / SLE / 694             |    Sierra Leone                        |    非洲              塞拉利昂                    
#   7    |    2410758    |     zh-CN     |        AF        |     ST / STP / 678             |    São Tomé and Príncipe               |    非洲              圣多美和普林西比                    
#   7    |    2413451    |     zh-CN     |        AF        |     GM / GMB / 270             |    The Gambia                          |    非洲              冈比亚                 
#   7    |    2420477    |     zh-CN     |        AF        |     GN / GIN / 324             |    Guinea                              |    非洲              几内亚                 
#   7    |    2434508    |     zh-CN     |        AF        |     TD / TCD / 148             |    Chad                                |    非洲              乍得                  
#   7    |    2440476    |     zh-CN     |        AF        |     NE / NER / 562             |    Niger                               |    非洲              尼日尔                 
#   7    |    2453866    |     zh-CN     |        AF        |     ML / MLI / 466             |    Mali                                |    非洲              马里                  
#   7    |    2461445    |     zh-CN     |        AF        |     EH / ESH / 732             |    Western Sahara                      |    非洲              西撒哈拉                    
#   7    |    2464461    |     zh-CN     |        AF        |     TN / TUN / 788             |    Tunisia                             |    非洲              突尼斯                 
#   7    |    2542007    |     zh-CN     |        AF        |     MA / MAR / 504             |    Morocco                             |    非洲              摩洛哥                 
#   7    |    2589581    |     zh-CN     |        AF        |     DZ / DZA / 12              |    Algeria                             |    非洲              阿尔及利亚                   
#   7    |    3351879    |     zh-CN     |        AF        |     AO / AGO / 24              |    Angola                              |    非洲              安哥拉                 
#   7    |    3355338    |     zh-CN     |        AF        |     NA / NAM / 516             |    Namibia                             |    非洲              纳米比亚                    
#   7    |    3370751    |     zh-CN     |        AF        |     SH / SHN / 654             |    Saint Helena                        |    非洲              圣赫勒拿                    
#   7    |    3374766    |     zh-CN     |        AF        |     CV / CPV / 132             |    Cabo Verde                          |    非洲              佛得角                 
#   7    |    7909807    |     zh-CN     |        AF        |     SS / SSD / 728             |    South Sudan                         |    非洲              南苏丹    
#        |               |               |                  |                                |                                        |                              
#        |               |               |                  |                                |                                        |                
#--------+---------------+---------------+------------------+--------------------------------+----------------------------------------+-------------------------------------------
                                             