## 此规则集

  用于分流： Aqara 🇺🇸 美国 的流量


## 注意

  1. 目前 仅支持美国Aqara的分流 ，DIY更多地区的分流，请看官方API ： 
     - https://opendoc-test.aqara.cn/en/docs/developmanual/apiIntroduction/APIUsageGuide.html](https://opendoc-test.aqara.cn/en/docs/developmanual/apiIntroduction/APIUsageGuide.html
      - 注意：官方API并不全，并没有包含，aws相关的规则（可以参考 本规则内的keyword相关规则 和 IP规则 ）

  2. ⚠️⚠️⚠️ 只有 aqara国际版（如美国亚马逊自营销售的版本）才能使用上本规则
     - aqara国际版 
        只会将数据上传给境外的亚马逊云 （ 以及你设置的 境外苹果账户 所对应的 境外icloud云 ） ，从而 最大化避免\隔离 中国执法机构审查
     - aqara国内版 （🇨🇳中国版）
       存在巨大安全风险。其固件，会将录制的监控视频，自动上传到 🇨🇳 中国国内aqara服务器，已备中国的执法机构审查
       另外，国内版无法刷成 国际版。

  3. aqara国际版，是目前最好用 apple homekit 监控摄像头 
     - 记住，你的摄像头内，不要放TF存储卡，设置数据只上传到 🇺🇸 美国icloud云端，并同时开始苹果icloud的 “高级数据保护”，
     - 按照上述 设置后，除了你自己，没有任何人能看到你的监控摄像头 已录制的视频。 安全性远远高于 本地NAS 存储监控视频。
         
  4. 安全性最高 的 监控摄像头，只推荐 ： 
        - 不会连接中国服务器 的 homekit摄像头 （ + 海外icloud账号 + 开启高级数据保护 ） ❕❕❕ 




## 引用范例

```

   Aqara_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_No_Resolve.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_No_Resolve.yaml')                                    , path: ./ruleset/Aqara_No_Resolve.yaml                    }    

   Aqara                              : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara.yaml')                                               , path: ./ruleset/Aqara.yaml                               }                 

   Aqara_Domain                       : {type: http, behavior: domain    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_Domain.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_Domain.yaml')                                        , path: ./ruleset/Aqara_Domain.yaml                        }   
   Aqara_IP                           : {type: http, behavior: ipcidr    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_IP.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_IP.yaml')                                      , path: ./ruleset/Aqara_IP.yaml                         }

```


## 使用说明 ：⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️

本项目，包括 以下三组规则，“三选一”，选其中一个即可

  + 后缀：No_Resolve    （第一组）

  + 后缀：无        （第二组）

  + 后缀：Doamin        （第三组）
  + 后缀：IP

以上三组，三选一，优先选择最后一组（Domain + IP），在移动端（Stash for iOS），这种写法极大增加匹配速度和减少内存占用。
