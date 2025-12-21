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

+ 本项目，是否会长期维护？
  - 是的，本项目会长期维护。
  - 本项目，是从我长期自用的 “超级省电clash分流规则模版” 的内置规则中 拆分出来的。
  - 本项目，用于补充 “超级省电clash分流模版” 需要使用到， 但市面上却没有的， 规则集。
 
+ 上述提到的 “超级省电clash分流规则模版” 是什么 ？
   - 面向如下需求的Clash模版：
        - 🔥 移动端 极致省电  +  0 DNS泄漏  +  修改IP归属地显示  +  国内国外主流APP分流 
   - 项目地址：https://github.com/Accademia/Clash_Configuration_Template
   - 集成规则库： “ blackmatrix + geosite + 本规则集 ” ！


<br>
<br>
  
⚠️⚠️ 不看完 本项目的 说明，就想指挥别人当保姆的 。直接关闭issue + 100% 必拉黑 ⚠️⚠️

<br>
<br>

规则介绍 ：
----------------------------------

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

+ Bank		：各国银行 的 Clash分流规则
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

+ VirtualFinance : 虚拟金融公司 的 Clash分流规则
  - Paypal
  - Wise
  - Monzo
  - Revolut

+ GeoRouting_For_Domain ：按 国家顶级域名 的 Clash分流规则
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

+ GeoRouting_For_IP 	：按 GeoIP 的 Clash分流规则
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

+ GlobalDNS		：全球DNS，（可信的、无用户隐私泄漏的 DNS） 的 Clash分流规则

+ ChinaDNS		：中国大陆 DNS（被GFW污染的DNS） 的 Clash分流规则

+ HijackingPlus		：反有害网站（针对反诈插件） 的 Clash分流规则

+ WaybackMachine	：网络时光机（互联网档案馆）的 Clash分流规则

+ eMuleServer		：电驴目录服务器（不涉及P2P下载） 的 Clash分流规则

+ Alipan		: 阿里云盘 的 Clash分流规则

+ BaiduNetDisk		: 百度网盘 的 Clash分流规则

+ WeiYun		: 腾讯微云 的 Clash分流规则

+ RustDesk		: RustDesk 的 Clash分流规则

+ Parsec		: Parsec 的 Clash分流规则

+ Triller		: Triller 的 Clash分流规则 （此软件已经被官方关闭）

+ Signal		: Signal 的 Clash分流规则

+ AppleNews		: 苹果新闻 的 Clash分流规则

+ AppleAI		: 苹果智能 (apple intelligence) 的 Clash分流规则 

+ Grok			: xAI Grok AI 的 Clash分流规则

+ Gemini		: Google Gemini AI 的 Clash分流规则

+ Copilot		: Microsoft Copilot AI 的 Clash分流规则

+ MacAppUpgrade		: MacOS上第三方 App 自更新和重装（ 通过 homebrew、sparkle 框架 ） 的 Clash 分流规则

+ UnsupportVPN		: 不支持VPN的网站（除 银行、HomeIP 分流规则以外的 网站）

+ Pornhub	：P站 的 Clash分流规则

+ Aqara ：Aqara Homekit 监控摄像头 的 Clash分流规则

+ Kwai ：“Kwai“（快手国际版） 的 Clash分流规则

+ Fastly： Fastly CDN 的 Clash分流规则

+ Apple： 苹果 的 Clash分流规则

+ MicrosoftAPPs： 微软APP全家桶 的 Clash分流规则 
    + 不包含 ：AI服务、云VPS服务、搜索服务、Xbox、github

+ China ：🇨🇳 中国网站 的 Clash分流规则 
    + blackmatrix7/ios_rule_script/China 的 修正版 
    + 注释掉 18% 错误、冗余规则后，有效规则 = 约 3000条 

+ GeositeCN ：🇨🇳 中国网站 的 Clash分流规则
    + geosite:cn 的 修正版
    + 注释掉 29% 的 错误、冗余规则后，有效规则 = 约 4800条 

<br>
<br>


使用说明 ⚠️
----------------------------------

<br>

本项目，包括 以下三组规则，“三选一”，选其中一个即可:

三组的后缀，分别为：

  + 第一组: 
    + 后缀 ：No_Resolve	

  + 第二组: 
    + 后缀 ：无		

  + 第三组: 
    + 后缀 ：Doamin		
    + 后缀 ：IP  

以上三组，三选一!

优先选择最后一组（Domain + IP）,在移动端（Stash for iOS），最后一组的写法，极大增加匹配速度、减少内存占用。

由于iPhone的网络扩展内存上限只有 50 MB，一旦匹配速度下降，会非常容易导致网络内存崩溃（VPN崩溃）。换更快的DNS连接方式 和 使用（Domain + IP）规则，是移动端唯一的解决方案。

经本人测试后，实测非常有效，10万条Domain规则，使得Stash（移动端版Clash）在iOS上只占用24MB网络内存 (如果使用Classical规则，则网络内存占用是38MB～42MB)。这极大缓解VPN崩溃的问题（超过50MB内存占用会发生VPN崩溃）。发热也极大降低了。

    出处：https://stash.wiki/rules/rule-set 

解答：为什么有些规则，没有第三组？因为，如果规则中，包含大量的 非域名后缀 、非IP 规则，如 DOMAIN-KEYWORD 、 PROCESS-NAME 、 GeoIP 等等，则无法拆分出第三组。



<br>

<br>

特别注意 ❗️❗️❗️❗️❗️❗️❗️
----------------------------------
<br>

+ xAI Grok 分流规则 ❗️❗️❗️❗️❗️

    - 单纯设置分流规则，可能 Grok APP for iOS（仅APP端） 仍旧连不上，需要在Stash、Clash的配置文件中，对IPv6做特殊处理 ！！！

    - 具体请看这里的说明：
        - https://github.com/Accademia/Additional_Rule_For_Clash/edit/main/Grok/Readme.txt 

<br>

+ AppleAI (苹果智能 apple intelligence) 分流规则 ❗️❗️❗️❗️❗️

    -  🇨🇳 国行 iPhone 、 iPad （不含Mac），无需尝试❕❕ 已被苹果锁死 ❕❕
      
    - 具体可以看这里的说明：⚠️⚠️
        - https://github.com/Accademia/Additional_Rule_For_Clash/blob/main/AppleAI/Readme.txt
     
<br>
   
+ 存在交叉的 分流规则 

    - AppleAI 和 AppleNews ，这俩个 分流规则，两者存在交叉规则。建议：最好使用同一个节点配置的开关。以免出现相互干扰。
    
<br>
<br>

授权协议：
----------------------------------

+ 通过 MIT协议 分发

+ 本规则整理，来自于 xAI SuperGrok DeepSarch 和 xAI SuperGrok Think 的协助。 





