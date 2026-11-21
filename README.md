# tvcache · 樱花动漫站源

TVBox / 影视仓 / OK影视 可用的樱花动漫（yinhuadm.xyz）站源，`csp_Yh`。

## 壳里填这个

```
https://raw.githubusercontent.com/Aouky7/tvcache/main/yh_full.json
```

加密版（key 在文件头 `$#yh888#$` 里明文，只防随手抄）：

```
https://raw.githubusercontent.com/Aouky7/tvcache/main/yh_full_encrypted
```

## 功能

- 分类：国产 / 日本 / 欧美 / 港台 / 动漫
- 榜单：最近热门 / 最近更新 / 本周热门（刮 `/label/*.html`）
- 年份筛选 2018–2027（接口实测只有 `year` 参数生效）
- 搜索（`ac=detail&wd=`）
- 播放直链自动带 UA + Referer

## 文件

| 文件 | 说明 |
|---|---|
| `Spiders.jar` | `csp_Yh` 爬虫（dex，壳直接加载） |
| `Spiders.jar.b64` | jar 的 base64，Actions 用来还原二进制 |
| `yh_full.json` | 明文配置 |
| `yh_full_encrypted` | 加密配置（key=yh888） |

## 已知限制

- 地区 / 语言 / 首字母 / 排序：接口参数不认，所以没做
- ffzy / feifei 直链按 UA+Referer 放行，部分网络会 403，换线路即可
