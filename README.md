# 简介

本项目生成适用于 [subconverter 外部配置 `ruleset` 字段的规则文件](https://github.com/tindy2013/subconverter/blob/master/README-cn.md#%E5%A4%96%E9%83%A8%E9%85%8D%E7%BD%AE) 。使用 GitHub Actions 北京时间 6:30 自动构建，保证规则最新。

## 说明

本项目规则集（RULE-SET）的数据主要来源于项目:
- [@Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)
- [@Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) 
- [@v2fly/domain-list-community](https://github.com/v2fly/domain-list-community)
- [@felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)
- [@17mon/china_ip_list](https://github.com/17mon/china_ip_list)

本项目 GitHub Actions 主要参考 [@Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules) 的 Action 文件

## 规则文件列表

| 建议 | 文件 | 国内访问链接 |
| :---: | --- | --- |
| 直连 | [直连域名列表 direct.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/direct.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/direct.txt |
| 直连 | [局域网 IP 及保留 IP 地址列表 lancidr.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/lancidr.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/lancidr.txt |
| 直连 | [中国大陆 IP 地址列表 cncidr.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/cncidr.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/cncidr.txt |
| 直连 | [需要直连的常见软件列表 applications.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/applications.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/applications.txt |
| 直连 | [私有网络专用域名列表 private.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/private.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/private.txt |
| 直连 | [Apple 在中国大陆可直连的域名列表 apple.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/apple.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/apple.txt |
| 直连 | [Google 在中国大陆可直连的域名列表 google.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/google.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/google.txt |
| 直连 | [iCloud 域名列表 icloud.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/icloud.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/icloud.txt |
| 代理 | [代理域名列表 proxy.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/proxy.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/proxy.txt |
| 代理 | [GFWList 域名列表 gfw.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/gfw.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/gfw.txt |
| 代理 | [非中国大陆使用的顶级域名列表 tld-not-cn.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/tld-not-cn.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/tld-not-cn.txt |
| 代理 | [Telegram 使用的 IP 地址列表 telegramcidr.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/telegramcidr.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/telegramcidr.txt |
| REJECT | [广告域名列表 reject.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/reject.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/reject.txt |

无法访问 `raw.githubusercontent.com` 域名的情况下可在文件链接前面加上 `https://ghproxy.com/`

以例 [direct.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/direct.txt) 为例：`https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/direct.txt`

## 规则重复

规则集合是从各个开源项目中搜集而来，会导致生成的 clash 配置文件有重复的规则。我用 Github Action 生成了去重规则列表：

| 建议 | 文件 | 国内访问链接 |
| 代理 | [去重代理域名列表 proxy.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/proxy-uniq.txt) | https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/proxy-uniq.txt |

## 使用方式

前提是在本地搭建好 subconverter 服务，搭建教程见 [subconverter-docker](https://github.com/tindy2013/subconverter/blob/master/README-docker.md)

``` bash
curl -sSL "http://127.0.0.1:25500/sub?target=clash&new_name=true&url=<urlencode 后的订阅链接>&config=<urlencode 后的外部配置文件链接>" > config.yaml
```

以 [external.ini](https://raw.githubusercontent.com/gitduk/clash-rules/main/external.ini) 文件为例：
```
curl -sSL "http://127.0.0.1:25500/sub?target=clash&url=<urlencode 后的订阅链接>&config=https%3A%2F%2Fghproxy.com%2Fhttps%3A%2F%2Fraw.githubusercontent.com%2Fgitduk%2Fclash-rules%2Fmain%2Fexternal.ini" > config.yaml
```

具体请查看 [subconverter 外部配置](https://github.com/tindy2013/subconverter/blob/master/README-cn.md#%E5%A4%96%E9%83%A8%E9%85%8D%E7%BD%AE) 相关内容。

## 致谢

- [@Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)
- [@Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip)
- [@Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat)
- [@gfwlist/gfwlist](https://github.com/gfwlist/gfwlist)
- [@v2fly/domain-list-community](https://github.com/v2fly/domain-list-community)
- [@felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)
- [@17mon/china_ip_list](https://github.com/17mon/china_ip_list)
