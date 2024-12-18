
   # -----------------------------------------
   # 此规则集：用于，基于 “国家顶级域名（ccTLD）” 的地理位置，进行分流
   # -----------------------------------------

   # 用途：根据 目的网站的国家域名，进行分流（决定走哪个临近国家的VPS）


# 引用范例：
#
#   ccTLD_America_North_No_Resolve                 : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_America_North_No_Resolve.yaml'                 , path: ./ruleset/ccTLD_America_North_No_Resolve.yaml                 }
#   ccTLD_America_South_No_Resolve                 : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_America_South_No_Resolve.yaml'                 , path: ./ruleset/ccTLD_America_South_No_Resolve.yaml                 }
#   ccTLD_Europe_West_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Europe_West_No_Resolve.yaml'                   , path: ./ruleset/ccTLD_Europe_West_No_Resolve.yaml                   }
#   ccTLD_Europe_East_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Europe_East_No_Resolve.yaml'                   , path: ./ruleset/ccTLD_Europe_East_No_Resolve.yaml                   }
#   ccTLD_Oceania_No_Resolve                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Oceania_No_Resolve.yaml'                       , path: ./ruleset/ccTLD_Oceania_No_Resolve.yaml                       }
#   ccTLD_Antarctica_No_Resolve                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Antarctica_No_Resolve.yaml'                    , path: ./ruleset/ccTLD_Antarctica_No_Resolve.yaml                    }
#   ccTLD_Asia_East_No_Resolve                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_East_No_Resolve.yaml'                     , path: ./ruleset/ccTLD_Asia_East_No_Resolve.yaml                     }
#   ccTLD_Asia_EastSouth_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_EastSouth_No_Resolve.yaml'                , path: ./ruleset/ccTLD_Asia_EastSouth_No_Resolve.yaml                }
#   ccTLD_Asia_South_No_Resolve                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_South_No_Resolve.yaml'                    , path: ./ruleset/ccTLD_Asia_South_No_Resolve.yaml                    }
#   ccTLD_Asia_Central_No_Resolve                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_Central_No_Resolve.yaml'                  , path: ./ruleset/ccTLD_Asia_Central_No_Resolve.yaml                  }
#   ccTLD_Asia_West_No_Resolve                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_West_No_Resolve.yaml'                     , path: ./ruleset/ccTLD_Asia_West_No_Resolve.yaml                     }
#   ccTLD_Africa_North_No_Resolve                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_North_No_Resolve.yaml'                  , path: ./ruleset/ccTLD_Africa_North_No_Resolve.yaml                  }
#   ccTLD_Africa_South_No_Resolve                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_South_No_Resolve.yaml'                  , path: ./ruleset/ccTLD_Africa_South_No_Resolve.yaml                  }
#   ccTLD_Africa_West_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_West_No_Resolve.yaml'                   , path: ./ruleset/ccTLD_Africa_West_No_Resolve.yaml                   }
#   ccTLD_Africa_East_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_East_No_Resolve.yaml'                   , path: ./ruleset/ccTLD_Africa_East_No_Resolve.yaml                   }
#   ccTLD_Africa_Central_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_Central_No_Resolve.yaml'                , path: ./ruleset/ccTLD_Africa_Central_No_Resolve.yaml                }
#
#
#   ccTLD_America_North                            : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_America_North.yaml'                            , path: ./ruleset/ccTLD_America_North.yaml                            }
#   ccTLD_America_South                            : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_America_South.yaml'                            , path: ./ruleset/ccTLD_America_South.yaml                            }
#   ccTLD_Europe_West                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Europe_West.yaml'                              , path: ./ruleset/ccTLD_Europe_West.yaml                              }
#   ccTLD_Europe_East                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Europe_East.yaml'                              , path: ./ruleset/ccTLD_Europe_East.yaml                              }
#   ccTLD_Oceania                                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Oceania.yaml'                                  , path: ./ruleset/ccTLD_Oceania.yaml                                  }
#   ccTLD_Antarctica                               : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Antarctica.yaml'                               , path: ./ruleset/ccTLD_Antarctica.yaml                               }
#   ccTLD_Asia_East                                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_East.yaml'                                , path: ./ruleset/ccTLD_Asia_East.yaml                                }
#   ccTLD_Asia_EastSouth                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_EastSouth.yaml'                           , path: ./ruleset/ccTLD_Asia_EastSouth.yaml                           }
#   ccTLD_Asia_South                               : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_South.yaml'                               , path: ./ruleset/ccTLD_Asia_South.yaml                               }
#   ccTLD_Asia_Central                             : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_Central.yaml'                             , path: ./ruleset/ccTLD_Asia_Central.yaml                             }
#   ccTLD_Asia_West                                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Asia_West.yaml'                                , path: ./ruleset/ccTLD_Asia_West.yaml                                }
#   ccTLD_Africa_North                             : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_North.yaml'                             , path: ./ruleset/ccTLD_Africa_North.yaml                             }
#   ccTLD_Africa_South                             : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_South.yaml'                             , path: ./ruleset/ccTLD_Africa_South.yaml                             }
#   ccTLD_Africa_West                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_West.yaml'                              , path: ./ruleset/ccTLD_Africa_West.yaml                              }
#   ccTLD_Africa_East                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_East.yaml'                              , path: ./ruleset/ccTLD_Africa_East.yaml                              }
#   ccTLD_Africa_Central                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/ccTLD_Africa_Central.yaml'                           , path: ./ruleset/ccTLD_Africa_Central.yaml                           }
#
#



   # 哪些域名被排除在外：
   #
   #
   #   1.  谷歌认为，下列国家或地区顶级域在
   #       使用上更加符合通用顶级域的功能，
   #       而不是国家或地区顶级域。并且在
   #       搜索引擎优化和搜索引擎索引上做了
   #       对应的处理
   #       .ad \ .as \ .ai \ .bz \ .cc \ 
   #       .cd \ .co \ .dj \ .fm \ .io \ 
   #       .la \ .me \ .ms \ .nu \ .sc \  
   #       .sr \ .su \ .tv \ .tk \ .ws \
   #
   #       .gg \ .ac \ .ag \ .ec \ .la \ 
   #       .ac \ .vc \ .to \ .ly \ .sb \
   #       .?? \ .?? \
   #
   #   2. 以下ISO代码，没有对应的，国家代码的顶级域名
   #       .bv \ .bl \ .mf \ .sj \ .gb \ .um \
   #
   #
   #   3. 已经停止解析的，国家顶级域名：
   #       .yr \ .yu \ .tp \ .an \ .ac \
   #
   #
   # 上述需要排除的域名（引用自）：
   #
   #   https://zh.Wikipedia.org/zh-hans/國家和地區頂級域
   #   https://en.Wikipedia.org/wiki/Country_code_top-level_domain
   #


   #  其他：
   # 
   # 截至2020年6月，纯拉丁字母的，两个字符的，国家代码顶级域名( Country-code of Root Zone Database ) ，共有250个
   #   https://www.iana.org/domains/root/db
   #   * 选取：country-code  （注意：有些Country-code没有生效）
   #

   #