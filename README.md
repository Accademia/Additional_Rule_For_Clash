# 规则集：

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
  
⚠️⚠️ 不看完 规则集合 中的 说明自述（以及当前自述汇总），就想指挥别人当保姆的 。🤣 直接 0 社交 关闭issue⚠️⚠️

本规则集 = 高强度 自用级验证， 实锤 = 高精度 + 100% 可用，如果你分流失败，建议用 “ 超级省电clash分流规则模版 ” 进行二次验证，以便排除是否是您自己配置文件bug引发的问题。
<br>
<br>

# 规则介绍 ：

+ [FakeLocation](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/FakeLocation)	: 国产APP 用户IP归属地显示（用户地理位置显示） Clash分流规则
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
  
+ [Bank](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Bank)		：各国银行 的 Clash分流规则
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

+ [VirtualFinance](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/VirtualFinance) : 虚拟金融公司 的 Clash分流规则
  - Paypal
  - Wise
  - Monzo
  - Revolut

+ [GeoRouting_For_Domain](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/GeoRouting_For_Domain) ：按 国家顶级域名 的 Clash分流规则
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

+ [GeoRouting_For_IP](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/GeoRouting_For_IP) 	：按 GeoIP 的 Clash分流规则
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

+ [HomeIP](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/HomeIP)		：必须要 “住宅IP” 才能正常下单的网站 

+ [PreRepairEasyPrivacy](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/PreRepairEasyPrivacy)	：对blackmatrix7种的“EasyPrivacy“和“AdvertisingLite”分流规则，进行修复 Clash分流规则

+ [GlobalDNS](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/GlobalDNS)		：全球DNS，（可信的、无用户隐私泄漏的 DNS） 的 Clash分流规则

+ [ChinaDNS](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/ChinaDNS)		：中国大陆 DNS（被GFW污染的DNS） 的 Clash分流规则

+ [HijackingPlus](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/HijackingPlus)		：反有害网站（针对反诈插件） 的 Clash分流规则

+ [WaybackMachine](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/WaybackMachine)	：网络时光机（互联网档案馆）的 Clash分流规则

+ [eMuleServer](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/eMuleServer)		：电驴目录服务器（不涉及P2P下载） 的 Clash分流规则

+ [Alipan](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Alipan)		: 阿里云盘 的 Clash分流规则

+ [BaiduNetDisk](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/BaiduNetDisk)		: 百度网盘 的 Clash分流规则

+ [WeiYun](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/WeiYun)		: 腾讯微云 的 Clash分流规则

+ [RustDesk](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/RustDesk)		: RustDesk 的 Clash分流规则

+ [Parsec](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Parsec)		: Parsec 的 Clash分流规则

+ [Signal](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Signal)		: Signal 的 Clash分流规则

+ [AppleNews](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/AppleNews)		: 苹果新闻 的 Clash分流规则

+ [AppleAI](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/AppleAI)		: 苹果智能 (apple intelligence) 的 Clash分流规则 

+ [Grok](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Grok)			: xAI Grok AI 的 Clash分流规则

+ [Gemini](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Gemini)		: Google Gemini AI 的 Clash分流规则

+ [Copilot](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Copilot)		: Microsoft Copilot AI 的 Clash分流规则

+ [MacAppUpgrade](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/MacAppUpgrade)		: MacOS上第三方 App 自更新和重装（ 通过 homebrew、sparkle 框架 ） 的 Clash 分流规则

+ [Pornhub](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Pornhub)	：P站 的 Clash分流规则

+ [Aqara](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Aqara) ：Aqara Homekit 监控摄像头 的 Clash分流规则

+ [Kwai](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Kwai) ：“Kwai“（快手国际版） 的 Clash分流规则

+ [Fastly](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Fastly)： Fastly CDN 的 Clash分流规则

+ [Apple](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Apple)： 苹果 的 Clash分流规则

+ [MicrosoftAPPs](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/MicrosoftAPPs)： 微软APP全家桶 的 Clash分流规则 
    + 不包含 ：AI服务、云VPS服务、搜索服务、Xbox、github、LinkedIn
    + 包含：Windows操作系统 的 系统更新 和 各种内置 、Office 、 以及其他 微软客户端APP

+ [UnsupportVPN](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/UnsupportVPN)		: 不支持VPN的网站（除 银行、HomeIP 分流规则以外的 网站）
  + 与HomeIP分流规格的区别，如 ： 
     - HomeIPUS     = 必须 🇺🇸 美国住宅IP 才能访问的网站
     - UnsupportVPN = 只要是 非机房IP / 非VPN IP ，都能访问的网站（无论是否是住宅IP）

+ [China](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/China) ：🇨🇳 中国网站 的 Clash分流规则 
    + [blackmatrix7/ios_rule_script/China](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/China) 的 修正版 
    + 注释掉 18% 错误、冗余规则后，有效规则 = 约 3,000条 

+ [GeositeCN](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/GeositeCN) ：🇨🇳 中国网站 的 Clash分流规则
    + [v2fly/geosite:cn](https://github.com/v2fly) 的 修正版
    + 注释掉 29% 的 错误、冗余规则后，有效规则 = 约 4,800条 

+ [ChinaMax](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/ChinaMax) ：🇨🇳 中国网站 的 Clash分流规则 
    + [blackmatrix7/ios_rule_script/ChinaMax](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaMax) 的 修正版 
    + 注释掉 17% 错误、冗余规则后，有效规则 = 约 98,000条 
    + 其清洗粒度，不及GeositeCN。具体请看此规则说明

<br>
<br>


# 使用说明 ⚠️

<br>

本项目，包括 以下三组规则，“三选一”，选其中一个即可:

| 分组 | 后缀 | 建议 |
| --- | --- | --- |
| 第一组 | No_Resolve |  |
| 第一组 | 无 |  |
| 第一组 | Domain \ IP | 🔥 最优 |

优先选择最后一组（Domain + IP），极大增加匹配速度、减少内存占用。

 - 由于iPhone的网络扩展内存上限只有 50 MB，一旦匹配速度下降，会非常容易导致网络内存崩溃（VPN崩溃）。换更快的DNS连接方式 和 使用（Domain + IP）规则，是移动端唯一的解决方案。

  - 经本人测试后，实测非常有效，10万条Domain规则，使得Stash（移动端版Clash）在iOS上只占用24MB网络内存 (如果使用Classical规则，则网络内存占用是38MB～42MB)。这极大缓解VPN崩溃的问题（超过50MB内存占用会发生VPN崩溃）。发热也极大降低了。

  - 出处：https://stash.wiki/rules/rule-set 


<br>

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

 - [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88) 


<br>

解答：为什么有些规则，没有第三组，如FakeLocation（修改IP归属地）？

  - 因为，如果规则中，包含大量的 非域名后缀 、非IP 规则，如 DOMAIN-KEYWORD 、 PROCESS-NAME 、 GeoIP 等等，则无法拆分出第三组。在此类规则用，自用级验证的规则 = 无任何后缀的规则。


<br>

<br>

# 特别注意 ❗️❗️❗️❗️❗️❗️❗️
<br>

+ [FakeLocation](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/FakeLocation)	 分流规则 ❗️❗️❗️❗️❗️
  
  - 由于Stash作者 “拒绝支持” 一些必备特性。❌❌❌ 所以，本规则，不保证在 Stash for iOS 中可以100%生效，仅完美兼容Clash Meta，具体可以看此规则的详情页。


<br>

+ [xAI Grok](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/Grok) 分流规则 ❗️❗️❗️❗️❗️

    - 单纯设置分流规则，可能 Grok APP for iOS（仅APP端） 仍旧连不上，需要在Stash、Clash的配置文件中，对IPv6做特殊处理 ！！！

    - 具体请看这里的说明：
        - https://github.com/Accademia/Additional_Rule_For_Clash/edit/main/Grok

<br>

+ [AppleAI](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/AppleAI) (苹果智能 apple intelligence) 分流规则 ❗️❗️❗️❗️❗️

    -  🇨🇳 国行 iPhone 、 iPad （不含Mac），无需尝试❕❕ 已被苹果锁死 ❕❕
      
    - 具体可以看这里的说明：⚠️⚠️
        - https://github.com/Accademia/Additional_Rule_For_Clash/blob/main/AppleAI
     
<br>
   
+ 存在交叉的 分流规则 

    -  [AppleAI](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/AppleAI)  和 [AppleNews](https://github.com/Accademia/Additional_Rule_For_Clash/tree/main/AppleNews)	 ，这俩个 分流规则，两者存在交叉规则。建议：最好使用同一个节点配置的开关。以免出现相互干扰。
    
<br>
<br>

# 授权协议：

<br>

+ 通过 MIT协议 分发

+ 本规则整理，来自于 xAI SuperGrok DeepSarch 和 xAI SuperGrok Think 的协助。
