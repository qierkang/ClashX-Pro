# 自用整合 ClashX Pro 分流

### ClashX Pro 下载地址

[ClashX Pro Download](https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public)

### 懒人配置参考！

[config.yaml](https://raw.githubusercontent.com/Semporia/ClashX-Pro/master/config.yaml)

### 远程引用分流规则

```yaml

# 代理组策略
proxy-groups:

# 策略组说明

# 「Proxy」是代理规则策略，它可以指定为某个节点或嵌套一个其他策略组，如：「url-test」（自动测试）、「Fallback」或「load-balance」（负载均衡）的策略组

  - { name: "MATCH", type: select, proxies: ["Proxy"]} 
  - { name: "Apple", type: select, proxies: ["DIRECT"], use: ["United States","Japan"]}
  - { name: "Adobe", type: url-test, use: ["United States"]}
  - { name: "Amazon", type: url-test, use: ["United States"]}
  - { name: "China", type: select, proxies: ["DIRECT"]}
  - { name: "Dler", type: select, use: ["Hong Kong","United States","Dler Cloud"]}
  - { name: "Facebook", type: url-test, use: ["Hong Kong"]}
  - { name: "GitHub", type: url-test, use: ["Hong Kong"]}
  - { name: "Google", type: url-test, use: ["United States"]}
  - { name: "Microsoft", type: select, proxies: ["DIRECT"], use: ["United States"]}
  - { name: "Netflix", type: url-test, use: ["United States"]}
  - { name: "Speedtest", type: select, proxies: ["DIRECT"]} 
  - { name: "Steam", type: url-test, use: ["United States"]}
  - { name: "Spotify", type: url-test, use: ["United States"]}
  - { name: "Telegram", type: url-test, use: ["Hong Kong"]}
  - { name: "Twitter", type: url-test, use: ["Hong Kong"]}
  - { name: "Tencent", type: select, proxies: ["DIRECT"]} 
  - { name: "YouTube", type: url-test, use: ["United States"]}
  - { name: "paypal", type: url-test, use: ["United States"]}
  - { name: "Proxy", type: url-test, use: ["Hong Kong","United States"]} 

# 分流规则  
rules:
- RULE-SET,AdBlock,REJECT
- RULE-SET,Proxy,Proxy
- RULE-SET,Apple,Apple
- RULE-SET,Adobe,Adobe
- RULE-SET,Amazon,Amazon
- RULE-SET,Dler,Dler
- RULE-SET,Facebook,Facebook 
- RULE-SET,GitHub,GitHub
- RULE-SET,Google,Google
- RULE-SET,Microsoft,Microsoft
- RULE-SET,Netflix,Netflix 
- RULE-SET,Speedtest,Speedtest
- RULE-SET,Steam,Steam
- RULE-SET,Spotify,Spotify
- RULE-SET,Telegram,Telegram 
- RULE-SET,Twitter,Twitter 
- RULE-SET,Tencent,Tencent
- RULE-SET,YouTube,YouTube 
- RULE-SET,PayPal,paypal 
- RULE-SET,China,China
- DOMAIN-SUFFIX,live.cn,China

- GEOIP,CN,DIRECT
- MATCH,MATCH

rule-providers:

  AdBlock: {type: http, behavior: classical, path: ./Filter/AdBlock, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/AdBlock.yaml, interval: 3600}
  Apple: {type: http, behavior: classical, path: ./Filter/Apple, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Apple.yaml, interval: 3600}
  Adobe: {type: http, behavior: classical, path: ./Filter/Adobe, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Adobe.yaml, interval: 3600}
  Amazon: {type: http, behavior: classical, path: ./Filter/Amazon, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Amazon.yaml, interval: 3600}

  China: {type: http, behavior: classical, path: ./Filter/China, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/China.yaml, interval: 3600}

  Dler: {type: http, behavior: classical, path: ./Filter/Dler, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Dler.yaml, interval: 3600}

  Facebook: {type: http, behavior: classical, path: ./Filter/Facebook, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Facebook.yaml, interval: 3600}

  GitHub: {type: http, behavior: classical, path: ./Filter/GitHub, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/GitHub.yaml, interval: 3600}
  Google: {type: http, behavior: classical, path: ./Filter/Google, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Google.yaml, interval: 3600}
  
  Microsoft: {type: http, behavior: classical, path: ./Filter/Microsoft, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Microsoft.yaml, interval: 3600}
  
  Netflix: {type: http, behavior: classical, path: ./Filter/Netflix, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Netflix.yaml, interval: 3600}
  
  Spotify: {type: http, behavior: classical, path: ./Filter/Spotify, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Spotify.yaml, interval: 3600}
  Speedtest: {type: http, behavior: classical, path: ./Filter/Speedtest, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Speedtest.yaml, interval: 3600}
  Steam: {type: http, behavior: classical, path: ./Filter/Steam, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Steam.yaml, interval: 3600}

  Telegram: {type: http, behavior: classical, path: ./Filter/Telegram, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Telegram.yaml, interval: 3600}
  Twitter: {type: http, behavior: classical, path: ./Filter/Twitter, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Twitter.yaml, interval: 3600}
  Tencent: {type: http, behavior: classical, path: ./Filter/Tencent, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Tencent.yaml, interval: 3600}

  YouTube: {type: http, behavior: classical, path: ./Filter/YouTube, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/YouTube.yaml, interval: 3600}

  PayPal: {type: http, behavior: classical, path: ./Filter/PayPal, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/PayPal.yaml, interval: 3600}
  Proxy: {type: http, behavior: classical, path: ./Filter/Proxy, url: https://cdn.jsdelivr.net/gh/Semporia/Clash-X@master/Filter/Proxy.yaml, interval: 3600}

```