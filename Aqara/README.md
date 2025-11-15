## 此规则集

  用于分流： 
   - AqaraGlobal 境外 的流量
   - AqaraCN 国内 的流量


.


## 引用范例

境外规则

```

   AqaraGlobal_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_No_Resolve.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal_No_Resolve.yaml')                                    , path: ./ruleset/AqaraGlobal_No_Resolve.yaml                    }    

   AqaraGlobal                              : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal.yaml')                                               , path: ./ruleset/AqaraGlobal.yaml                               }                 

   AqaraGlobal_Domain                       : {type: http, behavior: domain    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_Domain.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal_Domain.yaml')                                        , path: ./ruleset/AqaraGlobal_Domain.yaml                        }   
   AqaraGlobal_IP                           : {type: http, behavior: ipcidr    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_IP.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraGlobal_IP.yaml')                                      , path: ./ruleset/AqaraGlobal_IP.yaml                         }

```

国内规则

```

   AqaraCN_No_Resolve                   : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_No_Resolve.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN_No_Resolve.yaml')                                    , path: ./ruleset/AqaraCN_No_Resolve.yaml                    }    

   AqaraCN                              : {type: http, behavior: classical , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN.yaml')                                               , path: ./ruleset/AqaraCN.yaml                               }                 

   AqaraCN_Domain                       : {type: http, behavior: domain    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_Domain.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN_Domain.yaml')                                        , path: ./ruleset/AqaraCN_Domain.yaml                        }   
   AqaraCN_IP                           : {type: http, behavior: ipcidr    , interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/Aqara_IP.yaml'](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/Aqara/AqaraCN_IP.yaml')                                      , path: ./ruleset/AqaraCN_IP.yaml                         }

```

. 


## 使用说明 ：

本项目，包括 以下三组规则，“三选一”，选其中一个即可

  + 后缀：No_Resolve    （第一组）

  + 后缀：无        （第二组）

  + 后缀：Doamin        （第三组）
  + 后缀：IP

以上三组，三选一，优先选择最后一组（Domain + IP），在移动端（Stash for iOS），这种写法极大增加匹配速度和减少内存占用。

.

## 使用建议：

   - 对于追求绝对安全性：
       - 将本规则应用在路由器上，而非手机上 ⚠️⚠️ 屏蔽所有Aqara对自家服务器的连接（包括境内和国外），从而使得aqara只连接 苹果Homekit，做到摄像头数据安全的最大安全性（避免上传数据到苹果以外的服务器）
       - 注意，升级过程，需要连接aqara服务器。可以手动打开。

   - 对于追求 避开中国监管：
       - 将本规则应用在路由器上，只屏蔽中国区的aqara连接。

   - 对于追求 aqara官方APP 的连接速度：
       - 将本规则 应用在手机上，并全部给予 Direct 放行 ！
       
.


## 注意


  1. aqara 官方API如下 ： 
     - https://opendoc-test.aqara.cn/en/docs/developmanual/apiIntroduction/APIUsageGuide.html](https://opendoc-test.aqara.cn/en/docs/developmanual/apiIntroduction/APIUsageGuide.html
      - 注意：官方API并不全，并没有包含，aws相关的规则（可以参考 本规则内的keyword相关规则 和 IP规则 ）

  2. ⚠️⚠️⚠️  aqara国际版（如美国亚马逊自营销售的版本）与国内版区别
     - aqara国际版 
        只会将数据上传给境外的亚马逊云 （ 以及你设置的 境外苹果账户 所对应的 境外icloud云 ） ，从而 最大化避免\隔离 中国执法机构审查
     - aqara国内版 （🇨🇳中国版）
       存在巨大安全风险。其固件，会将录制的监控视频，自动上传到 🇨🇳 中国国内aqara服务器，已备中国的执法机构审查
       另外，国内版无法刷成 国际版。

  3. aqara国际版，是目前最好用 apple homekit 监控摄像头 
     - 记住，你的摄像头内，不要放TF存储卡，设置数据只上传到 🇺🇸 美国icloud云端，并同时开始苹果icloud的 “高级数据保护”，
     - 按照上述 设置后，除了你自己，没有任何人能看到你的监控摄像头 已录制的视频。 安全性远远高于 本地NAS 存储监控视频。
         
  4. 安全性最高 的 监控摄像头，只推荐 ： 
        - 不会连接中国服务器 和 服务商自己服务器 的 homekit摄像头 （ + 海外icloud账号 + 开启高级数据保护 ） ❕❕❕ 


.


## 其他

![20CAD1E5-37D0-459C-A74D-30D66B7184DC](https://github.com/user-attachments/assets/368653f6-115f-4e18-9e0a-a0bb8da3643b)



