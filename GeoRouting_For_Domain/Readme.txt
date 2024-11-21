   #
   # 截至2020年6月，纯拉丁字母的，两个字符的，国家代码顶级域名( Country-code of Root Zone Database ) ，共有250个
   #   https://www.iana.org/domains/root/db
   #   * 选取：country-code  （注意：有些Country-code没有生效）
   #
   # 需要排除的域名：
   #   https://zh.Wikipedia.org/zh-hans/國家和地區頂級域
   #   https://en.Wikipedia.org/wiki/Country_code_top-level_domain
   #
   # 
  
   # 注意：
   #
   #   1.  谷歌认为，下列国家或地区顶级域在
   #       使用上更加符合通用顶级域的功能，
   #       而不是国家或地区顶级域。并且在
   #       搜索引擎优化和搜索引擎索引上做了
   #       对应的处理
   #       .ad \ .as \ .ai \ .bz \ .cc \ 
   #       .cd \ .co \ .dj \ .fm \ .io \ 
   #       .la \ .me \ .ms \ .nu \ .sc \  
   #       .sr \ .su \ .tv \ .tk \ .ws \
   #
   #       .gg \ .ac \ .ag \ .ec \ .la \ 
   #       .ac \ .vc \ .to \ .ly \ .sb \
   #       .?? \ .?? \
   #
   #   2. 以下ISO代码，没有对应的，国家代码的顶级域名
   #       .bv \ .bl \ .mf \ .sj \ .gb \ .um \
   #
   #
   #   3. 已经停止解析的，国家顶级域名：
   #       .yr \ .yu \ .tp \ .an \ .ac \
   #
   #
   # 注意：只对域名（DOMAIN-SUFFIX）做例外
   #       处理，不要IP地理位置（GEOIP）做
   #       例外处理。因为IP地址表达了网站
   #       真实的物理地点，应该匹配最近国家
   #       的VPN节点服务器。
   #