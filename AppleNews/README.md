# AppleNews / xAI Clash 分流规则集

## 用途

- 访问 **Apple News** 与 **xAI** 所需的 Clash 分流规则

<br>

## 特别注意

- **必须同时满足**：
  - 启用本规则
  - 关闭移动网络（或拔出中国 SIM 卡）
- 否则在中国大陆 **无法正常访问 Apple News**
- iOS 后台会进行区域检查并自动限制（与是否国行设备无关）

> ⚠️ 以下 Apple 相关规则之间 **存在交叉**，请确保更靠前解析的规则不会干扰本规则：
>
> - Siri / Spotlight / Lookup / Safari / News / 信息 / 音乐

<br>

## 引用范例

```yaml
AppleNews_No_Resolve :
  { type: http, behavior: classical, interval: 86400,
    url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleNews/AppleNews_No_Resolve.yaml',
    path: ./ruleset/AppleNews_No_Resolve.yaml }

AppleNews :
  { type: http, behavior: classical, interval: 86400,
    url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleNews/AppleNews.yaml',
    path: ./ruleset/AppleNews.yaml }

AppleNews_Domain :
  { type: http, behavior: domain, interval: 86400,
    url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleNews/AppleNews_Domain.yaml',
    path: ./ruleset/AppleNews_Domain.yaml }

AppleNews_IP :
  { type: http, behavior: ipcidr, interval: 86400,
    url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/AppleNews/AppleNews_IP.yaml',
    path: ./ruleset/AppleNews_IP.yaml }
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
