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

## 使用方式

前提是在本地搭建好 subconverter 服务，搭建教程见 [subconverter-docker](https://github.com/tindy2013/subconverter/blob/master/README-docker.md)

``` bash
curl -sSL "http://127.0.0.1:25500/sub?target=clash&new_name=true&url=<urlencode 后的订阅链接>&config=<urlencode 后的外部配置文件链接>" > config.yaml
```

以 [external.ini](https://raw.githubusercontent.com/gitduk/clash-rules/main/external.ini) 文件为例：
```
curl -sSL "http://127.0.0.1:25500/sub?target=clash&url=<urlencode 后的订阅链接>&config=https%3A%2F%2Fghproxy.com%2Fhttps%3A%2F%2Fraw.githubusercontent.com%2Fgitduk%2Fclash-rules%2Fmain%2Fexternal.ini" > config.yaml
```

外部配置文件示例：
```
[custom]

; 代理组
custom_proxy_group=🚀 节点选择`select`[]🔰 手动切换`[]♻️ 自动选择`[]🇭🇰 香港`[]🇹🇼 台湾`[]🇸🇬 狮城`[]🇯🇵 日本`[]🇺🇲 美国`[]🇰🇷 韩国`🇮🇳 印度`🇦🇷 阿根廷`🇹🇷 土耳其`[]DIRECT
custom_proxy_group=🔰 手动切换`select`.*
custom_proxy_group=♻️ 自动选择`url-test`.*`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🎯 全球直连`select`[]DIRECT`[]🚀 节点选择`[]🔰 手动切换`[]♻️ 自动选择
custom_proxy_group=⛔️ 广告拦截`select`[]REJECT`[]DIRECT
custom_proxy_group=🐟 漏网之鱼`select`[]🚀 节点选择`[]🔰 手动切换`[]♻️ 自动选择`[]DIRECT`[]🇭🇰 香港`[]🇹🇼 台湾`[]🇸🇬 狮城`[]🇯🇵 日本`[]🇺🇲 美国`[]🇰🇷 韩国`🇮🇳 印度`🇦🇷 阿根廷`🇹🇷 土耳其

; 代理组-基于服务
custom_proxy_group=💬 OpenAi`select`[]🚀 节点选择`[]🔰 手动切换`[]🇺🇲 美国`[]🇰🇷 韩国`🇮🇳 印度`🇦🇷 阿根廷`🇹🇷 土耳其
custom_proxy_group=Ⓜ 微软服务`select`[]🚀 节点选择`[]🔰 手动切换`[]♻️ 自动选择`[]🇺🇲 美国`[]🇭🇰 香港`[]🇹🇼 台湾`[]🇸🇬 狮城`[]🇯🇵 日本`[]🇰🇷 韩国`🇮🇳 印度`🇦🇷 阿根廷`🇹🇷 土耳其`[]DIRECT
custom_proxy_group=🌍 国外媒体`select`[]🚀 节点选择`[]🔰 手动切换`[]♻️ 自动选择`[]🇭🇰 香港`[]🇹🇼 台湾`[]🇸🇬 狮城`[]🇯🇵 日本`[]🇺🇲 美国`[]🇰🇷 韩国`🇮🇳 印度`🇦🇷 阿根廷`🇹🇷 土耳其`[]DIRECT
custom_proxy_group=🌏 国内媒体`select`[]DIRECT`[]🔰 手动切换`[]🇭🇰 香港`[]🇹🇼 台湾`[]🇸🇬 狮城`[]🇯🇵 日本


; 代理组-基于地域
custom_proxy_group=🇭🇰 香港`url-test`(港|HK|Hong Kong)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇹🇼 台湾`url-test`(台|新北|彰化|TW|Taiwan)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇸🇬 狮城`url-test`(新加坡|坡|狮城|SG|Singapore)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇯🇵 日本`url-test`(日本|川日|东京|大阪|泉日|埼玉|沪日|深日|[^-]日|JP|Japan)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇺🇲 美国`url-test`(美|波特兰|达拉斯|俄勒冈|凤凰城|费利蒙|硅谷|拉斯维加斯|洛杉矶|圣何塞|圣克拉拉|西雅图|芝加哥|US|United States)`http://www.gstatic.com/generate_204`300,,150
custom_proxy_group=🇰🇷 韩国`url-test`(韩国|韩|首尔|韓|KR|Korea|KOR)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇮🇳 印度`url-test`(印度|孟买|India)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇦🇷 阿根廷`url-test`(阿根廷)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇹🇷 土耳其`url-test`(土耳其|伊斯坦布尔|TR|Turkey)`http://www.gstatic.com/generate_204`300,,50

; 规则集-直连
ruleset=🎯 全球直连,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/direct.txt
ruleset=🎯 全球直连,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/lancidr.txt
ruleset=🎯 全球直连,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/cncidr.txt
ruleset=🎯 全球直连,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/applications.txt
ruleset=🎯 全球直连,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/private.txt
ruleset=🎯 全球直连,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/apple.txt
ruleset=🎯 全球直连,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/google.txt
ruleset=🎯 全球直连,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/icloud.txt
ruleset=🎯 全球直连,[]GEOIP,CN

; 规则集-广告
ruleset=⛔️ 广告拦截,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/reject.txt

; 规则集-代理
ruleset=🚀 节点选择,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/proxy.txt
ruleset=🚀 节点选择,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/gfw.txt
ruleset=🚀 节点选择,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/tld-not-cn.txt
ruleset=🚀 节点选择,https://ghproxy.com/https://raw.githubusercontent.com/gitduk/clash-rules/release/telegramcidr.txt

; 未匹配
ruleset=🐟 漏网之鱼,[]FINAL

enable_rule_generator=true
overwrite_original_rules=true
exclude_remarks=(IEPL)
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
