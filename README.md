# tvcache

一份配置同时挂四个站：樱花动漫（自写 `csp_Yh`）+ Jable / MissAV / Netflav（上游 `csp_GM`）。

```
https://raw.githubusercontent.com/Aouky7/tvcache/main/yh_full.json
```

## 文件

| 文件 | 说明 |
|---|---|
| `SpidersAll.jar` | 合并 dex：`csp_Yh` + `csp_GM`（GM 来自 CatVodSpider-GM），579 KB |
| `Spiders.jar` | 只有樱花（旧） |
| `yh_full.json` | 四站合并配置 |
| `av_full.json` | 只有三个 AV 站 |

## 说明

- `spider` 走 `gh-proxy.com` 加速，国内直连 raw 常超时
- Jable / MissAV 有 Cloudflare 盾，`csp_GM` 靠 WebView 过，首次加载慢
- MissAV 换域名时改 `ext.spider` 里的 4 处 `loadUrl`
