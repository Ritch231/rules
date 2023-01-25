## 包含
openclash rule-set规则  
surge domain-set规则  

## 示例

```yaml

port: 7890
socks-port: 7891
allow-lan: true
mode: Rule
log-level: info
external-controller: :9090
dns:
  enable: true
  listen: 0.0.0.0:7874
  default-nameserver:
    - 223.5.5.5
    - 119.29.29.29
  nameserver:
    - 223.5.5.5
    - 119.29.29.29
    - 114.114.114.114
  fallback:
    - tls://8.8.8.8:853
    - https://8.8.4.4/dns-query
    - https://1.1.1.1/dns-query
    - https://9.9.9.9/dns-query
    - https://94.140.14.140/dns-query
    - https://208.67.222.222/dns-query
proxies:
  - name: ex-trojan
    server: server.example.com
    port: 443
    type: trojan
  - name: ex-v2ray
    server: server.example.com
    port: 443
    type: v2ray
proxy-groups:
  - name: 🚀代理节点
    proxies:
      - ♻️自动选择
      - 🔮故障转移
    type: select
  - name: ♻️自动选择
    proxies:
      - ex-trojan
      - ex-v2ray
    type: url-test
    url: http://www.gstatic.com/generate_204
    interval: "900"
  - name: 🔮故障转移
    proxies:
      - ex-trojan
      - ex-v2ray
    type: fallback
    url: http://www.gstatic.com/generate_204
    interval: "900"
  - name: 🐟漏网之鱼
    proxies:
      - 🚀代理节点
      - ♻️自动选择
      - 🔮故障转移
      - DIRECT
    type: select
  - name: 🚴‍♀️直连通道
    proxies:
      - DIRECT
      - 🚀代理节点
      - ♻️自动选择
      - 🔮故障转移
    type: select
  - name: 🍎苹果iCloud
    proxies:
      - DIRECT
      - 🚀代理节点
      - ♻️自动选择
      - 🔮故障转移
    type: select
  - name: 🍎苹果服务
    proxies:
      - DIRECT
      - 🚀代理节点
      - ♻️自动选择
      - 🔮故障转移
    type: select
  - name: 🍏苹果代理
    proxies:
      - 🔮故障转移
      - 🚀代理节点
      - ♻️自动选择
      - DIRECT
    type: select
  - name: 🏠ClubHouse
    proxies:
      - 🔮故障转移
      - 🚀代理节点
      - ♻️自动选择
      - DIRECT
    type: select
  - name: 📹油管视频
    proxies:
      - 🚀代理节点
      - ♻️自动选择
      - 🔮故障转移
    type: select
  - name: 📲电报消息
    proxies:
      - 🔮故障转移
      - 🚀代理节点
      - ♻️自动选择
    type: select
  - name: 🦜Twitter
    proxies:
      - 🔮故障转移
      - 🚀代理节点
      - ♻️自动选择
    type: select
  - name: 📖Facebook
    proxies:
      - 🚀代理节点
      - 🔮故障转移
      - DIRECT
    type: select
  - name: 🌍国外媒体
    proxies:
      - 🚀代理节点
      - ♻️自动选择
      - 🔮故障转移
    type: select
  - name: Ⓜ️微软服务
    proxies:
      - 🚀代理节点
      - ♻️自动选择
      - 🔮故障转移
      - DIRECT
    type: select
  - name: 🎶网易音乐
    proxies:
      - DIRECT
      - 🚀代理节点
      - ♻️自动选择
      - 🔮故障转移
    type: select
  - name: 🎬哔哩哔哩
    proxies:
      - DIRECT
      - 🚀代理节点
      - ♻️自动选择
      - 🔮故障转移
    type: select
  - name: 🛡️奇艺净化
    proxies:
      - REJECT
      - DIRECT
    type: select
rule-providers:
  domain_AppleProxy:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_AppleProxy.yaml"
    path: "./rule_provider/domain_AppleProxy.yaml"
    interval: 86400
  domain_Apple:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_Apple.yaml"
    path: "./rule_provider/domain_Apple.yaml"
    interval: 86400
  domain_AppleiCloud:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_AppleiCloud.yaml"
    path: "./rule_provider/domain_AppleiCloud.yaml"
    interval: 86400
  domain_Bilibili:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_Bilibili.yaml"
    path: "./rule_provider/domain_Bilibili.yaml"
    interval: 86400
  domain_ClubHouse:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_ClubHouse.yaml"
    path: "./rule_provider/domain_ClubHouse.yaml"
    interval: 86400
  domain_Facebook:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_Facebook.yaml"
    path: "./rule_provider/domain_Facebook.yaml"
    interval: 86400
  domain_ForeignMedia:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_ForeignMedia.yaml"
    path: "./rule_provider/domain_ForeignMedia.yaml"
    interval: 86400
  domain_Google:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_Google.yaml"
    path: "./rule_provider/domain_Google.yaml"
    interval: 86400
  domain_Microsoft:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_Microsoft.yaml"
    path: "./rule_provider/domain_Microsoft.yaml"
    interval: 86400
  domain_NetEase:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_NetEase.yaml"
    path: "./rule_provider/domain_NetEase.yaml"
    interval: 86400
  domain_Telegram:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_Telegram.yaml"
    path: "./rule_provider/domain_Telegram.yaml"
    interval: 86400
  domain_Twitter:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_Twitter.yaml"
    path: "./rule_provider/domain_Twitter.yaml"
    interval: 86400
  domain_AD:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_AD.yaml"
    path: "./rule_provider/domain_AD.yaml"
    interval: 86400
  domain_proxy:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_proxy.yaml"
    path: "./rule_provider/domain_proxy.yaml"
    interval: 86400
  domain_direct:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/domain_direct.yaml"
    path: "./rule_provider/domain_direct.yaml"
    interval: 86400
  IP_Apple:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/IP_Apple.yaml"
    path: "./rule_provider/IP_Apple.yaml"
    interval: 86400
  IP_Bilibili:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/IP_Bilibili.yaml"
    path: "./rule_provider/IP_Bilibili.yaml"
    interval: 86400
  IP_ClubHouse:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/IP_ClubHouse.yaml"
    path: "./rule_provider/IP_ClubHouse.yaml"
    interval: 86400
  IP_Facebook:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/IP_Facebook.yaml"
    path: "./rule_provider/IP_Facebook.yaml"
    interval: 86400
  IP_ForeignMedia:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/IP_ForeignMedia.yaml"
    path: "./rule_provider/IP_ForeignMedia.yaml"
    interval: 86400
  IP_Google:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/IP_Google.yaml"
    path: "./rule_provider/IP_Google.yaml"
    interval: 86400
  IP_NetEase:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/IP_NetEase.yaml"
    path: "./rule_provider/IP_NetEase.yaml"
    interval: 86400
  IP_Telegram:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/IP_Telegram.yaml"
    path: "./rule_provider/IP_Telegram.yaml"
    interval: 86400
  IP_Twitter:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/Ritch231/rules/master/clash/IP_Twitter.yaml"
    path: "./rule_provider/IP_Twitter.yaml"
    interval: 86400
rules:
  - DOMAIN-SUFFIX,openai.com,🔮故障转移
  - RULE-SET,domain_AppleProxy,🍏苹果代理
  - RULE-SET,domain_AppleiCloud,🍎苹果iCloud
  - RULE-SET,domain_Apple,🍎苹果服务
  - RULE-SET,domain_Google,📹油管视频
  - RULE-SET,domain_Telegram,📲电报消息
  - RULE-SET,domain_Twitter,🦜Twitter
  - RULE-SET,domain_ClubHouse,🏠ClubHouse
  - RULE-SET,domain_Facebook,📖Facebook
  - RULE-SET,domain_Microsoft,Ⓜ️微软服务
  - RULE-SET,domain_ForeignMedia,🌍国外媒体
  - RULE-SET,domain_proxy,🚀代理节点
  - RULE-SET,domain_AD,🛡️奇艺净化
  - RULE-SET,domain_NetEase,🎶网易音乐
  - RULE-SET,domain_Bilibili,🎬哔哩哔哩
  - RULE-SET,domain_direct,🚴‍♀️直连通道
  - RULE-SET,IP_Apple,🍎苹果服务
  - RULE-SET,IP_ClubHouse,🏠ClubHouse
  - RULE-SET,IP_Telegram,📲电报消息
  - RULE-SET,IP_Twitter,🦜Twitter
  - RULE-SET,IP_Google,📹油管视频
  - RULE-SET,IP_Facebook,📖Facebook
  - RULE-SET,IP_ForeignMedia,🌍国外媒体
  - RULE-SET,IP_Bilibili,🎬哔哩哔哩
  - RULE-SET,IP_NetEase,🎶网易音乐
  - GEOIP,CN,🚴‍♀️直连通道
  - MATCH,🐟漏网之鱼

```

## 整理各路大神资源，日常自用。