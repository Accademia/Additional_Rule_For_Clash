# 百度网盘（BaiduNetDisk）Clash 分流规则集

## 用途

- 访问 **百度网盘（Baidu NetDisk）** 所需的 Clash 分流规则
<br>

## 引用范例

```yaml
BaiduNetDisk_No_Resolve :
  { type: http, behavior: classical, interval: 86400,
    url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BaiduNetDisk/BaiduNetDisk_No_Resolve.yaml',
    path: ./ruleset/BaiduNetDisk_No_Resolve.yaml }

BaiduNetDisk :
  { type: http, behavior: classical, interval: 86400,
    url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BaiduNetDisk/BaiduNetDisk.yaml',
    path: ./ruleset/BaiduNetDisk.yaml }

BaiduNetDisk_Domain :
  { type: http, behavior: domain, interval: 86400,
    url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/BaiduNetDisk/BaiduNetDisk_Domain.yaml',
    path: ./ruleset/BaiduNetDisk_Domain.yaml }
```

<br>

## 使用说明 ⚠️⚠️⚠️

本项目包含 **多组规则文件**，**三选一即可**，请勿同时启用。


### 规则后缀说明

| 规则组 |后缀 |  说明 |
|------|--------|------|
|第一组 |  `No_Resolve` | 不进行 DNS 解析 |
|第二组 |  （无后缀） |   |
|第三组 |  `Domain` 、`IP` | 🔥 建议 |


> **优先使用：Domain + IP**

在移动端（**Stash for iOS**）中，此组合可以：
- 显著提升匹配速度
- 明显降低内存占用

<br>

## 重要说明

⚠️ **仅长期验证并保证正确性** 的规则 (后缀) 如下，其他后缀（尤其是 `No_Resolve`）**未进行自用级验证**，本人也不会长期验证。

- `Domain`
- `IP`



原因详见：

- [为什么必须完全禁用官方推荐的 Fake IP + Fallback DNS + no-resolve 组合？](https://github.com/Accademia/Clash_Configuration_Template?tab=readme-ov-file)