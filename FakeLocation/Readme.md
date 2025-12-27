
# FakeLocation 国内应用 IP 地理位置伪装规则集

### 项目简述

* **用途：** 针对国内主要社交平台，通过 VPN 指定 IP 地理位置展示。
* **场景：** 想要修改 Bilibili、抖音、微博等平台的 IP 归属地展示（俗称“装逼利器”）。

<br>

### ⚠️ 核心警告与使用建议

在使用本规则前，请务必阅读以下注意事项，以确保规则生效：

1.  **⚠️ 客户端兼容性警告**：
    * ✅✅✅ **Clash Meta** ：保证 **100% 生效**。
    * ❌❌❌ **Stash for iOS**：**不保证 100% 生效**。
    * *原因*：Stash 目前拒绝支持在远程规则集中识别 `Reject` / `Reject-drop` / `DIRECT` 。而伪装 IP 必须阻断 `httpdns`（需预置 reject）。多次对开发者沟通，对方客服，不是压根不回复，要么就是 “我们没问题，不需要改❕❕❕” 😠😠😠 什么玩意

2.  **⚠️ 模式设置**：
    * 请**不要**使用仅 “Tunnel 代理” 模式，否则会导致小红书、抖音的 IP 修改失效。

3.  **⚠️ 前置条件 (重要)**：
    * 建议先引用 **blackmatrix + geosite** 中的 `httpdns` 规则并进行**阻断**。
    * 然后再使用本规则集。
    * *备选方案*：如果无法修改 IP，建议使用“超级省电 Clash 模版”，经验证可 100% 修改归属地。

<br>
<br>

---

# 📱 支持平台与生效时效
<br>

以下是各平台应用本规则后的生效情况说明：

| 平台应用 | 生效时效说明 | 备注 |
| :--- | :--- | :--- |
| **BiliBili (B站)** | **留言：** 立即生效 <br> **主页：** 需挂机 **14天** 后生效 | ⚠️ 主页显示需要不间断挂 14 天 |
| **抖音 / 快手** | **立即生效** | - |
| **小红书 / 西瓜** | **立即生效** | - |
| **微博 / 知乎 / 豆瓣** | **立即生效** | - |
| **闲鱼 / 淘宝** | **立即生效** | - |
| **百度贴吧** | **2.5 小时后** | 百度系应用特性，生效较慢 |

<br>
<br>

---

# 引用配置范例
<br>

请在您的 Clash / Stash 配置文件中参考以下格式引入。

### 📦 规则文件后缀说明 (三选一)

本项目提供三组不同后缀的规则文件，请根据您的客户端和需求，**任选其一**即可。

| 后缀类型 | 说明 | 适用场景 |
| :--- | :--- | :--- |
| **No_Resolve** | 包含 `no-resolve` 策略 | 第一组 |
| **(无后缀)** | 标准 Classical 格式 | 第二组 |
| **Domain** | 纯域名 / IP 列表 | **🔥🔥🔥 移动端 (Stash for iOS) 推荐** <br> 极大增加匹配速度并减少内存占用 |

<br>

## 1. No-Resolve 策略引用
<br>

```yaml
# ---------------------------------------------------
#  FakeLocation - 引用示例 (No-Resolve 版)
# ---------------------------------------------------

FakeLocationBiliBili_No_Resolve     : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationBiliBili_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationBiliBili_No_Resolve.yaml)',    path: ./ruleset/FakeLocationBiliBili_No_Resolve.yaml    }
FakeLocationDouYin_No_Resolve       : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouYin_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouYin_No_Resolve.yaml)',      path: ./ruleset/FakeLocationDouYin_No_Resolve.yaml      }
FakeLocationKuaiShou_No_Resolve     : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationKuaiShou_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationKuaiShou_No_Resolve.yaml)',    path: ./ruleset/FakeLocationKuaiShou_No_Resolve.yaml    }
FakeLocationXiaoHongShu_No_Resolve  : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiaoHongShu_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiaoHongShu_No_Resolve.yaml)', path: ./ruleset/FakeLocationXiaoHongShu_No_Resolve.yaml }
FakeLocationXiGua_No_Resolve        : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiGua_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiGua_No_Resolve.yaml)',       path: ./ruleset/FakeLocationXiGua_No_Resolve.yaml       }
FakeLocationWeiBo_No_Resolve        : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationWeiBo_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationWeiBo_No_Resolve.yaml)',       path: ./ruleset/FakeLocationWeiBo_No_Resolve.yaml       }
FakeLocationZhiHu_No_Resolve        : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationZhiHu_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationZhiHu_No_Resolve.yaml)',       path: ./ruleset/FakeLocationZhiHu_No_Resolve.yaml       }
FakeLocationTieBa_No_Resolve        : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationTieBa_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationTieBa_No_Resolve.yaml)',       path: ./ruleset/FakeLocationTieBa_No_Resolve.yaml       }
FakeLocationDouBan_No_Resolve       : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouBan_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouBan_No_Resolve.yaml)',      path: ./ruleset/FakeLocationDouBan_No_Resolve.yaml      }
FakeLocationXianYu_No_Resolve       : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXianYu_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXianYu_No_Resolve.yaml)',      path: ./ruleset/FakeLocationXianYu_No_Resolve.yaml      }

```

<br>

## 2. 标准策略引用 (Classical)
<br>

```yaml
# ---------------------------------------------------
#  FakeLocation - 引用示例 (标准版)
# ---------------------------------------------------

FakeLocationBiliBili                : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationBiliBili.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationBiliBili.yaml)',          path: ./ruleset/FakeLocationBiliBili.yaml          }
FakeLocationDouYin                  : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouYin.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouYin.yaml)',            path: ./ruleset/FakeLocationDouYin.yaml            }
FakeLocationKuaiShou                : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationKuaiShou.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationKuaiShou.yaml)',          path: ./ruleset/FakeLocationKuaiShou.yaml          }
FakeLocationXiaoHongShu             : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiaoHongShu.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiaoHongShu.yaml)',       path: ./ruleset/FakeLocationXiaoHongShu.yaml       }
FakeLocationXiGua                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiGua.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXiGua.yaml)',             path: ./ruleset/FakeLocationXiGua.yaml             }
FakeLocationWeiBo                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationWeiBo.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationWeiBo.yaml)',             path: ./ruleset/FakeLocationWeiBo.yaml             }
FakeLocationZhiHu                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationZhiHu.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationZhiHu.yaml)',             path: ./ruleset/FakeLocationZhiHu.yaml             }
FakeLocationTieBa                   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationTieBa.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationTieBa.yaml)',             path: ./ruleset/FakeLocationTieBa.yaml             }
FakeLocationDouBan                  : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouBan.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationDouBan.yaml)',            path: ./ruleset/FakeLocationDouBan.yaml            }
FakeLocationXianYu                  : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXianYu.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/FakeLocation/FakeLocationXianYu.yaml)',            path: ./ruleset/FakeLocationXianYu.yaml            }

```

---
<br>
<br>

# 🔗 参考资料
<br>

本规则集参考了以下第三方规则库：

* **anti-ip-attribution:** [GitHub Link](https://github.com/SunsetMkt/anti-ip-attribution/blob/main/rules.yaml)

* **bilibili-rule:** [GitHub Link](https://github.com/elysias123/bilibili-rule/blob/main/bilibili.yaml)

