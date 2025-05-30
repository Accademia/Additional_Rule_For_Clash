
# -----------------------------------------
# 此规则集：用于，基于“可信DNS”，进行分流
# -----------------------------------------

# 以下DNS被排除在本列表之外：
# 	- 中国大陆DNS（DNS污染：GFW是万恶之源）
#	- 记录隐私DNS（隐私泄漏：用户行为分析）
#	- 私有DNS（隐私泄漏：用户地理位置）


# 引用范例：
#
#    GlobalDNS_No_Resolve                : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GlobalDNS/GlobalDNS_No_Resolve.yaml'                   , path: ./ruleset/GlobalDNS_No_Resolve.yaml   }
#
#    GlobalDNS                           : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GlobalDNS/GlobalDNS.yaml'                              , path: ./ruleset/GlobalDNS.yaml              }
#
#
#    GlobalDNS_Domain                   : {type: http, behavior: domain    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GlobalDNS/GlobalDNS_Domain.yaml'                       , path: ./ruleset/GlobalDNS_Domain.yaml       }
#    GlobalDNS_IP                       : {type: http, behavior: ipcidr    , interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/GlobalDNS/GlobalDNS_IP.yaml'                           , path: ./ruleset/GlobalDNS_IP.yaml           }
#


#
# ----------------------------------
# 使用说明 ：⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️⚠️
# ----------------------------------
# 
# 本项目，包括 以下三组规则，“三选一”，选其中一个即可:
# 
# 三组的后缀，分别为：
# 
#   + 后缀：No_Resolve	（第一组）
# 
#   + 后缀：无		（第二组）
# 
#   + 后缀：Doamin		（第三组）
#   + 后缀：IP
# 
# 以上三组，三选一，优先选择最后一组（Domain + IP），在移动端（Stash for iOS），这种写法极大增加匹配速度和减少内存占用。
#
#



# 特别注意：所有来自中国的DNS均会污染解析！！！！

#-----------------------------------------------------------------------------------
# 加密的 DNS 服务列表 （每日更新）  国外DNS，不统计中国DNS
#-----------------------------------------------------------------------------------
#
# DNS列表 下载链接：
#    https://feeds.alphasoc.net/encrypted_dns.txt
#
# ASCII表格 转换工具：
#    https://tableconvert.com/zh-cn/csv-to-ascii
#
#-----------------------------------------------------------------------------------
#
# 该列表生成于 2023-09-28 10:10:05 UTC
#
# +--------------------+---------+----------+--------------+--------------------------------+
# |  IP                |   Port  | Protocol |   DNS Type   |   Manufacturer                 |
# +--------------------+---------+----------+--------------+--------------------------------+
# |  1.0.0.1           |   443   |   tcp    |   DoH        |   Cloudflare                   |
# |  1.0.0.1           |   853   |   tcp    |   DoT        |   Cloudflare                   |
# |  1.0.0.2           |   443   |   tcp    |   DoH        |   Cloudflare                   |
# |  1.0.0.3           |   443   |   tcp    |   DoH        |   Cloudflare                   |
# |  1.1.1.1           |   443   |   tcp    |   DoH        |   Cloudflare                   |
# |  1.1.1.1           |   853   |   tcp    |   DoT        |   Cloudflare                   |
# |  5.1.66.255        |   443   |   tcp    |   DoH        |   doh.ffmuc.net                |
# |  5.1.66.255        |   853   |   tcp    |   DoT        |   dot.ffmuc.net                |
# |  5.133.8.187       |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  5.133.8.187       |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  5.254.96.195      |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  5.254.96.195      |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  8.8.4.4           |   443   |   tcp    |   DoH        |   Google                       |
# |  8.8.4.4           |   853   |   tcp    |   DoT        |   Google                       |
# |  8.8.8.8           |   443   |   tcp    |   DoH        |   Google                       |
# |  8.8.8.8           |   853   |   tcp    |   DoT        |   Google                       |
# |  9.9.9.9           |   8443  |   tcp    |   DNSCrypt   |   Quad9                        |
# |  9.9.9.9           |   8443  |   udp    |   DNSCrypt   |   Quad9                        |
# |  9.9.9.9           |   443   |   tcp    |   DoH        |   Quad9                        |
# |  9.9.9.9           |   5053  |   tcp    |   DoH        |   Quad9                        |
# |  9.9.9.9           |   853   |   tcp    |   DoT        |   Quad9                        |
# |  9.9.9.10          |   8443  |   tcp    |   DNSCrypt   |   Quad9                        |
# |  9.9.9.10          |   8443  |   udp    |   DNSCrypt   |   Quad9                        |
# |  9.9.9.10          |   443   |   tcp    |   DoH        |   Quad9                        |
# |  9.9.9.10          |   5053  |   tcp    |   DoH        |   Quad9                        |
# |  9.9.9.10          |   853   |   tcp    |   DoT        |   Quad9                        |
# |  9.9.9.11          |   8443  |   tcp    |   DNSCrypt   |   Quad9                        |
# |  9.9.9.11          |   8443  |   udp    |   DNSCrypt   |   Quad9                        |
# |  9.9.9.11          |   443   |   tcp    |   DoH        |   Quad9                        |
# |  9.9.9.11          |   5053  |   tcp    |   DoH        |   Quad9                        |
# |  9.9.9.11          |   853   |   tcp    |   DoT        |   Quad9                        |
# |  9.9.9.12          |   8443  |   tcp    |   DNSCrypt   |   Quad9                        |
# |  9.9.9.12          |   8443  |   udp    |   DNSCrypt   |   Quad9                        |
# |  9.9.9.12          |   5053  |   tcp    |   DoH        |   Quad9                        |
# |  9.9.9.12          |   443   |   tcp    |   DoH        |   Quad9                        |
# |  9.9.9.12          |   853   |   tcp    |   DoT        |   Quad9                        |
# |  13.49.175.86      |   443   |   tcp    |   DoH        |   dns.brahma.world             |
# |  13.49.175.86      |   853   |   tcp    |   DoT        |   dns.brahma.world             |
# |  13.89.120.251     |   443   |   tcp    |   DoH        |   AT&T                         |
# |  13.89.120.251     |   853   |   tcp    |   DoT        |   AT&T                         |
# |  13.89.121.94      |   443   |   tcp    |   DoH        |   AT&T                         |
# |  13.89.121.94      |   853   |   tcp    |   DoT        |   AT&T                         |
# |  13.89.121.95      |   443   |   tcp    |   DoH        |   AT&T                         |
# |  13.89.121.95      |   853   |   tcp    |   DoT        |   AT&T                         |
# |  20.42.80.15       |   443   |   tcp    |   DoH        |   AT&T                         |
# |  20.42.80.15       |   853   |   tcp    |   DoT        |   AT&T                         |
# |  20.42.80.49       |   443   |   tcp    |   DoH        |   AT&T                         |
# |  20.42.80.49       |   853   |   tcp    |   DoT        |   AT&T                         |
# |  23.19.67.116      |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  23.19.67.116      |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  27.255.77.56      |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  27.255.77.56      |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  35.230.160.38     |   443   |   tcp    |   DoH        |   blockerDNS                   |
# |  35.230.160.38     |   853   |   tcp    |   DoT        |   blockerDNS                   |
# |  35.231.247.227    |   443   |   tcp    |   DoH        |   blockerDNS                   |
# |  35.231.247.227    |   853   |   tcp    |   DoT        |   blockerDNS                   |
# |  35.237.220.84     |   443   |   tcp    |   DoH        |   blockerDNS                   |
# |  35.237.220.84     |   853   |   tcp    |   DoT        |   blockerDNS                   |
# |  35.245.234.132    |   443   |   tcp    |   DoH        |   blockerDNS                   |
# |  35.245.234.132    |   853   |   tcp    |   DoT        |   blockerDNS                   |
# |  37.120.147.2      |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  37.120.147.2      |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  40.76.112.230     |   443   |   tcp    |   DoH        |   AT&T                         |
# |  40.76.112.230     |   853   |   tcp    |   DoT        |   AT&T                         |
# |  45.32.55.94       |   8443  |   tcp    |   DNSCrypt   |   BlahDNS                      |
# |  45.32.55.94       |   8443  |   udp    |   DNSCrypt   |   BlahDNS                      |
# |  45.32.55.94       |   443   |   tcp    |   DoH        |   BlahDNS                      |
# |  45.32.55.94       |   853   |   tcp    |   DoT        |   BlahDNS                      |
# |  45.63.30.163      |   443   |   tcp    |   DoH        |   pi-dns.com                   |
# |  45.63.30.163      |   853   |   tcp    |   DoT        |   pi-dns.com                   |
# |  45.67.219.208     |   443   |   tcp    |   DoH        |   pi-dns.com                   |
# |  45.67.219.208     |   853   |   tcp    |   DoT        |   pi-dns.com                   |
# |  45.76.113.31      |   443   |   tcp    |   DNSCrypt   |   dns.seby.io                  |
# |  45.76.113.31      |   443   |   udp    |   DNSCrypt   |   dns.seby.io                  |
# |  45.76.113.31      |   8443  |   tcp    |   DoH        |   dns.seby.io                  |
# |  45.76.113.31      |   853   |   tcp    |   DoT        |   dns.seby.io                  |
# |  45.90.28.0        |   443   |   tcp    |   DoH        |   NextDNS                      |
# |  45.90.28.0        |   853   |   tcp    |   DoT        |   NextDNS                      |
# |  45.90.30.0        |   443   |   tcp    |   DoH        |   NextDNS                      |
# |  45.90.30.0        |   853   |   tcp    |   DoT        |   NextDNS                      |
# |  46.101.66.244     |   443   |   tcp    |   DoH        |   doh.li                       |
# |  46.101.66.244     |   853   |   tcp    |   DoT        |   doh.li                       |
# |  46.226.108.173    |   443   |   tcp    |   DoH        |   Hostux                       |
# |  46.226.108.173    |   853   |   tcp    |   DoT        |   Hostux                       |
# |  46.226.109.82     |   443   |   tcp    |   DoH        |   Hostux                       |
# |  46.226.109.82     |   853   |   tcp    |   DoT        |   Hostux                       |
# |  46.227.200.54     |   8443  |   tcp    |   DNSCrypt   |   faelix.net                   |
# |  46.227.200.54     |   8443  |   udp    |   DNSCrypt   |   faelix.net                   |
# |  46.227.200.54     |   443   |   tcp    |   DoH        |   faelix.net                   |
# |  46.227.200.54     |   853   |   tcp    |   DoT        |   faelix.net                   |
# |  46.227.200.55     |   8443  |   tcp    |   DNSCrypt   |   faelix.net                   |
# |  46.227.200.55     |   8443  |   udp    |   DNSCrypt   |   faelix.net                   |
# |  46.227.200.55     |   443   |   tcp    |   DoH        |   faelix.net                   |
# |  46.227.200.55     |   853   |   tcp    |   DoT        |   faelix.net                   |
# |  46.239.223.80     |   443   |   tcp    |   DoH        |   dns.flatuslifir.is           |
# |  46.239.223.80     |   853   |   tcp    |   DoT        |   dns.flatuslifir.is           |
# |  47.96.179.163     |   443   |   tcp    |   DoH        |   rubyfish.cn                  |
# |  47.96.179.163     |   853   |   tcp    |   DoT        |   rubyfish.cn                  |
# |  51.15.70.167      |   853   |   tcp    |   DoT        |   dns.larsdebruin.net          |
# |  51.15.98.97       |   5353  |   tcp    |   DNSCrypt   |   resolver.dnspoint.cloud      |
# |  51.15.98.97       |   5353  |   udp    |   DNSCrypt   |   resolver.dnspoint.cloud      |
# |  51.15.98.97       |   443   |   tcp    |   DoH        |   resolver.dnspoint.cloud      |
# |  51.38.82.198      |   5353  |   tcp    |   DNSCrypt   |   dns.pumplex.com              |
# |  51.38.82.198      |   5353  |   udp    |   DNSCrypt   |   dns.pumplex.com              |
# |  51.38.82.198      |   443   |   tcp    |   DoH        |   dns.pumplex.com              |
# |  51.38.82.198      |   853   |   tcp    |   DoT        |   dns.pumplex.com              |
# |  51.38.83.141      |   5353  |   tcp    |   DNSCrypt   |   dns.oszx.co                  |
# |  51.38.83.141      |   5353  |   udp    |   DNSCrypt   |   dns.oszx.co                  |
# |  51.38.83.141      |   443   |   tcp    |   DoH        |   dns.oszx.co                  |
# |  51.38.83.141      |   853   |   tcp    |   DoT        |   dns.oszx.co                  |
# |  51.79.68.177      |   443   |   tcp    |   DoH        |   dns.okashi.me                |
# |  51.79.68.177      |   853   |   tcp    |   DoT        |   dns.okashi.me                |
# |  51.158.147.50     |   443   |   tcp    |   DoH        |   lelux.fi                     |
# |  51.158.147.50     |   853   |   tcp    |   DoT        |   lelux.fi                     |
# |  62.75.198.178     |   443   |   tcp    |   DoH        |   B-DNS                        |
# |  62.210.177.189    |   1053  |   tcp    |   DNSCrypt   |   iriseden.eu                  |
# |  62.210.177.189    |   1053  |   udp    |   DNSCrypt   |   iriseden.eu                  |
# |  62.210.177.189    |   443   |   tcp    |   DoH        |   iriseden.eu                  |
# |  62.210.177.189    |   853   |   tcp    |   DoT        |   iriseden.eu                  |
# |  62.210.180.71     |   1053  |   tcp    |   DNSCrypt   |   iriseden.eu                  |
# |  62.210.180.71     |   1053  |   udp    |   DNSCrypt   |   iriseden.eu                  |
# |  62.210.180.71     |   443   |   tcp    |   DoH        |   iriseden.eu                  |
# |  62.210.180.71     |   853   |   tcp    |   DoT        |   iriseden.eu                  |
# |  64.42.181.227     |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  64.42.181.227     |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  64.120.5.251      |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  64.120.5.251      |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  66.42.33.135      |   443   |   tcp    |   DoH        |   pi-dns.com                   |
# |  66.42.33.135      |   853   |   tcp    |   DoT        |   pi-dns.com                   |
# |  66.244.159.100    |   853   |   tcp    |   DoT        |   Tenta                        |
# |  66.244.159.200    |   853   |   tcp    |   DoT        |   Tenta                        |
# |  74.82.42.42       |   443   |   tcp    |   DoH        |   Hurricane Electric           |
# |  74.82.42.42       |   853   |   tcp    |   DoT        |   Hurricane Electric           |
# |  75.75.77.99       |   443   |   tcp    |   DoH        |   Xfinity                      |
# |  78.46.244.143     |   8443  |   tcp    |   DNSCrypt   |   BlahDNS                      |
# |  78.46.244.143     |   8443  |   udp    |   DNSCrypt   |   BlahDNS                      |
# |  78.46.244.143     |   443   |   tcp    |   DoH        |   BlahDNS                      |
# |  78.46.244.143     |   853   |   tcp    |   DoT        |   BlahDNS                      |
# |  78.47.243.3       |   1053  |   tcp    |   DNSCrypt   |   fische.io                    |
# |  78.47.243.3       |   1053  |   udp    |   DNSCrypt   |   fische.io                    |
# |  78.47.243.3       |   853   |   tcp    |   DoT        |   fische.io                    |
# |  78.47.243.3       |   853   |   udp    |   DoT        |   fische.io                    |
# |  80.67.188.188     |   443   |   tcp    |   DoH        |   Lorraine Data Network        |
# |  80.67.188.188     |   853   |   tcp    |   DoT        |   Lorraine Data Network        |
# |  80.156.145.201    |   443   |   tcp    |   DoH        |   dns.t53.de                   |
# |  80.156.145.201    |   853   |   tcp    |   DoT        |   dns.t53.de                   |
# |  81.17.31.34       |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  81.17.31.34       |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  82.163.72.123     |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  82.163.72.123     |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  84.16.240.43      |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  84.16.240.43      |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  88.80.20.20       |   443   |   tcp    |   DoH        |   B-DNS                        |
# |  88.80.21.20       |   443   |   tcp    |   DoH        |   B-DNS                        |
# |  88.198.91.187     |   443   |   tcp    |   DoH        |   pi-dns.com                   |
# |  88.198.91.187     |   853   |   tcp    |   DoT        |   pi-dns.com                   |
# |  89.163.214.174    |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  89.163.214.174    |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  89.233.43.71      |   853   |   tcp    |   DoT        |   UncensoredDNS                |
# |  89.234.186.112    |   443   |   tcp    |   DoH        |   Neutopia                     |
# |  89.234.186.112    |   853   |   tcp    |   DoT        |   Neutopia                     |
# |  94.130.106.88     |   443   |   tcp    |   DoH        |   appliedprivacy.net           |
# |  94.130.106.88     |   853   |   tcp    |   DoT        |   appliedprivacy.net           |
# |  94.130.110.178    |   853   |   tcp    |   DoT        |   dnsprivacy.at                |
# |  94.130.110.185    |   853   |   tcp    |   DoT        |   dnsprivacy.at                |
# |  94.140.14.14      |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.14.14      |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.14.14      |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  94.140.14.14      |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  94.140.14.15      |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.14.15      |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.14.15      |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  94.140.14.15      |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  94.140.14.140     |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.14.140     |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.14.140     |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  94.140.14.140     |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  94.140.14.141     |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.14.141     |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.14.141     |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  94.140.14.141     |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  94.140.15.15      |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.15.15      |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.15.15      |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  94.140.15.15      |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  94.140.15.16      |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.15.16      |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  94.140.15.16      |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  94.140.15.16      |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  94.247.43.254     |   5353  |   tcp    |   DNSCrypt   |   eth-services.de              |
# |  94.247.43.254     |   5353  |   udp    |   DNSCrypt   |   eth-services.de              |
# |  94.247.43.254     |   853   |   tcp    |   DoH        |   eth-services.de              |
# |  95.216.24.230     |   853   |   tcp    |   DoT        |   snopyta.org                  |
# |  95.216.181.228    |   443   |   tcp    |   DoH        |   pi-dns.com                   |
# |  95.216.181.228    |   853   |   tcp    |   DoT        |   pi-dns.com                   |
# |  95.216.212.177    |   8443  |   tcp    |   DNSCrypt   |   BlahDNS                      |
# |  95.216.212.177    |   8443  |   udp    |   DNSCrypt   |   BlahDNS                      |
# |  95.216.212.177    |   8443  |   tcp    |   DNSCrypt   |   BlahDNS                      |
# |  95.216.212.177    |   8443  |   udp    |   DNSCrypt   |   BlahDNS                      |
# |  95.216.212.177    |   443   |   tcp    |   DoH        |   BlahDNS                      |
# |  95.216.212.177    |   853   |   tcp    |   DoT        |   BlahDNS                      |
# |  95.216.229.153    |   443   |   tcp    |   DoH        |   snopyta.org                  |
# |  95.217.16.205     |   443   |   tcp    |   DoH        |   dns.tin-fan.com              |
# |  96.113.151.141    |   443   |   tcp    |   DoH        |   Xfinity                      |
# |  96.113.151.142    |   443   |   tcp    |   DoH        |   Xfinity                      |
# |  96.113.151.143    |   443   |   tcp    |   DoH        |   Xfinity                      |
# |  96.113.151.145    |   853   |   tcp    |   DoT        |   Xfinity                      |
# |  96.113.151.147    |   443   |   tcp    |   DoH        |   Xfinity                      |
# |  96.113.151.148    |   443   |   tcp    |   DoH        |   Xfinity                      |
# |  96.113.151.149    |   443   |   tcp    |   DoH        |   Xfinity                      |
# |  96.113.151.150    |   443   |   tcp    |   DoH        |   Xfinity                      |
# |  99.192.182.100    |   853   |   tcp    |   DoT        |   Tenta                        |
# |  99.192.182.200    |   853   |   tcp    |   DoT        |   Tenta                        |
# |  101.101.101.101   |   853   |   tcp    |   DoT        |   Quad 101                     |
# |  101.102.103.104   |   853   |   tcp    |   DoT        |   Quad 101                     |
# |  103.2.57.5        |   443   |   tcp    |   DoH        |   public.dns.iij.jp            |
# |  103.2.57.6        |   443   |   tcp    |   DoH        |   public.dns.iij.jp            |
# |  104.16.248.249    |   443   |   tcp    |   DoH        |   Cloudflare                   |
# |  104.16.248.249    |   853   |   tcp    |   DoT        |   Cloudflare                   |
# |  104.16.249.249    |   443   |   tcp    |   DoH        |   Cloudflare                   |
# |  104.16.249.249    |   853   |   tcp    |   DoT        |   Cloudflare                   |
# |  104.236.178.232   |   443   |   tcp    |   DoH        |   dnsoverhttps.net             |
# |  104.238.181.28    |   443   |   tcp    |   DoH        |   NextDNS                      |
# |  104.238.181.28    |   853   |   tcp    |   DoT        |   NextDNS                      |
# |  104.238.186.192   |   443   |   tcp    |   DNSCrypt   |   dnscrypt.uk                  |
# |  104.238.186.192   |   443   |   udp    |   DNSCrypt   |   dnscrypt.uk                  |
# |  104.244.78.231    |   443   |   tcp    |   DoH        |   NixNet                       |
# |  104.244.78.231    |   853   |   tcp    |   DoT        |   NixNet                       |
# |  104.255.175.2     |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  104.255.175.2     |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  107.191.43.90     |   443   |   tcp    |   DoH        |   dns.tin-fan.com              |
# |  108.61.201.119    |   443   |   tcp    |   DoH        |   BlahDNS                      |
# |  108.61.201.119    |   853   |   tcp    |   DoT        |   BlahDNS                      |
# |  109.70.100.100    |   853   |   tcp    |   DoT        |   appliedprivacy.net           |
# |  109.70.100.100    |   853   |   tcp    |   DoT        |   Applied Privacy              |
# |  109.71.42.228     |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  109.71.42.228     |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  109.248.149.133   |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  109.248.149.133   |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  115.159.131.230   |   443   |   tcp    |   DoH        |   rubyfish.cn                  |
# |  115.159.131.230   |   853   |   tcp    |   DoT        |   rubyfish.cn                  |
# |  116.202.176.26    |   443   |   tcp    |   DoH        |   libredns.gr                  |
# |  116.202.176.26    |   853   |   tcp    |   DoT        |   libredns.gr                  |
# |  116.203.179.248   |   443   |   tcp    |   DoH        |   rumpelsepp.org               |
# |  118.89.110.78     |   443   |   tcp    |   DoH        |   rubyfish.cn                  |
# |  118.89.110.78     |   853   |   tcp    |   DoT        |   rubyfish.cn                  |
# |  128.127.104.108   |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  128.127.104.108   |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  130.59.31.248     |   443   |   tcp    |   DoH        |   dns.switch.ch                |
# |  130.59.31.248     |   853   |   tcp    |   DoT        |   dns.switch.ch                |
# |  130.59.31.251     |   443   |   tcp    |   DoH        |   dns.switch.ch                |
# |  130.59.31.251     |   853   |   tcp    |   DoT        |   dns.switch.ch                |
# |  136.144.215.158   |   443   |   tcp    |   DoH        |   PowerDNS                     |
# |  136.144.215.158   |   853   |   tcp    |   DoT        |   PowerDNS                     |
# |  139.59.48.222     |   4434  |   tcp    |   DNSCrypt   |   captnemo.in                  |
# |  139.59.48.222     |   4434  |   udp    |   DNSCrypt   |   captnemo.in                  |
# |  139.59.48.222     |   443   |   tcp    |   DoH        |   captnemo.in                  |
# |  139.59.51.46      |   853   |   tcp    |   DoT        |   dns.bitgeek.in               |
# |  139.99.222.72     |   8443  |   tcp    |   DNSCrypt   |   dns.seby.io                  |
# |  139.99.222.72     |   8443  |   udp    |   DNSCrypt   |   dns.seby.io                  |
# |  139.99.222.72     |   443   |   tcp    |   DoH        |   dns.seby.io                  |
# |  139.99.222.72     |   853   |   tcp    |   DoT        |   dns.seby.io                  |
# |  139.162.3.123     |   853   |   tcp    |   DoH        |   sg.gridns.xyz                |
# |  139.162.3.123     |   443   |   tcp    |   DoH        |   sg.gridns.xyz                |
# |  139.162.112.47    |   8443  |   tcp    |   DNSCrypt   |   BlahDNS                      |
# |  139.162.112.47    |   443   |   tcp    |   DoH        |   BlahDNS                      |
# |  139.162.112.47    |   853   |   tcp    |   DoT        |   BlahDNS                      |
# |  139.180.141.57    |   8443  |   tcp    |   DNSCrypt   |   BlahDNS                      |
# |  139.180.141.57    |   8443  |   udp    |   DNSCrypt   |   BlahDNS                      |
# |  139.180.141.57    |   443   |   tcp    |   DoH        |   BlahDNS                      |
# |  142.4.204.111     |   443   |   tcp    |   DNSCrypt   |   luggs.co                     |
# |  142.4.204.111     |   443   |   udp    |   DNSCrypt   |   luggs.co                     |
# |  142.4.205.47      |   443   |   tcp    |   DNSCrypt   |   luggs.co                     |
# |  142.4.205.47      |   443   |   udp    |   DNSCrypt   |   luggs.co                     |
# |  143.110.229.87    |   443   |   tcp    |   DoH        |   NextDNS                      |
# |  143.110.229.87    |   853   |   tcp    |   DoT        |   NextDNS                      |
# |  145.100.185.15    |   443   |   tcp    |   DoH        |   Surfnet                      |
# |  145.100.185.15    |   853   |   tcp    |   DoT        |   Surfnet                      |
# |  145.100.185.16    |   443   |   tcp    |   DoH        |   Surfnet                      |
# |  145.100.185.16    |   853   |   tcp    |   DoT        |   Surfnet                      |
# |  145.100.185.17    |   853   |   tcp    |   DoT        |   Surfnet                      |
# |  145.100.185.18    |   853   |   tcp    |   DoT        |   Surfnet                      |
# |  145.239.92.241    |   443   |   tcp    |   DoH        |   dns.tin-fan.com              |
# |  146.112.41.2      |   443   |   tcp    |   DoH        |   OpenDNS                      |
# |  146.185.167.43    |   443   |   tcp    |   DoH        |   SecureDNS                    |
# |  146.185.167.43    |   853   |   tcp    |   DoT        |   SecureDNS                    |
# |  146.185.176.36    |   5353  |   tcp    |   DNSCrypt   |   phillymesh.net               |
# |  146.185.176.36    |   5353  |   udp    |   DNSCrypt   |   phillymesh.net               |
# |  146.255.56.98     |   443   |   tcp    |   DoH        |   Applied Privacy              |
# |  146.255.56.98     |   853   |   tcp    |   DoT        |   Applied Privacy              |
# |  149.56.228.45     |   443   |   tcp    |   DNSCrypt   |   dnscrypt.ca                  |
# |  149.56.228.45     |   443   |   udp    |   DNSCrypt   |   dnscrypt.ca                  |
# |  149.56.228.45     |   453   |   tcp    |   DoH        |   dnscrypt.ca                  |
# |  149.112.112.9     |   8443  |   tcp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.9     |   8443  |   udp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.9     |   443   |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.9     |   5053  |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.9     |   853   |   tcp    |   DoT        |   Quad9                        |
# |  149.112.112.10    |   8443  |   tcp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.10    |   8443  |   udp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.10    |   5053  |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.10    |   443   |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.10    |   853   |   tcp    |   DoT        |   Quad9                        |
# |  149.112.112.11    |   8443  |   tcp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.11    |   8443  |   udp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.11    |   5053  |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.11    |   443   |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.11    |   853   |   tcp    |   DoT        |   Quad9                        |
# |  149.112.112.12    |   8443  |   tcp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.12    |   8443  |   udp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.12    |   443   |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.12    |   5053  |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.12    |   853   |   tcp    |   DoT        |   Quad9                        |
# |  149.112.112.112   |   8443  |   tcp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.112   |   8443  |   udp    |   DNSCrypt   |   Quad9                        |
# |  149.112.112.112   |   5053  |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.112   |   443   |   tcp    |   DoH        |   Quad9                        |
# |  149.112.112.112   |   853   |   tcp    |   DoT        |   Quad9                        |
# |  149.154.153.153   |   443   |   tcp    |   DoH        |   usableprivacy.net            |
# |  149.154.153.153   |   853   |   tcp    |   DoT        |   usableprivacy.net            |
# |  151.80.222.79     |   5353  |   tcp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   5353  |   udp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   1053  |   tcp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   1053  |   udp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   1194  |   tcp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   1194  |   udp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   8080  |   tcp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   8080  |   udp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   54    |   tcp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   54    |   udp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   27015 |   tcp    |   DNSCrypt   |   i2pd.xyz                     |
# |  151.80.222.79     |   27015 |   udp    |   DNSCrypt   |   i2pd.xyz                     |
# |  155.138.240.237   |   443   |   tcp    |   DoH        |   dns.tin-fan.com              |
# |  155.254.29.113    |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  155.254.29.113    |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  158.64.1.29       |   853   |   tcp    |   DoT        |   Foundation RESTENA           |
# |  159.69.198.101    |   8443  |   tcp    |   DNSCrypt   |   BlahDNS                      |
# |  159.69.198.101    |   8443  |   udp    |   DNSCrypt   |   BlahDNS                      |
# |  159.69.198.101    |   443   |   tcp    |   DoH        |   BlahDNS                      |
# |  159.69.198.101    |   853   |   tcp    |   DoT        |   BlahDNS                      |
# |  162.221.207.228   |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  162.221.207.228   |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  163.172.180.125   |   443   |   tcp    |   DNSCrypt   |   sfw.scaleway-fr              |
# |  163.172.180.125   |   443   |   udp    |   DNSCrypt   |   sfw.scaleway-fr              |
# |  167.114.84.132    |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  167.114.84.132    |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  167.114.220.125   |   443   |   tcp    |   DNSCrypt   |   dnscrypt.ca                  |
# |  167.114.220.125   |   443   |   udp    |   DNSCrypt   |   dnscrypt.ca                  |
# |  167.114.220.125   |   453   |   tcp    |   DoH        |   dnscrypt.ca                  |
# |  168.138.243.216   |   443   |   tcp    |   DoH        |   ibuki.cgnat.net              |
# |  168.138.243.216   |   853   |   tcp    |   DoT        |   ibuki.cgnat.net              |
# |  168.235.81.167    |   443   |   tcp    |   DoH        |   aaflalo.me                   |
# |  168.235.81.167    |   853   |   tcp    |   DoT        |   aaflalo.me                   |
# |  172.104.93.80     |   443   |   tcp    |   DoH        |   jp.tiar.app                  |
# |  172.105.241.93    |   443   |   tcp    |   DoH        |   jp.gridns.xyz                |
# |  172.105.241.93    |   853   |   tcp    |   DoH        |   jp.gridns.xyz                |
# |  173.234.56.115    |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  173.234.56.115    |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  173.234.159.235   |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  173.234.159.235   |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  174.68.248.77     |   443   |   tcp    |   DoH        |   Cox                          |
# |  174.68.248.77     |   853   |   tcp    |   DoT        |   Cox                          |
# |  174.138.29.175    |   443   |   tcp    |   DoH        |   doh.tiar.app                 |
# |  176.9.1.117       |   443   |   tcp    |   DoH        |   dnsforge.de                  |
# |  176.9.1.117       |   853   |   tcp    |   DoT        |   dnsforge.de                  |
# |  176.9.93.198      |   443   |   tcp    |   DoH        |   dnsforge.de                  |
# |  176.9.93.198      |   853   |   tcp    |   DoT        |   dnsforge.de                  |
# |  176.9.199.158     |   443   |   tcp    |   DoH        |   decloudus.com                |
# |  176.9.199.158     |   853   |   tcp    |   DoT        |   decloudus.com                |
# |  176.56.236.175    |   443   |   tcp    |   DoH        |   aaflalo.me                   |
# |  176.56.236.175    |   853   |   tcp    |   DoT        |   aaflalo.me                   |
# |  176.103.130.130   |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  176.103.130.130   |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  176.103.130.130   |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  176.103.130.130   |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  176.103.130.131   |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  176.103.130.131   |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  176.103.130.131   |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  176.103.130.131   |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  176.103.130.132   |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  176.103.130.132   |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  176.103.130.132   |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  176.103.130.132   |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  176.103.130.134   |   5443  |   tcp    |   DNSCrypt   |   AdGuard DNS                  |
# |  176.103.130.134   |   5443  |   udp    |   DNSCrypt   |   AdGuard DNS                  |
# |  176.103.130.134   |   443   |   tcp    |   DoH        |   AdGuard DNS                  |
# |  176.103.130.134   |   853   |   tcp    |   DoT        |   AdGuard DNS                  |
# |  178.175.139.211   |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  178.175.139.211   |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  184.105.193.78    |   853   |   tcp    |   DoT        |   OARC                         |
# |  185.26.126.14     |   443   |   tcp    |   DoH        |   Hostux                       |
# |  185.26.126.37     |   443   |   tcp    |   DoH        |   Hostux                       |
# |  185.43.135.1      |   443   |   tcp    |   DoH        |   odvr.nic.cz                  |
# |  185.43.135.1      |   853   |   tcp    |   DoT        |   odvr.nic.cz                  |
# |  185.49.141.37     |   853   |   tcp    |   DoT        |   getdnsapi.net                |
# |  185.94.193.234    |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  185.94.193.234    |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  185.95.218.42     |   443   |   tcp    |   DoH        |   dns.digitale-gesellschaft.ch |
# |  185.95.218.42     |   853   |   tcp    |   DoT        |   dns.digitale-gesellschaft.ch |
# |  185.95.218.43     |   443   |   tcp    |   DoH        |   dns.digitale-gesellschaft.ch |
# |  185.95.218.43     |   853   |   tcp    |   DoT        |   dns.digitale-gesellschaft.ch |
# |  185.107.80.84     |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  185.107.80.84     |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  185.117.118.20    |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  185.117.118.20    |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  185.134.196.54    |   443   |   tcp    |   DoH        |   faelix.net                   |
# |  185.134.196.54    |   853   |   tcp    |   DoT        |   faelix.net                   |
# |  185.134.196.55    |   443   |   tcp    |   DoH        |   faelix.net                   |
# |  185.134.196.55    |   853   |   tcp    |   DoT        |   faelix.net                   |
# |  185.134.197.54    |   443   |   tcp    |   DoH        |   faelix.net                   |
# |  185.150.99.255    |   443   |   tcp    |   DoH        |   doh.ffmuc.net                |
# |  185.150.99.255    |   853   |   tcp    |   DoT        |   dot.ffmuc.net                |
# |  185.184.222.222   |   853   |   tcp    |   DoT        |   dns.sb                       |
# |  185.212.169.139   |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  185.212.169.139   |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  185.213.26.187    |   443   |   tcp    |   DoH        |   pi-dns.com                   |
# |  185.213.26.187    |   853   |   tcp    |   DoT        |   pi-dns.com                   |
# |  185.216.27.142    |   443   |   tcp    |   DoH        |   doh.42l.fr                   |
# |  185.222.222.222   |   853   |   tcp    |   DoT        |   dns.sb                       |
# |  185.228.168.9     |   443   |   tcp    |   DoH        |   CleanBrowsing                |
# |  185.228.168.9     |   853   |   tcp    |   DoT        |   CleanBrowsing                |
# |  185.228.168.10    |   443   |   tcp    |   DoH        |   CleanBrowsing                |
# |  185.228.168.10    |   853   |   tcp    |   DoT        |   CleanBrowsing                |
# |  185.228.168.168   |   443   |   tcp    |   DoH        |   CleanBrowsing                |
# |  185.228.168.168   |   853   |   tcp    |   DoT        |   CleanBrowsing                |
# |  185.228.168.199   |   443   |   tcp    |   DoH        |   CleanBrowsing                |
# |  185.228.168.199   |   853   |   tcp    |   DoT        |   CleanBrowsing                |
# |  185.228.169.9     |   443   |   tcp    |   DoH        |   CleanBrowsing                |
# |  185.228.169.9     |   853   |   tcp    |   DoT        |   CleanBrowsing                |
# |  185.228.169.11    |   443   |   tcp    |   DoH        |   CleanBrowsing                |
# |  185.228.169.11    |   853   |   tcp    |   DoT        |   CleanBrowsing                |
# |  185.228.169.168   |   443   |   tcp    |   DoH        |   CleanBrowsing                |
# |  185.228.169.168   |   853   |   tcp    |   DoT        |   CleanBrowsing                |
# |  185.235.81.1      |   443   |   tcp    |   DoH        |   dnslify.com                  |
# |  185.235.81.1      |   853   |   tcp    |   DoT        |   dnslify.com                  |
# |  185.235.81.2      |   443   |   tcp    |   DoH        |   dnslify.com                  |
# |  185.235.81.2      |   853   |   tcp    |   DoT        |   dnslify.com                  |
# |  190.115.26.106    |   443   |   tcp    |   DoH        |   B-DNS                        |
# |  193.17.47.1       |   443   |   tcp    |   DoH        |   odvr.nic.cz                  |
# |  193.17.47.1       |   853   |   tcp    |   DoT        |   odvr.nic.cz                  |
# |  194.54.82.12      |   443   |   tcp    |   DoH        |   B-DNS                        |
# |  194.54.82.13      |   443   |   tcp    |   DoH        |   B-DNS                        |
# |  195.10.195.195    |   5353  |   tcp    |   DNSCrypt   |   eth-services.de              |
# |  195.10.195.195    |   5353  |   udp    |   DNSCrypt   |   eth-services.de              |
# |  195.10.195.195    |   853   |   tcp    |   DoH        |   eth-services.de              |
# |  195.154.40.48     |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  195.154.40.48     |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  198.7.58.227      |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  198.7.58.227      |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  198.100.148.36    |   443   |   tcp    |   DoH        |   boothlabs.me                 |
# |  198.100.148.224   |   443   |   tcp    |   DNSCrypt   |   boothlabs.me                 |
# |  198.100.148.224   |   443   |   udp    |   DNSCrypt   |   boothlabs.me                 |
# |  198.251.90.89     |   443   |   tcp    |   DoH        |   NixNet                       |
# |  198.251.90.89     |   853   |   tcp    |   DoT        |   NixNet                       |
# |  198.251.90.91     |   443   |   tcp    |   DoH        |   NixNet                       |
# |  198.251.90.91     |   853   |   tcp    |   DoT        |   NixNet                       |
# |  199.58.81.218     |   443   |   tcp    |   DoH        |   dns.cmrg.net                 |
# |  199.58.81.218     |   53053 |   tcp    |   DoT        |   dns.cmrg.net                 |
# |  199.58.81.218     |   853   |   tcp    |   DoT        |   dns.cmrg.net                 |
# |  199.195.251.84    |   443   |   tcp    |   DoH        |   NixNet                       |
# |  199.195.251.84    |   853   |   tcp    |   DoT        |   NixNet                       |
# |  200.1.123.46      |   853   |   tcp    |   DoT        |   NIC Chile                    |
# |  208.67.220.220    |   443   |   tcp    |   DNSCrypt   |   OpenDNS                      |
# |  208.67.220.220    |   443   |   udp    |   DNSCrypt   |   OpenDNS                      |
# |  208.67.222.222    |   443   |   tcp    |   DNSCrypt   |   OpenDNS                      |
# |  208.67.222.222    |   443   |   udp    |   DNSCrypt   |   OpenDNS                      |
# |  209.58.147.36     |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  209.58.147.36     |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  209.141.34.95     |   443   |   tcp    |   DoH        |   NixNet                       |
# |  209.141.34.95     |   853   |   tcp    |   DoT        |   NixNet                       |
# |  210.17.9.228      |   443   |   tcp    |   DoH        |   Quad 101                     |
# |  212.129.46.32     |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  212.129.46.32     |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  213.163.64.208    |   443   |   tcp    |   DNSCrypt   |   cryptostorm                  |
# |  213.163.64.208    |   443   |   udp    |   DNSCrypt   |   cryptostorm                  |
# |  213.196.191.96    |   8443  |   tcp    |   DNSCrypt   |   ibksturm.Synology.me         |
# |  213.196.191.96    |   8443  |   udp    |   DNSCrypt   |   ibksturm.Synology.me         |
# |  213.196.191.96    |   443   |   tcp    |   DoH        |   ibksturm.Synology.me         |
# |  213.196.191.96    |   853   |   tcp    |   DoT        |   ibksturm.Synology.me         |
# |  216.128.181.13    |   443   |   tcp    |   DoH        |   dns.sb                       |
# |  217.61.0.97       |   853   |   tcp    |   DoT        |   BlahDNS                      |
# |  217.169.20.22     |   443   |   tcp    |   DoH        |   dns.aa.net.uk                |
# |  217.169.20.22     |   853   |   tcp    |   DoT        |   dns.aa.net.uk                |
# |  217.169.20.23     |   443   |   tcp    |   DoH        |   dns.aa.net.uk                |
# |  217.169.20.23     |   853   |   tcp    |   DoT        |   dns.aa.net.uk                |
# +--------------------+---------+----------+--------------+--------------------------------+
#
#
