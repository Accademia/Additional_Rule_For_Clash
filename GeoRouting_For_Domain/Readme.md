
# GeoRouting 基于 ccTLD 的地理位置分流规则

### 项目简述

* **用途：** 根据目的网站的国家顶级域名 (ccTLD) 的地理位置进行分流，决定流量走哪个临近国家的 VPS 节点。
* **注意：** 本规则集中，**不包含** 🇨🇳 中国 (CN)。

<br>

### ⚠️ 使用建议与核心说明

为了达到最佳分流效果，请仔细阅读以下建议：

1.  **分流原理**：基于域名后缀（如 `.jp`, `.uk`, `.hk`）将流量指向对应区域的代理策略组。
2.  **移动端推荐**：在移动端（如 Stash for iOS），建议优先选择 **Domain** 后缀规则，这能极大增加匹配速度并减少内存占用。

<br>
<br>

---

# 引用配置范例
<br>

请在您的 Clash / Stash 配置文件中参考以下格式引入。

### 📦 规则文件后缀说明 (三选一)

本项目提供三组不同后缀的规则文件，请根据您的客户端和需求，**任选其一**即可，不要重复引用。

| 后缀类型       | 说明                               | 适用场景                                           |
| :------------- | :--------------------------------- | :------------------------------------------------- |
| **No_Resolve** | 包含 `no-resolve` 策略             | 适用于不需要解析 DNS 的场景                        |
| **(无后缀)** | 标准 Classical 格式                |                                            |
| **Domain** | 纯域名列表                         | **🔥🔥🔥 推荐 (内存消耗最低)** |

<br>

⚠️ 注意，仅优先保证 ： Domain/IP 后缀的规则 ，是长期验证过的（ = 自用级验证 + 100%正确 ） 。其他后缀的规则，均未参与。尤其no_resolve 规则，我本人应该永远也不会 自用级验证，原因请看这里：

 - [ 为什么 必须禁用 ，官方推荐 的 “ Fake IP + Fallback DNS + no-resolve ” 组合 ？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file#%EF%B8%8F%EF%B8%8F-%E4%B8%BA%E4%BB%80%E4%B9%88-%E5%BF%85%E9%A1%BB%E5%AE%8C%E5%85%A8%E7%A6%81%E7%94%A8-%E5%AE%98%E6%96%B9%E6%8E%A8%E8%8D%90%E7%9A%84--fake-ip--fallback-dns--no-resolve--%E7%BB%84%E5%90%88) 
 
<br>
<br>

### 1. No-Resolve 策略引用 (推荐用于由 IP 分流兜底的场景)
<br>

```yaml
# ---------------------------------------------------
#  GeoRouting - 引用示例 (No-Resolve 版)
# ---------------------------------------------------

# 北美洲 & 南美洲
GeoRouting_America_North_ccTLD_No_Resolve : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_North_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_North_ccTLD_No_Resolve.yaml)', path: ./ruleset/GeoRouting_America_North_ccTLD_No_Resolve.yaml }
GeoRouting_America_South_ccTLD_No_Resolve : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_South_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_South_ccTLD_No_Resolve.yaml)', path: ./ruleset/GeoRouting_America_South_ccTLD_No_Resolve.yaml }

# 欧洲
GeoRouting_Europe_West_ccTLD_No_Resolve   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_West_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_West_ccTLD_No_Resolve.yaml)',   path: ./ruleset/GeoRouting_Europe_West_ccTLD_No_Resolve.yaml   }
GeoRouting_Europe_East_ccTLD_No_Resolve   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_East_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_East_ccTLD_No_Resolve.yaml)',   path: ./ruleset/GeoRouting_Europe_East_ccTLD_No_Resolve.yaml   }

# 大洋洲 & 南极洲
GeoRouting_Oceania_ccTLD_No_Resolve       : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Oceania_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Oceania_ccTLD_No_Resolve.yaml)',       path: ./ruleset/GeoRouting_Oceania_ccTLD_No_Resolve.yaml       }
GeoRouting_Antarctica_ccTLD_No_Resolve    : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Antarctica_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Antarctica_ccTLD_No_Resolve.yaml)',    path: ./ruleset/GeoRouting_Antarctica_ccTLD_No_Resolve.yaml    }

# 亚洲
GeoRouting_Asia_East_ccTLD_No_Resolve     : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_East_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_East_ccTLD_No_Resolve.yaml)',     path: ./ruleset/GeoRouting_Asia_East_ccTLD_No_Resolve.yaml     }
GeoRouting_Asia_EastSouth_ccTLD_No_Resolve: {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_EastSouth_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_EastSouth_ccTLD_No_Resolve.yaml)', path: ./ruleset/GeoRouting_Asia_EastSouth_ccTLD_No_Resolve.yaml }
GeoRouting_Asia_South_ccTLD_No_Resolve    : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_South_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_South_ccTLD_No_Resolve.yaml)',    path: ./ruleset/GeoRouting_Asia_South_ccTLD_No_Resolve.yaml    }
GeoRouting_Asia_Central_ccTLD_No_Resolve  : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_Central_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_Central_ccTLD_No_Resolve.yaml)',  path: ./ruleset/GeoRouting_Asia_Central_ccTLD_No_Resolve.yaml  }
GeoRouting_Asia_West_ccTLD_No_Resolve     : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_West_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_West_ccTLD_No_Resolve.yaml)',     path: ./ruleset/GeoRouting_Asia_West_ccTLD_No_Resolve.yaml     }

# 非洲
GeoRouting_Africa_North_ccTLD_No_Resolve  : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_North_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_North_ccTLD_No_Resolve.yaml)',  path: ./ruleset/GeoRouting_Africa_North_ccTLD_No_Resolve.yaml  }
GeoRouting_Africa_South_ccTLD_No_Resolve  : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_South_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_South_ccTLD_No_Resolve.yaml)',  path: ./ruleset/GeoRouting_Africa_South_ccTLD_No_Resolve.yaml  }
GeoRouting_Africa_West_ccTLD_No_Resolve   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_West_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_West_ccTLD_No_Resolve.yaml)',   path: ./ruleset/GeoRouting_Africa_West_ccTLD_No_Resolve.yaml   }
GeoRouting_Africa_East_ccTLD_No_Resolve   : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_East_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_East_ccTLD_No_Resolve.yaml)',   path: ./ruleset/GeoRouting_Africa_East_ccTLD_No_Resolve.yaml   }
GeoRouting_Africa_Central_ccTLD_No_Resolve: {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_Central_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_Central_ccTLD_No_Resolve.yaml)', path: ./ruleset/GeoRouting_Africa_Central_ccTLD_No_Resolve.yaml }

```
<br>
<br>

### 2. 标准策略引用 (Classical)
<br>

```yaml
# ---------------------------------------------------
#  GeoRouting - 引用示例 (标准版)
# ---------------------------------------------------

# 北美洲 & 南美洲
GeoRouting_America_North_ccTLD            : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_North_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_North_ccTLD.yaml)',            path: ./ruleset/GeoRouting_America_North_ccTLD.yaml            }
GeoRouting_America_South_ccTLD            : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_South_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_South_ccTLD.yaml)',            path: ./ruleset/GeoRouting_America_South_ccTLD.yaml            }

# 欧洲
GeoRouting_Europe_West_ccTLD              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_West_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_West_ccTLD.yaml)',              path: ./ruleset/GeoRouting_Europe_West_ccTLD.yaml              }
GeoRouting_Europe_East_ccTLD              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_East_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_East_ccTLD.yaml)',              path: ./ruleset/GeoRouting_Europe_East_ccTLD.yaml              }

# 大洋洲 & 南极洲
GeoRouting_Oceania_ccTLD                  : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Oceania_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Oceania_ccTLD.yaml)',                  path: ./ruleset/GeoRouting_Oceania_ccTLD.yaml                  }
GeoRouting_Antarctica_ccTLD               : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Antarctica_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Antarctica_ccTLD.yaml)',               path: ./ruleset/GeoRouting_Antarctica_ccTLD.yaml               }

# 亚洲
GeoRouting_Asia_East_ccTLD                : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_East_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_East_ccTLD.yaml)',                path: ./ruleset/GeoRouting_Asia_East_ccTLD.yaml                }
GeoRouting_Asia_EastSouth_ccTLD           : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_EastSouth_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_EastSouth_ccTLD.yaml)',           path: ./ruleset/GeoRouting_Asia_EastSouth_ccTLD.yaml           }
GeoRouting_Asia_South_ccTLD               : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_South_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_South_ccTLD.yaml)',               path: ./ruleset/GeoRouting_Asia_South_ccTLD.yaml               }
GeoRouting_Asia_Central_ccTLD             : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_Central_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_Central_ccTLD.yaml)',             path: ./ruleset/GeoRouting_Asia_Central_ccTLD.yaml             }
GeoRouting_Asia_West_ccTLD                : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_West_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_West_ccTLD.yaml)',                path: ./ruleset/GeoRouting_Asia_West_ccTLD.yaml                }

# 非洲
GeoRouting_Africa_North_ccTLD             : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_North_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_North_ccTLD.yaml)',             path: ./ruleset/GeoRouting_Africa_North_ccTLD.yaml             }
GeoRouting_Africa_South_ccTLD             : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_South_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_South_ccTLD.yaml)',             path: ./ruleset/GeoRouting_Africa_South_ccTLD.yaml             }
GeoRouting_Africa_West_ccTLD              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_West_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_West_ccTLD.yaml)',              path: ./ruleset/GeoRouting_Africa_West_ccTLD.yaml              }
GeoRouting_Africa_East_ccTLD              : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_East_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_East_ccTLD.yaml)',              path: ./ruleset/GeoRouting_Africa_East_ccTLD.yaml              }
GeoRouting_Africa_Central_ccTLD           : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_Central_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_Central_ccTLD.yaml)',           path: ./ruleset/GeoRouting_Africa_Central_ccTLD.yaml           }

```
<br>
<br>

### 3. 🔥🔥🔥🔥🔥  纯域名策略引用 (Domain - 推荐)
<br>

```yaml
# ---------------------------------------------------
#  GeoRouting - 引用示例 (Domain 版)
# ---------------------------------------------------

# 北美洲 & 南美洲
GeoRouting_America_North_ccTLD_Domain     : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_North_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_North_ccTLD_Domain.yaml)',     path: ./ruleset/GeoRouting_America_North_ccTLD_Domain.yaml     }
GeoRouting_America_South_ccTLD_Domain     : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_South_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_America_South_ccTLD_Domain.yaml)',     path: ./ruleset/GeoRouting_America_South_ccTLD_Domain.yaml     }

# 欧洲
GeoRouting_Europe_West_ccTLD_Domain       : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_West_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_West_ccTLD_Domain.yaml)',       path: ./ruleset/GeoRouting_Europe_West_ccTLD_Domain.yaml       }
GeoRouting_Europe_East_ccTLD_Domain       : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_East_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Europe_East_ccTLD_Domain.yaml)',       path: ./ruleset/GeoRouting_Europe_East_ccTLD_Domain.yaml       }

# 大洋洲 & 南极洲
GeoRouting_Oceania_ccTLD_Domain           : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Oceania_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Oceania_ccTLD_Domain.yaml)',           path: ./ruleset/GeoRouting_Oceania_ccTLD_Domain.yaml           }
GeoRouting_Antarctica_ccTLD_Domain        : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Antarctica_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Antarctica_ccTLD_Domain.yaml)',        path: ./ruleset/GeoRouting_Antarctica_ccTLD_Domain.yaml        }

# 亚洲
GeoRouting_Asia_East_ccTLD_Domain         : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_East_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_East_ccTLD_Domain.yaml)',         path: ./ruleset/GeoRouting_Asia_East_ccTLD_Domain.yaml         }
GeoRouting_Asia_EastSouth_ccTLD_Domain    : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_EastSouth_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_EastSouth_ccTLD_Domain.yaml)',    path: ./ruleset/GeoRouting_Asia_EastSouth_ccTLD_Domain.yaml    }
GeoRouting_Asia_South_ccTLD_Domain        : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_South_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_South_ccTLD_Domain.yaml)',        path: ./ruleset/GeoRouting_Asia_South_ccTLD_Domain.yaml        }
GeoRouting_Asia_Central_ccTLD_Domain      : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_Central_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_Central_ccTLD_Domain.yaml)',      path: ./ruleset/GeoRouting_Asia_Central_ccTLD_Domain.yaml      }
GeoRouting_Asia_West_ccTLD_Domain         : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_West_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_West_ccTLD_Domain.yaml)',         path: ./ruleset/GeoRouting_Asia_West_ccTLD_Domain.yaml         }

# 非洲
GeoRouting_Africa_North_ccTLD_Domain      : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_North_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_North_ccTLD_Domain.yaml)',      path: ./ruleset/GeoRouting_Africa_North_ccTLD_Domain.yaml      }
GeoRouting_Africa_South_ccTLD_Domain      : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_South_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_South_ccTLD_Domain.yaml)',      path: ./ruleset/GeoRouting_Africa_South_ccTLD_Domain.yaml      }
GeoRouting_Africa_West_ccTLD_Domain       : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_West_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_West_ccTLD_Domain.yaml)',       path: ./ruleset/GeoRouting_Africa_West_ccTLD_Domain.yaml       }
GeoRouting_Africa_East_ccTLD_Domain       : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_East_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_East_ccTLD_Domain.yaml)',       path: ./ruleset/GeoRouting_Africa_East_ccTLD_Domain.yaml       }
GeoRouting_Africa_Central_ccTLD_Domain    : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_Central_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Africa_Central_ccTLD_Domain.yaml)',    path: ./ruleset/GeoRouting_Africa_Central_ccTLD_Domain.yaml    }

```
<br>

> **🇨🇳 特别注意**：上述洲际规则中，**不包含中国**。中国需要使用单独规则：

```yaml
# 中国 (CN)
GeoRouting_Asia_China_ccTLD_No_Resolve    : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_China_ccTLD_No_Resolve.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_China_ccTLD_No_Resolve.yaml)', path: ./ruleset/GeoRouting_Asia_China_ccTLD_No_Resolve.yaml }
GeoRouting_Asia_China_ccTLD               : {type: http, behavior: classical, interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_China_ccTLD.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_China_ccTLD.yaml)',            path: ./ruleset/GeoRouting_Asia_China_ccTLD.yaml            }
GeoRouting_Asia_China_ccTLD_Domain        : {type: http, behavior: domain,    interval: 86400, url: '[https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_China_ccTLD_Domain.yaml](https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GeoRouting_For_Domain/GeoRouting_Asia_China_ccTLD_Domain.yaml)',     path: ./ruleset/GeoRouting_Asia_China_ccTLD_Domain.yaml     }

```
<br>
<br>

---

# ⚠️ 规则排除说明
<br>

本规则集参考了 [IANA Root Zone Database](https://www.iana.org/domains/root/db) 截止 2020年6月的标准。部分顶级域名因特殊原因未被收录。

## 1. 被 Google 视为通用顶级域 (gTLD) 的排除项

Google 将下列国家或地区顶级域视为符合通用顶级域的功能，并在搜索引擎优化中做了特殊处理，因此它们**未被包含**在地理分流规则中：

* `.ad`, `.as`, `.ai`, `.bz`, `.cc`
* `.cd`, `.co`, `.dj`, `.fm`, `.io`
* `.la`, `.me`, `.ms`, `.nu`, `.sc`
* `.sr`, `.su`, `.tv`, `.tk`, `.ws`
* `.gg`, `.ac`, `.ag`, `.ec`, `.vc`
* `.to`, `.ly`, `.sb`

<br>

## 2. 无对应国家代码的排除项

以下 ISO 代码没有对应的国家代码顶级域名：

* `.bv`, `.bl`, `.mf`, `.sj`, `.gb`, `.um`

<br>

## 3. 已停止解析的顶级域名

* `.yr`, `.yu`, `.tp`, `.an`, `.ac`

> **参考资料：**
> * [Wikipedia: 國家和地區頂級域](https://zh.Wikipedia.org/zh-hans/國家和地區頂級域)
> * [Wikipedia: Country code top-level domain](https://en.Wikipedia.org/wiki/Country_code_top-level_domain)
> 
> 
