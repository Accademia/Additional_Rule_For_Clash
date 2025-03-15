+ 规则集：面向Clash的分流规则

+ 用途： 作为 blackmatrix7/ios_rule_script的补充规则（填补其缺失的却则）

+ 被填补的规则集合：blackmatrix7/ios_rule_script - https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash 

+ 兼容的客户端：	Stash for iOS/Mac
		Clash Verga Rec for Mac/win10

+ 为什么要建立新项目，而不是给原规则提issue？ 
	- 因为原规则作者无意扩展新规则（原作者精力不够的问题，可以理解，毕竟是用爱发电。而且本规则也只是添加本项目主 自己常用的 长期验证过的 规则）

----------------------------------

使用说明：

+ Pornhub		：P站 Clash分流规则

+ FakeLocation		: 国产APP 用户IP归属地显示（用户地理位置显示） Clash分流规则
	- Bilibili    	立即生效（留言立即生效，但主页IP归属地，需要“连续挂”2周才会生效）   
	- 抖音    	立即生效   
	- 快手     	立即生效  
	- 小红书   	立即生效  
	- 西瓜     	立即生效
	- 微博     	立即生效  
	- 知乎     	立即生效 
	- 贴吧     	2.5小时后 ！！！！！（百度的垃圾，真已无可救药）
	- 豆瓣     	立即生效 
	- 闲鱼     	立即生效

+ Bank			：各国银行 Clash分流规则
	- 美国银行
	- 加拿大银行
	- 英国银行
	- 澳大利亚银行
	- 日本银行
 	- 香港银行
	- 新加坡银行
	- 荷兰银行
	- 法国银行
	- 德国银行

+ VirtualFinance	: 虚拟金融公司 Clash分流规则
	- Paypal
	- Wise
	- Monzo
	- Revolut

+ GeoRouting_For_Domain ：按 国家顶级域名 的Clash分流规则
	- 北美     # America (North America)       
	- 南美     # America (South America)       
	- 西欧     # Europe (East   Europe)        
	- 东欧     # Europe (West   Europe)        
	- 大洋     # Oceania                       
	- 南极     # Antarctica                    
	- 东亚     # Asia (East  Asia)             
	- 东南     # Asia (EastSouth Asia)         
	- 南亚     # Asia (South Asia)             
	- 中亚     # Asia (Central Asia)           
	- 西亚     # Asia (West Asia , Middle East)
	- 南非     # Africa (North   Africa)       
	- 北非     # Africa (South   Africa)       
	- 西非     # Africa (West    Africa)       
	- 东非     # Africa (East    Africa)       
	- 中非     # Africa (Central Africa)   

+ GeoRouting_For_IP 	：按 GeoIP 的Clash分流规则
	- 北美     # America (North America)       
	- 南美     # America (South America)       
	- 西欧     # Europe (East   Europe)        
	- 东欧     # Europe (West   Europe)        
	- 大洋     # Oceania                       
	- 南极     # Antarctica                    
	- 东亚     # Asia (East  Asia)             
	- 东南     # Asia (EastSouth Asia)         
	- 南亚     # Asia (South Asia)             
	- 中亚     # Asia (Central Asia)           
	- 西亚     # Asia (West Asia , Middle East)
	- 南非     # Africa (North   Africa)       
	- 北非     # Africa (South   Africa)       
	- 西非     # Africa (West    Africa)       
	- 东非     # Africa (East    Africa)       
	- 中非     # Africa (Central Africa)   

+ HomeIP		：必须要 “住宅IP” 才能正常访问（或正常下单）的网站 

+ PreRepairEasyPrivacy	：（安全类分流规则）对blackmatrix7种的“EasyPrivacy“和“AdvertisingLite”分流规则，进行修复 Clash分流规则

+ GlobalDNS		：（安全类分流规则）全球DNS分流规则 ，（仅包含：可信的、无用户隐私泄漏的 DNS）

+ ChinalDNS		：（安全类分流规则）中国大陆 DNS分流规则（仅包含：中国大陆DNS，被GFW污染的DNS）

+ HijackingPlus		：（安全类分流规则）反有害网站（主要针对反诈非法监控用户） Clash分流规则 （未来会包括哄蒙非法监听用户的规则）

+ WaybackMachine	：网络时光机（互联网档案馆） Clash分流规则

+ eMuleServer		：电驴目录服务器的Clash分流规则（不涉及P2P直连阶段的下载）

+ Alipan		: 阿里云盘 Clash分流规则 

+ RustDesk		: （远程控制、云桌面）RustDesk Clash分流规则

+ Parsec		: （远程控制、云桌面）Parsec Clash分流规则

+ Triller		: （美国短视频平台）Triller Clash分流规则

+ Signal		: （端到端加密即时通信软件）Signal Clash分流规则



----------------------------------
授权协议：
----------------------------------

MIT协议





----------------------------------
#  耻辱榜！ 
----------------------------------

#  宁波上官科技有限公司，此公司，是我见见过的最恶心的中国MAC软件公司之一，区别对待中国人和外国人，
#  其homebrew更新和安装，只能外国人使用。对所有中国用户进行屏蔽。妥妥的中国人与狗不得入内。而且还窥探用户隐私！无耻至极！！！！
#  不信的可以执行这条命令试试：
#    brew install --force --cask flykey
#
#  在中国，结果必然是403错误，也就意味着中国IP不能使用Homebrew下载他们的APP。。妥妥的中国人与狗不得入内。🤣🤣🤣🤣🤣🤣🤣🤣
#
# 导致分流规则中，必须添加对这个中国公司的翻墙规则！！！！ 无耻至极！！
