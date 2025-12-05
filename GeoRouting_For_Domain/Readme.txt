
# -----------------------------------------
# 此规则集：用于，基于 “国家顶级域名（ccTLD）” 的地理位置，进行分流
# -----------------------------------------

# 用途：根据 目的网站的国家域名，进行分流（决定走哪个临近国家的VPS）

# 注意： 规则中，并没有包含🇨🇳cn

# 引用范例：
#
#   GeoRouting_America_North_ccTLD_No_Resolve                 : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_North_ccTLD_No_Resolve.yaml'                 , path: ./ruleset/GeoRouting_America_North_ccTLD_No_Resolve.yaml                 }
#   GeoRouting_America_South_ccTLD_No_Resolve                 : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_South_ccTLD_No_Resolve.yaml'                 , path: ./ruleset/GeoRouting_America_South_ccTLD_No_Resolve.yaml                 }
#   GeoRouting_Europe_West_ccTLD_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_West_ccTLD_No_Resolve.yaml'                   , path: ./ruleset/GeoRouting_Europe_West_ccTLD_No_Resolve.yaml                   }
#   GeoRouting_Europe_East_ccTLD_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_East_ccTLD_No_Resolve.yaml'                   , path: ./ruleset/GeoRouting_Europe_East_ccTLD_No_Resolve.yaml                   }
#   GeoRouting_Oceania_ccTLD_No_Resolve                       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Oceania_ccTLD_No_Resolve.yaml'                       , path: ./ruleset/GeoRouting_Oceania_ccTLD_No_Resolve.yaml                       }
#   GeoRouting_Antarctica_ccTLD_No_Resolve                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Antarctica_ccTLD_No_Resolve.yaml'                    , path: ./ruleset/GeoRouting_Antarctica_ccTLD_No_Resolve.yaml                    }
#   GeoRouting_Asia_East_ccTLD_No_Resolve                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_East_ccTLD_No_Resolve.yaml'                     , path: ./ruleset/GeoRouting_Asia_East_ccTLD_No_Resolve.yaml                     }
#   GeoRouting_Asia_EastSouth_ccTLD_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_EastSouth_ccTLD_No_Resolve.yaml'                , path: ./ruleset/GeoRouting_Asia_EastSouth_ccTLD_No_Resolve.yaml                }
#   GeoRouting_Asia_South_ccTLD_No_Resolve                    : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_South_ccTLD_No_Resolve.yaml'                    , path: ./ruleset/GeoRouting_Asia_South_ccTLD_No_Resolve.yaml                    }
#   GeoRouting_Asia_Central_ccTLD_No_Resolve                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_Central_ccTLD_No_Resolve.yaml'                  , path: ./ruleset/GeoRouting_Asia_Central_ccTLD_No_Resolve.yaml                  }
#   GeoRouting_Asia_West_ccTLD_No_Resolve                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_West_ccTLD_No_Resolve.yaml'                     , path: ./ruleset/GeoRouting_Asia_West_ccTLD_No_Resolve.yaml                     }
#   GeoRouting_Africa_North_ccTLD_No_Resolve                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_North_ccTLD_No_Resolve.yaml'                  , path: ./ruleset/GeoRouting_Africa_North_ccTLD_No_Resolve.yaml                  }
#   GeoRouting_Africa_South_ccTLD_No_Resolve                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_South_ccTLD_No_Resolve.yaml'                  , path: ./ruleset/GeoRouting_Africa_South_ccTLD_No_Resolve.yaml                  }
#   GeoRouting_Africa_West_ccTLD_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_West_ccTLD_No_Resolve.yaml'                   , path: ./ruleset/GeoRouting_Africa_West_ccTLD_No_Resolve.yaml                   }
#   GeoRouting_Africa_East_ccTLD_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_East_ccTLD_No_Resolve.yaml'                   , path: ./ruleset/GeoRouting_Africa_East_ccTLD_No_Resolve.yaml                   }
#   GeoRouting_Africa_Central_ccTLD_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_Central_ccTLD_No_Resolve.yaml'                , path: ./ruleset/GeoRouting_Africa_Central_ccTLD_No_Resolve.yaml                }
#
#
#   GeoRouting_America_North_ccTLD                            : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_North_ccTLD.yaml'                            , path: ./ruleset/GeoRouting_America_North_ccTLD.yaml                            }
#   GeoRouting_America_South_ccTLD                            : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_South_ccTLD.yaml'                            , path: ./ruleset/GeoRouting_America_South_ccTLD.yaml                            }
#   GeoRouting_Europe_West_ccTLD                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_West_ccTLD.yaml'                              , path: ./ruleset/GeoRouting_Europe_West_ccTLD.yaml                              }
#   GeoRouting_Europe_East_ccTLD                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_East_ccTLD.yaml'                              , path: ./ruleset/GeoRouting_Europe_East_ccTLD.yaml                              }
#   GeoRouting_Oceania_ccTLD                                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Oceania_ccTLD.yaml'                                  , path: ./ruleset/GeoRouting_Oceania_ccTLD.yaml                                  }
#   GeoRouting_Antarctica_ccTLD                               : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Antarctica_ccTLD.yaml'                               , path: ./ruleset/GeoRouting_Antarctica_ccTLD.yaml                               }
#   GeoRouting_Asia_East_ccTLD                                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_East_ccTLD.yaml'                                , path: ./ruleset/GeoRouting_Asia_East_ccTLD.yaml                                }
#   GeoRouting_Asia_EastSouth_ccTLD                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_EastSouth_ccTLD.yaml'                           , path: ./ruleset/GeoRouting_Asia_EastSouth_ccTLD.yaml                           }
#   GeoRouting_Asia_South_ccTLD                               : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_South_ccTLD.yaml'                               , path: ./ruleset/GeoRouting_Asia_South_ccTLD.yaml                               }
#   GeoRouting_Asia_Central_ccTLD                             : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_Central_ccTLD.yaml'                             , path: ./ruleset/GeoRouting_Asia_Central_ccTLD.yaml                             }
#   GeoRouting_Asia_West_ccTLD                                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_West_ccTLD.yaml'                                , path: ./ruleset/GeoRouting_Asia_West_ccTLD.yaml                                }
#   GeoRouting_Africa_North_ccTLD                             : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_North_ccTLD.yaml'                             , path: ./ruleset/GeoRouting_Africa_North_ccTLD.yaml                             }
#   GeoRouting_Africa_South_ccTLD                             : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_South_ccTLD.yaml'                             , path: ./ruleset/GeoRouting_Africa_South_ccTLD.yaml                             }
#   GeoRouting_Africa_West_ccTLD                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_West_ccTLD.yaml'                              , path: ./ruleset/GeoRouting_Africa_West_ccTLD.yaml                              }
#   GeoRouting_Africa_East_ccTLD                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_East_ccTLD.yaml'                              , path: ./ruleset/GeoRouting_Africa_East_ccTLD.yaml                              }
#   GeoRouting_Africa_Central_ccTLD                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_Central_ccTLD.yaml'                           , path: ./ruleset/GeoRouting_Africa_Central_ccTLD.yaml                           }
#
#
#   GeoRouting_America_North_ccTLD_Domain                     : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_North_ccTLD_Domain.yaml'                    , path: ./ruleset/GeoRouting_America_North_ccTLD_Domain.yaml                     }
#   GeoRouting_America_South_ccTLD_Domain                     : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_South_ccTLD_Domain.yaml'                    , path: ./ruleset/GeoRouting_America_South_ccTLD_Domain.yaml                     }
#   GeoRouting_Europe_West_ccTLD_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_West_ccTLD_Domain.yaml'                      , path: ./ruleset/GeoRouting_Europe_West_ccTLD_Domain.yaml                       }
#   GeoRouting_Europe_East_ccTLD_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_East_ccTLD_Domain.yaml'                      , path: ./ruleset/GeoRouting_Europe_East_ccTLD_Domain.yaml                       }
#   GeoRouting_Oceania_ccTLD_Domain                           : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Oceania_ccTLD_Domain.yaml'                          , path: ./ruleset/GeoRouting_Oceania_ccTLD_Domain.yaml                           }
#   GeoRouting_Antarctica_ccTLD_Domain                        : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Antarctica_ccTLD_Domain.yaml'                       , path: ./ruleset/GeoRouting_Antarctica_ccTLD_Domain.yaml                        }
#   GeoRouting_Asia_East_ccTLD_Domain                         : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_East_ccTLD_Domain.yaml'                        , path: ./ruleset/GeoRouting_Asia_East_ccTLD_Domain.yaml                         }
#   GeoRouting_Asia_EastSouth_ccTLD_Domain                    : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_EastSouth_ccTLD_Domain.yaml'                   , path: ./ruleset/GeoRouting_Asia_EastSouth_ccTLD_Domain.yaml                    }
#   GeoRouting_Asia_South_ccTLD_Domain                        : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_South_ccTLD_Domain.yaml'                       , path: ./ruleset/GeoRouting_Asia_South_ccTLD_Domain.yaml                        }
#   GeoRouting_Asia_Central_ccTLD_Domain                      : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_Central_ccTLD_Domain.yaml'                     , path: ./ruleset/GeoRouting_Asia_Central_ccTLD_Domain.yaml                      }
#   GeoRouting_Asia_West_ccTLD_Domain                         : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_West_ccTLD_Domain.yaml'                        , path: ./ruleset/GeoRouting_Asia_West_ccTLD_Domain.yaml                         }
#   GeoRouting_Africa_North_ccTLD_Domain                      : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_North_ccTLD_Domain.yaml'                     , path: ./ruleset/GeoRouting_Africa_North_ccTLD_Domain.yaml                      }
#   GeoRouting_Africa_South_ccTLD_Domain                      : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_South_ccTLD_Domain.yaml'                     , path: ./ruleset/GeoRouting_Africa_South_ccTLD_Domain.yaml                      }
#   GeoRouting_Africa_West_ccTLD_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_West_ccTLD_Domain.yaml'                      , path: ./ruleset/GeoRouting_Africa_West_ccTLD_Domain.yaml                       }
#   GeoRouting_Africa_East_ccTLD_Domain                       : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_East_ccTLD_Domain.yaml'                      , path: ./ruleset/GeoRouting_Africa_East_ccTLD_Domain.yaml                       }
#   GeoRouting_Africa_Central_ccTLD_Domain                    : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_Central_ccTLD_Domain.yaml'                   , path: ./ruleset/GeoRouting_Africa_Central_ccTLD_Domain.yaml                    }
#


#
# 注意： 上述洲际规则中，并没有包含 🇨🇳中国 ，中国需要使用单独规则：
#
#   GeoRouting_Asia_China_ccTLD_No_Resolve                     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_China_ccTLD_No_Resolve.yaml'                     , path: ./ruleset/GeoRouting_Asia_China_ccTLD_No_Resolve.yaml                     }
#   GeoRouting_Asia_China_ccTLD                                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_China_ccTLD.yaml'                                , path: ./ruleset/GeoRouting_Asia_China_ccTLD.yaml                                }
#   GeoRouting_Asia_China_ccTLD_Domain                         : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_China_ccTLD_Domain.yaml'                        , path: ./ruleset/GeoRouting_Asia_China_ccTLD_Domain.yaml                         }
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
