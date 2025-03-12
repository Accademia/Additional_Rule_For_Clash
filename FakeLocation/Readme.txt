
# -----------------------------------------
# 此规则集：针对（国内网站）IP地理位置展示，进行分流
# -----------------------------------------

# 用途：
#	人在美国刚下飞机 的 的装逼利器！！！！
#	对于国内主要社交属性的平台，给予VPN指定的IP地理位置展示
#
#	BiliBili  	留言：立即生效	主页：不间断挂14天后才会生效！！！！
#	抖音    		立即生效   
#	快手     	立即生效  
#	小红书   		立即生效  
#	西瓜     	立即生效
#	微博     	立即生效  
#	知乎     	立即生效 
#	贴吧     	2.5小时后 ！！！！！（百度的垃圾，真已无可救药）
#	豆瓣     	立即生效 
#	闲鱼     	立即生效
#	
# 注意：
#	最好将出境VPS IP和入境IP分开，以防止被GFW封杀。即，强烈建议使用双IP（出入站不同IP）的VPS主机。
#
#
# 引用范例 ：
#
#   FakeLocationBiliBili_No_Resolve     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationBiliBili_No_Resolve.yaml'            , path:./ruleset/FakeLocationBiliBili_No_Resolve.yaml        }
#   FakeLocationDouYin_No_Resolve       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouYin_No_Resolve.yaml'              , path:./ruleset/FakeLocationDouYin_No_Resolve.yaml          }
#   FakeLocationKuaiShou_No_Resolve     : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationKuaiShou_No_Resolve.yaml'            , path:./ruleset/FakeLocationKuaiShou_No_Resolve.yaml        }
#   FakeLocationXiaoHongShu_No_Resolve  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiaoHongShu_No_Resolve.yaml'         , path:./ruleset/FakeLocationXiaoHongShu_No_Resolve.yaml     }
#   FakeLocationXiGua_No_Resolve        : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiGua_No_Resolve.yaml'               , path:./ruleset/FakeLocationXiGua_No_Resolve.yaml           }
#   FakeLocationWeiBo_No_Resolve        : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationWeiBo_No_Resolve.yaml'               , path:./ruleset/FakeLocationWeiBo_No_Resolve.yaml           }
#   FakeLocationZhiHu_No_Resolve        : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationZhiHu_No_Resolve.yaml'               , path:./ruleset/FakeLocationZhiHu_No_Resolve.yaml           }
#   FakeLocationTieBa_No_Resolve        : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationTieBa_No_Resolve.yaml'               , path:./ruleset/FakeLocationTieBa_No_Resolve.yaml           }
#   FakeLocationDouBan_No_Resolve       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouBan_No_Resolve.yaml'              , path:./ruleset/FakeLocationDouBan_No_Resolve.yaml          }
#   FakeLocationXianYu_No_Resolve       : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXianYu_No_Resolve.yaml'              , path:./ruleset/FakeLocationXianYu_No_Resolve.yaml          }
#
#   FakeLocationBiliBili                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationBiliBili.yaml'                       , path:./ruleset/FakeLocationBiliBili.yaml                   }
#   FakeLocationDouYin                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouYin.yaml'                         , path:./ruleset/FakeLocationDouYin.yaml                     }
#   FakeLocationKuaiShou                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationKuaiShou.yaml'                       , path:./ruleset/FakeLocationKuaiShou.yaml                   }
#   FakeLocationXiaoHongShu             : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiaoHongShu.yaml'                    , path:./ruleset/FakeLocationXiaoHongShu.yaml                }
#   FakeLocationXiGua                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiGua.yaml'                          , path:./ruleset/FakeLocationXiGua.yaml                      }
#   FakeLocationWeiBo                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationWeiBo.yaml'                          , path:./ruleset/FakeLocationWeiBo.yaml                      }
#   FakeLocationZhiHu                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationZhiHu.yaml'                          , path:./ruleset/FakeLocationZhiHu.yaml                      }
#   FakeLocationTieBa                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationTieBa.yaml'                          , path:./ruleset/FakeLocationTieBa.yaml                      }
#   FakeLocationDouBan                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouBan.yaml'                         , path:./ruleset/FakeLocationDouBan.yaml                     }
#   FakeLocationXianYu                  : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXianYu.yaml'                         , path:./ruleset/FakeLocationXianYu.yaml                     }
#
#
#
# 第三方规则参考
# 参考1（anti-ip-attribution）：https://github.com/SunsetMkt/anti-ip-attribution/blob/main/rules.yaml
# 参考2 (bilibili-rule) : https://github.com/elysias123/bilibili-rule/blob/main/bilibili.yaml