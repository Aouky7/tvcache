# tvcache · 樱花动漫站源

TVBox / 影视仓 / OK影视 可用的樱花动漫站源，`csp_Yh`。

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
- **域名自动跟随**（见下）

## 域名自动跟随

站点经常换域名，所以 jar 里不再写死域名，每次解析顺序是：

1. 抓「永久发布页」`https://www.yinhuadm.one/`，从里面提取所有 `yinhuadm.*` 域名
2. 拼接上内置种子域名（`www.yinhuadm.xyz`、`www.yinhuadm.net`）
3. 逐个请求 `api.php/provide/vod/?ac=list&pg=1`，第一个返回 `"code":1` 的域名就用它
4. 之后请求失败（比如站点又换域名），60 秒后自动重新解析并重试

想手动指定域名，就在配置的 `sites[].ext` 里写：

```json
"ext": "https://www.yinhuadm.xyz"
```

## 文件

| 文件 | 说明 |
|---|---|
| `Spiders.jar` | `csp_Yh` 爬虫（dex，壳直接加载） |
| `yh_full.json` | 明文配置 |
| `yh_full_encrypted` | 加密配置（key=yh888） |

> jar 是二进制，需要直接上传；修改源码后重新 build 再覆盖同名文件即可。

## 已知限制

- 地区 / 语言 / 首字母 / 排序：接口参数不认，所以没做
- 新增分类需要改 `TYPES` 重新编译
- ffzy / feifei 直链按 UA+Referer 放行，部分网络会 403，换线路即可
