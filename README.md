规则集：
----------------------------------
面向Clash的分流规则

+ 用途： 作为 blackmatrix7/ios_rule_script的补充规则（填补其缺失的却则）
  - https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash 

+ 兼容的客户端：	
   - Stash （ for iOS/Mac ）
   - Clash Verga Rec （ for Mac/win ）

+ 为什么要建立新项目，而不是给原规则提issue？ 
  - blackmatrix7 作者无意扩展新规则，本规则也只是添加 本项目主 自己常用的 长期验证过的 规则

+ 推荐的clash分流规则模版？
   - 同时集成 “ blackmatrix + geosite + 本规则 ”  的 clash 模版
      - https://github.com/Accademia/Clash_Configuration_Template
   - 建议使用 chatgpt ，将你自己的规则 与 上述模版 做融合，扩充完善你自己的分流配置。

.


规则介绍 ：
----------------------------------

+ Pornhub	：P站 Clash分流规则

+ FakeLocation	: 国产APP 用户IP归属地显示（用户地理位置显示） Clash分流规则
  - Bilibili 	
      - 留言：立即生效
      - 主页：“连续挂”2周才生效   
  - 抖音 ：   	立即生效   
  - 快手 ：   	立即生效  
  - 小红书 ：  	立即生效  
  - 西瓜 ：    	立即生效
  - 微博 ：    	立即生效  
  - 知乎 ：    	立即生效 
  - 贴吧 ：    	2.5小时后 ！！！
  - 豆瓣 ：    	立即生效 
  - 闲鱼\淘宝 ：    	立即生效

+ Bank		：各国银行 Clash分流规则
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

+ VirtualFinance : 虚拟金融公司 Clash分流规则
  - Paypal
  - Wise
  - Monzo
  - Revolut

+ GeoRouting_For_Domain ：按 国家顶级域名 的Clash分流规则
  - 北美  # America (North America)       
  - 南美  # America (South America)       
  - 西欧  # Europe (East   Europe)        
  - 东欧  # Europe (West   Europe)        
  - 大洋  # Oceania                       
  - 南极  # Antarctica                    
  - 东亚  # Asia (East  Asia)             
  - 东南  # Asia (EastSouth Asia)         
  - 南亚  # Asia (South Asia)             
  - 中亚  # Asia (Central Asia)           
  - 西亚  # Asia (West Asia , Middle East)
  - 南非  # Africa (North   Africa)       
  - 北非  # Africa (South   Africa)       
  - 西非  # Africa (West    Africa)       
  - 东非  # Africa (East    Africa)       
  - 中非  # Africa (Central Africa)   

+ GeoRouting_For_IP 	：按 GeoIP 的Clash分流规则
  - 北美  # America (North America)       
  - 南美  # America (South America)       
  - 西欧  # Europe (East   Europe)        
  - 东欧  # Europe (West   Europe)        
  - 大洋  # Oceania                       
  - 南极  # Antarctica                    
  - 东亚  # Asia (East  Asia)             
  - 东南  # Asia (EastSouth Asia)         
  - 南亚  # Asia (South Asia)             
  - 中亚  # Asia (Central Asia)           
  - 西亚  # Asia (West Asia , Middle East)
  - 南非  # Africa (North   Africa)       
  - 北非  # Africa (South   Africa)       
  - 西非  # Africa (West    Africa)       
  - 东非  # Africa (East    Africa)       
  - 中非  # Africa (Central Africa)   

+ HomeIP		：必须要 “住宅IP” 才能正常下单的网站 

+ PreRepairEasyPrivacy	：对blackmatrix7种的“EasyPrivacy“和“AdvertisingLite”分流规则，进行修复 Clash分流规则

+ GlobalDNS		：全球DNS，（可信的、无用户隐私泄漏的 DNS）

+ ChinalDNS		：中国大陆 DNS（被GFW污染的DNS）

+ HijackingPlus		：反有害网站（针对反诈插件） 

+ WaybackMachine	：网络时光机（互联网档案馆）

+ eMuleServer		：电驴目录服务器（不涉及P2P下载）

+ Alipan		: 阿里云盘 Clash分流规则

+ BaiduNetDisk		: 百度网盘 Clash分流规则

+ WeiYun		: 腾讯微云 Clash分流规则

+ RustDesk		: RustDesk Clash分流规则

+ Parsec		: Parsec Clash分流规则

+ Triller		: Triller Clash分流规则

+ Signal		: Signal Clash分流规则

+ AppleAI		: 苹果AI (苹果 Siri AI) Clash分流规则 

+ Grok			: xAI Grok Clash分流规则

+ Gemini		: Google Gemini分流规则

+ MacAppUpgrade		: Homebrew App Install \ Upgrade  Clash 分流规则

+ UnsupportVPN		: 不支持VPN的网站（除 银行、HomeIP 分流规则以外的 网站）

+ AppleNews		: 苹果新闻 分流规则

.

使用说明 ⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️
----------------------------------

本项目，包括 以下三组规则，“三选一”，选其中一个即可:

三组的后缀，分别为：

  + 后缀：No_Resolve	（第一组）

  + 后缀：无		（第二组）

  + 后缀：Doamin	（第三组）	
  + 后缀：IP  （第三组） 

以上三组，三选一，优先选择最后一组（Domain + IP），在移动端（Stash for iOS），这种写法极大增加匹配速度和减少内存占用。

由于iPhone的网络扩展内存上限只有 50 MB，一旦匹配速度下降，会非常容易导致网络内存崩溃（VPN崩溃）。换更快的DNS连接方式 和 使用（Domain + IP）规则，是移动端唯一的解决方案。

经本人测试后，实测非常有效，10万条Domain规则，使得Stash（移动端版Clash）在iOS上只占用24MB网络内存 (如果使用Classical规则，则网络内存占用是38MB～42MB)。这极大缓解VPN崩溃的问题（超过50MB内存占用会发生VPN崩溃）。发热也极大降低了。

出处：https://stash.wiki/rules/rule-set 

要特别说明的是：如果规则中，包含大量的 非域名后缀 、非IP 规则，如 DOMAIN-KEYWORD 、 PROCESS-NAME 、 GeoIP 等等，则无法拆分出第三组。




.

特别注意 ❗️❗️❗️❗️❗️❗️❗️
----------------------------------

+ xAI Grok 分流规则 ❗️❗️❗️❗️❗️

    - ⚠️⚠️  如果在 Stash For iOS 上使用 Grok分流规则，必须在Stash面板中，手动开启IPv6分流，不然Grok APP for iOS 会非常难以连接。甚至无法连接 ！！！！！！！
 
    - 开启路径为： Stash -> 设置 -> 网络设置 -> 启用 Tunnel IPV6 路由


+ AppleAI (苹果智能) 分流规则 ❗️❗️❗️❗️❗️

    - ⚠️⚠️ 注意：
    	- 如果你的 iOS （ iPhone \ iPad ） 是 🇨🇳 国行设备 ，即便配置了本分流规则也没用。不会调用 🇺🇸 美区AppleAI ❕❕❕
		- 如果你的 Mac是 🇨🇳 国行设备 ，可以通过 enableAppleAI 脚本，绕过上述iOS的限制。
    	- 非国行设备，不受上述限制。
      
    - 在国行MacOS上，如何强行启用 “美区Apple AI” 选项 ？
        - 请移步这个项目，https://github.com/kanshurichard/enableAppleAI  .此项目 使用时需注意以下2点：
            -  必须 🇺🇸 美区ID（不能不登录ID） + 系统地区选择美国（非中国地区）
            	- 🇺🇸 美区ID = iCloud 美区ID + AppStore 美区ID （两者同时部署） 	
            -  每次大版本升级（如v26 -> v27 ），需要重新跑一遍本脚本
            
    -  在 “启用AppleAI” 后，如何在 Siri中 绑定ChatGPT ？
        -   绑定过程，系统内有IP锁。通过 AppleAI规则，可绕过IP锁，成功绑定
        
    - 在 “绑定ChatGPT” 后，如何让Apple AI只调用 🇺🇸 美区AppleAI（ChatGPT），而不调用 🇨🇳 国内AI（文心一言）？
        -  调用过程，有 《 LBS锁+ IP锁 》 。苹果会通过 “GPS位置+ IP归属地” 来判定你是否在中国，如果在，则不会调用ChatGPT。只会调用 🇨🇳 文心一言。
        -  解除LBS锁：禁用siri获取 地理位置 ，
        	-  设置 -> 隐私与安全性 -> 定位服务 -> Siri -> 关闭
     
	- 以上步骤看不懂的，具体可以看这里的说明：
       - https://github.com/Accademia/Additional_Rule_For_Clash/blob/main/AppleAI/Readme.txt


.

授权协议：
----------------------------------

+ 通过 MIT协议 分发

+ 本规则整理，来自于 xAI SuperGrok DeepSarch 和 xAI SuperGrok Think 的协助。 





