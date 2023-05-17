# 简介

本项目生成适用于 [subconverter 外部配置 `ruleset` 字段的规则文件](https://github.com/tindy2013/subconverter/blob/master/README-cn.md#%E5%A4%96%E9%83%A8%E9%85%8D%E7%BD%AE) 。使用 GitHub Actions 北京时间 6:30 自动构建，保证规则最新。

## 说明

本项目规则集（RULE-SET）的数据主要来源于项目:
- [@Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)
- [@Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) 
- [@v2fly/domain-list-community](https://github.com/v2fly/domain-list-community)
- [@felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)
- [@17mon/china_ip_list](https://github.com/17mon/china_ip_list)

## 规则文件列表

- 直连域名列表 direct.txt
- 代理域名列表 proxy.txt
- 广告域名列表 reject.txt
- 私有网络专用域名列表 private.txt
- ![Apple 在中国大陆可直连的域名列表 apple.txt](https://raw.githubusercontent.com/gitduk/clash-rules/release/apple.txt)
- iCloud 域名列表 icloud.txt
- Google 在中国大陆可直连的域名列表 google.txt
- GFWList 域名列表 gfw.txt
- 非中国大陆使用的顶级域名列表 tld-not-cn.txt
- Telegram 使用的 IP 地址列表 telegramcidr.txt
- 局域网 IP 及保留 IP 地址列表 lancidr.txt
- 中国大陆 IP 地址列表 cncidr.txt
- 需要直连的常见软件列表 applications.txt

## 使用方式

## 致谢

- [@Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)
- [@Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip)
- [@Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat)
- [@gfwlist/gfwlist](https://github.com/gfwlist/gfwlist)
- [@v2fly/domain-list-community](https://github.com/v2fly/domain-list-community)
- [@felixonmars/dnsmasq-china-list](https://github.com/felixonmars/dnsmasq-china-list)
- [@17mon/china_ip_list](https://github.com/17mon/china_ip_list)
