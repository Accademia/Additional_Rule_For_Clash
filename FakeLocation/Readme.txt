
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
#	闲鱼\淘宝     	立即生效
#
#
# 注意；⚠️⚠️⚠️
#	怀疑快手的IP归属地，有某种二次验证机制，导致使用一段时间后，指定的IP归属地失败。
#	而且这种二次验证，和闲鱼有些类似，看似不是域名访问，而是IP访问。哪怕分流了所有域名都无效。
#	由于，快手的二次验证是延迟起效的，所以，暂不做处理，希望有人实锤后，能够提Issue反馈。
#
#
# 使用方法：
#	在Stash上，需要在使用前，调用如下规则，否则部分规则会调用失败
#		GEOSITE , category-ads , REJECT
#		以及
#		https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/EasyPrivacy 
#	原因是因为Stash不支持远程规则集中使用REJECT，作者也坚决不改，反馈说用户用不到😂😂
#	Clash Verge Rev不会有此问题。
#	
# 注意：
#	1. 最好将出境VPS IP和入境IP分开，以防止被GFW封杀。即，强烈建议使用双IP（出入站不同IP）的VPS主机。
#	2. ⚠️⚠️⚠️ 请不要在Stash中，使用仅 “仅使用Tunnel代理”，不然会导致，小红书、抖音的 “IP归属地” 修改不生效
#
#


⚠️ 建议：先引用 blackmatrix  + geosite 中的 httpdns 规则 ，并阻断。然后再使用上述修改ip归属地规则。
        虽然 已经在规则中引入了httpdns阻断，但是 更新即时性 肯定没有其他远程规则集即时维护频度高
        如果你还是改不了ip归属地，建议使用 “超级省电clash模版”。
        这是本人自用验证过的。100%可改ip归属地。



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

