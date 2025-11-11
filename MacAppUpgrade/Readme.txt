
# -----------------------------------------
# 此规则集：Homebrew App Install \ Upgrade  Clash 分流规则
# -----------------------------------------

# ---------
# 用途：
# ---------
#	mac苹果电脑 升级常用软件的分流规则 
#	
# 注意：
#	1. 不包含Apple App Store内任何软件和Mac OS系统自带的软件，仅仅包含常用的第三方Mac软件
#	2. 本分流规则：由脚本全自动生成，代理 homebrew 、 sparkle 的升级安装
#	3. 未来会手动添加更多规则，主要面向非homebrew的升级需求
#
#
# ---------
# 脚本：
# ---------
#
# 本规则内，homebrew 、 sparkle 对应的升级规则，可通过以下脚本自动生成  ：
# 	./usercmd_MacAppUpgrade_to_clashruleset	
#
#
#
# -----------
# 引用范例 ：
# -----------
#
#    MacAppUpgrade_No_Resolve                   : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MacAppUpgrade/MacAppUpgrade_No_Resolve.yaml'                                      , path: ./ruleset/MacAppUpgrade_No_Resolve.yaml                    }       
#           
#    MacAppUpgrade                              : {type: http, behavior: classical, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MacAppUpgrade/MacAppUpgrade.yaml'                                                 , path: ./ruleset/MacAppUpgrade.yaml    	                       }    
#           
#    MacAppUpgrade_Domain                       : {type: http, behavior: domain, interval: 86400, url: 'https://cdn.jsdelivr.net/gh/Accademia/Additional_Rule_For_Clash@master/MacAppUpgrade/MacAppUpgrade_Domain.yaml'                                             , path: ./ruleset/MacAppUpgrade_Domain.yaml    		               }    
#
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
#
# -------------------------------------------
# 本规则中，被分流的 homebrew 安装命令，包括：
# -------------------------------------------
#
# brew install ack                                  # 开发工具     ｜  代码搜索工具，类似 grep 但更适合开发者
# brew install aom                                  # 多媒体库     ｜  AV1 视频编码器库，支持高效视频压缩
# brew install apr                                  # 开发库       ｜  Apache 便携运行时库，提供跨平台功能
# brew install apr-util                             # 开发库       ｜  Apache 便携运行时实用工具库
# brew install aria2                                # 下载工具     ｜  多协议高速下载工具，支持 HTTP/BitTorrent
# brew install aribb24                              # 多媒体库     ｜  解析 ARIB STD-B24 字幕的库
# brew install autoenv                              # 开发工具     ｜  自动加载环境变量的 shell 工具
# brew install autojump                             # 命令行工具   ｜  快速跳转到常用目录的 shell 工具
# brew install axel                                 # 下载工具     ｜  多线程下载加速工具，类似 wget
# brew install azure-cli                            # 云服务工具   ｜  Azure 命令行接口，管理 Azure 云服务
# brew install bash                                 # 命令行壳     ｜  GNU Bash，强大的 Unix shell
# brew install bash-completion                      # 命令行工具   ｜  为 Bash 提供命令补全功能
# brew install bat                                  # 命令行工具   ｜  带语法高亮的 cat 替代工具
# brew install bdw-gc                               # 开发库       ｜  Boehm-Demers-Weiser 垃圾回收库
# brew install blake3                               # 加密库       ｜  高性能的 BLAKE3 哈希算法库
# brew install brotli                               # 压缩库       ｜  Brotli 压缩算法库，优化网络传输
# brew install ca-certificates                      # 安全工具     ｜  提供常用 CA 证书集合
# brew install cairo                                # 图形库       ｜  2D 图形渲染库，支持多种输出格式
# brew install capstone                             # 开发库       ｜  轻量级多架构反汇编框架
# brew install ccache                               # 开发工具     ｜  编译缓存工具，加速代码编译
# brew install certifi                              # Python 库    ｜  Python 的 SSL/TLS 证书验证库
# brew install cffi                                 # Python 库    ｜  Python 与 C 代码交互的外部函数接口
# brew install cheat                                # 命令行工具   ｜  交互式命令行备忘录工具
# brew install cjson                                # 开发库       ｜  轻量级 JSON 解析库
# brew install cloc                                 # 开发工具     ｜  统计代码行数的工具
# brew install cmake                                # 开发工具     ｜  跨平台构建系统，管理编译过程
# brew install cmus                                 # 音频播放     ｜  轻量级终端音乐播放器
# brew install coreutils                            # 命令行工具   ｜  GNU 核心工具集，增强 Unix 命令
# brew install cowsay                               # 娱乐工具     ｜  终端生成 ASCII 艺术文本
# brew install cryptography                         # Python 库    ｜  Python 加密和安全相关库
# brew install dash                                 # 命令行壳     ｜  轻量级 POSIX 兼容 shell
# brew install dav1d                                # 多媒体库     ｜  AV1 视频解码器库，优化性能
# brew install dtc                                  # 开发工具     ｜  设备树编译器，处理设备树文件
# brew install faad2                                # 多媒体库     ｜  AAC 音频解码库
# brew install fd                                   # 命令行工具   ｜  快速、用户友好的文件查找工具
# brew install ffmpeg                               # 多媒体工具   ｜  音视频处理工具，支持编码、解码等
# brew install fish                                 # 命令行壳     ｜  用户友好的交互式 shell
# brew install flac                                 # 音频库       ｜  无损音频压缩编解码库
# brew install fmt                                  # 开发库       ｜  现代 C++ 格式化库
# brew install fontconfig                           # 字体库       ｜  字体配置和管理库
# brew install frei0r                               # 多媒体库     ｜  视频效果插件库
# brew install freetype                             # 字体库       ｜  字体渲染库，支持 TrueType 等
# brew install fribidi                              # 文本处理     ｜  双向文本处理库，支持复杂脚本
# brew install gettext                              # 开发库       ｜  国际化与本地化支持库
# brew install ghostscript                          # 文档处理     ｜  PostScript 和 PDF 处理工具
# brew install giflib                               # 图形库       ｜  GIF 图像处理库
# brew install git                                  # 版本控制     ｜  分布式版本控制系统
# brew install glances                              # 系统监控     ｜  跨平台系统监控工具
# brew install glib                                 # 开发库       ｜  通用 C 库，提供数据结构等
# brew install glow                                 # 命令行工具   ｜  终端 Markdown 渲染工具
# brew install gmp                                  # 数学库       ｜  大整数运算库
# brew install gnutls                               # 安全库       ｜  TLS/SSL 协议实现库
# brew install graphite2                            # 字体库       ｜  智能字体渲染引擎
# brew install grep                                 # 命令行工具   ｜  GNU grep，文本搜索工具
# brew install gum                                  # 命令行工具   ｜  美化终端脚本的交互工具
# brew install harfbuzz                             # 字体库       ｜  文本整形引擎，支持复杂脚本
# brew install highway                              # 开发库       ｜  SIMD 优化库，提升计算性能
# brew install hiredis                              # 数据库库     ｜  Redis C 客户端库
# brew install htop                                 # 系统监控     ｜  交互式进程查看工具
# brew install icu4c@77                             # 开发库       ｜  国际化组件库，支持 Unicode
# brew install imagemagick                          # 图像处理     ｜  图像处理工具，支持多种格式
# brew install img2pdf                              # 文档处理     ｜  将图像转换为 PDF 的工具
# brew install imgdiff                              # 图像处理     ｜  比较图像差异的工具
# brew install ipfs                                 # 网络工具     ｜  分布式文件系统协议实现
# brew install iproute2mac                          # 网络工具     ｜  macOS 网络配置工具集
# brew install ipsw                                 # 开发工具     ｜  处理 iOS 固件文件的工具
# brew install iperf3                               # 网络工具     ｜  网络性能测试工具
# brew install jasper                               # 图形库       ｜  JPEG-2000 图像处理库
# brew install jbig2dec                             # 图形库       ｜  JBIG2 图像解码库
# brew install jbig2enc                             # 图形库       ｜  JBIG2 图像编码工具
# brew install jpeg-turbo                           # 图形库       ｜  优化的 JPEG 图像处理库
# brew install jpeg-xl                              # 图形库       ｜  下一代 JPEG 图像格式库
# brew install jq                                   # 命令行工具   ｜  JSON 数据处理工具
# brew install lame                                 # 音频库       ｜  MP3 音频编码库
# brew install leptonica                            # 图像处理     ｜  图像分析与处理库
# brew install less                                 # 命令行工具   ｜  文本分页查看工具
# brew install libao                                # 音频库       ｜  跨平台音频输出库
# brew install libarchive                           # 压缩库       ｜  多格式压缩与解压库
# brew install libass                               # 多媒体库     ｜  字幕渲染库，支持 ASS/SSA 格式
# brew install libassuan                            # 安全库       ｜  GnuPG 进程间通信库
# brew install libb2                                # 加密库       ｜  BLAKE2 哈希算法库
# brew install libbluray                            # 多媒体库     ｜  Blu-ray 光盘解码库
# brew install libcue                               # 多媒体库     ｜  CUE 文件解析库
# brew install libde265                             # 多媒体库     ｜  HEVC/H.265 视频解码库
# brew install libdeflate                           # 压缩库       ｜  高效 DEFLATE 压缩库
# brew install libevent                             # 开发库       ｜  异步事件通知库
# brew install libgcrypt                            # 加密库       ｜  通用加密算法库
# brew install libgit2                              # 版本控制     ｜  Git 核心功能库
# brew install libgpg-error                         # 安全库       ｜  GnuPG 错误处理库
# brew install libheif                              # 图形库       ｜  HEIF 图像格式处理库
# brew install libidn                               # 网络库       ｜  国际化域名支持库
# brew install libidn2                              # 网络库       ｜  国际化域名支持库（更新版）
# brew install libimagequant                        # 图像处理     ｜  图像颜色量化库
# brew install libksba                              # 安全库       ｜  X.509 证书处理库
# brew install liblqr                               # 图像处理     ｜  图像缩放库，支持内容感知
# brew install liblinear                            # 机器学习     ｜  线性分类与回归库
# brew install libmicrohttpd                        # 网络库       ｜  轻量级 HTTP 服务器库
# brew install libnghttp2                           # 网络库       ｜  HTTP/2 协议实现库
# brew install libogg                               # 音频库       ｜  Ogg 容器格式支持库
# brew install libomp                               # 开发库       ｜  OpenMP 并行编程库
# brew install libplacebo                           # 多媒体库     ｜  视频渲染与处理库
# brew install libpng                               # 图形库       ｜  PNG 图像格式处理库
# brew install libraqm                              # 文本处理     ｜  复杂文本布局库
# brew install libraw                               # 图像处理     ｜  相机 RAW 文件处理库
# brew install librist                              # 网络库       ｜  可靠互联网流传输库
# brew install libsamplerate                        # 音频库       ｜  音频采样率转换库
# brew install libsndfile                           # 音频库       ｜  多种音频格式读写库
# brew install libslirp                             # 网络库       ｜  用户态网络栈库
# brew install libsodium                            # 加密库       ｜  现代加密算法库
# brew install libsoxr                              # 音频库       ｜  高质量音频重采样库
# brew install libssh                               # 网络库       ｜  SSH 协议实现库
# brew install libssh2                              # 网络库       ｜  SSH2 协议客户端与服务器库
# brew install libtasn1                             # 安全库       ｜  ASN.1 数据处理库
# brew install libtiff                              # 图形库       ｜  TIFF 图像格式处理库
# brew install libtool                              # 开发工具     ｜  通用库构建工具
# brew install libunibreak                          # 文本处理     ｜  文本换行与分段库
# brew install libunistring                         # 文本处理     ｜  Unicode 字符串处理库
# brew install libusb                               # 硬件库       ｜  USB 设备访问库
# brew install libuv                                # 开发库       ｜  异步 I/O 事件循环库
# brew install libvidstab                           # 多媒体库     ｜  视频稳定化库
# brew install libvmaf                              # 多媒体库     ｜  视频质量评估库
# brew install libvorbis                            # 音频库       ｜  Vorbis 音频压缩库
# brew install libvpx                               # 多媒体库     ｜  VP8/VP9 视频编码库
# brew install libx11                               # 图形库       ｜  X11 协议客户端库
# brew install libxau                               # 图形库       ｜  X11 认证协议库
# brew install libxcb                               # 图形库       ｜  X11 C 绑定库
# brew install libxdmcp                             # 图形库       ｜  X11 显示管理协议库
# brew install libxext                              # 图形库       ｜  X11 扩展协议库
# brew install libxrender                           # 图形库       ｜  X11 渲染扩展库
# brew install libyaml                              # 开发库       ｜  YAML 数据解析库
# brew install libzip                               # 压缩库       ｜  ZIP 文件处理库
# brew install little-cms2                          # 图像处理     ｜  颜色管理库
# brew install lolcat                               # 娱乐工具     ｜  为终端文本添加彩虹颜色
# brew install lporg                                # 系统工具     ｜  macOS Launchpad 布局管理工具
# brew install lua                                  # 脚本语言     ｜  轻量嵌入式脚本语言
# brew install luajit                               # 脚本语言     ｜  高效的 Lua 解释器
# brew install lpeg                                 # 开发库       ｜  Lua 的模式匹配库
# brew install luv                                  # 开发库       ｜  Lua 的 libuv 绑定
# brew install lynx                                 # 网络工具     ｜  文本模式的网页浏览器
# brew install lz4                                  # 压缩库       ｜  高速压缩算法库
# brew install lzo                                  # 压缩库       ｜  实时压缩库
# brew install m4                                   # 开发工具     ｜  GNU 宏处理器
# brew install m-cli                                # 系统工具     ｜  macOS 系统管理 CLI 工具
# brew install mad                                  # 音频库       ｜  MPEG 音频解码库
# brew install mas                                  # 系统工具     ｜  Mac App Store 命令行工具
# brew install mbedtls                              # 安全库       ｜  轻量级加密与 TLS 库
# brew install mihomo                               # 网络工具     ｜  多功能代理工具
# brew install mist-cli                             # 开发工具     ｜  Mist 静态网站生成器 CLI
# brew install molten-vk                            # 图形库       ｜  Vulkan API 的 Metal 实现
# brew install mp4v2                                # 多媒体库     ｜  MP4 文件处理库
# brew install mpdecimal                            # 数学库       ｜  高精度十进制运算库
# brew install mpg123                               # 音频库       ｜  快速 MPEG 音频解码库
# brew install mpv                                  # 媒体播放     ｜  轻量级多功能媒体播放器
# brew install mujs                                 # 脚本语言     ｜  轻量级 JavaScript 引擎
# brew install mycli                                # 数据库工具   ｜  MySQL 交互式命令行客户端
# brew install nano                                 # 文本编辑     ｜  简单易用的终端文本编辑器
# brew install ncdu                                 # 系统工具     ｜  磁盘使用分析工具
# brew install ncurses                              # 开发库       ｜  终端界面库
# brew install neovim                               # 文本编辑     ｜  现代化的 Vim 编辑器
# brew install nettle                               # 加密库       ｜  加密算法与协议库
# brew install nmap                                 # 网络工具     ｜  网络扫描与安全审计工具
# brew install npth                                 # 开发库       ｜  非抢占式线程库
# brew install ocrmypdf                             # 文档处理     ｜  为 PDF 添加 OCR 文本层
# brew install oniguruma                            # 开发库       ｜  正则表达式库
# brew install opencore-amr                         # 音频库       ｜  AMR 音频编解码库
# brew install openexr                              # 图像处理     ｜  高动态范围图像格式库
# brew install openjpeg                             # 图形库       ｜  JPEG 2000 图像处理库
# brew install openssl@3                            # 安全库       ｜  加密与 SSL/TLS 协议库
# brew install openvpn                              # 网络工具     ｜  虚拟专用网络客户端
# brew install opus                                 # 音频库       ｜  低延迟音频压缩库
# brew install opusfile                             # 音频库       ｜  Opus 音频文件处理库
# brew install p11-kit                              # 安全库       ｜  PKCS#11 模块管理库
# brew install pandoc                               # 文档处理     ｜  通用文档格式转换工具
# brew install pango                                # 文本处理     ｜  文本布局与渲染库
# brew install parallel                             # 命令行工具   ｜  并行执行 shell 命令的工具
# brew install parallel-disk-usage                  # 系统工具     ｜  并行磁盘使用分析工具
# brew install pcre                                 # 开发库       ｜  Perl 兼容正则表达式库
# brew install pcre2                                # 开发库       ｜  更新的正则表达式库
# brew install pillow                               # Python 库    ｜  Python 图像处理库
# brew install pinentry                             # 安全工具     ｜  GnuPG 密码输入工具
# brew install pinentry-mac                         # 安全工具     ｜  macOS 原生 GnuPG 密码输入工具
# brew install pixman                               # 图形库       ｜  像素操作库，优化渲染性能
# brew install pkcs11-helper                        # 安全库       ｜  PKCS#11 辅助库
# brew install pngquant                             # 图像处理     ｜  PNG 图像无损压缩工具
# brew install powerlevel10k                        # 命令行壳     ｜  Zsh 的高性能主题
# brew install pstree                               # 系统工具     ｜  显示进程树结构
# brew install pv                                   # 命令行工具   ｜  监控管道数据传输进度
# brew install pybind11                             # 开发库       ｜  C++ 与 Python 绑定库
# brew install pycparser                            # Python 库    ｜  Python 的 C 语言解析器
# brew install python@3.12                          # 编程语言     ｜  Python 3.12 解释器
# brew install python@3.13                          # 编程语言     ｜  Python 3.13 解释器
# brew install qemu                                 # 虚拟化工具   ｜  通用机器模拟器与虚拟化工具
# brew install qpdf                                 # 文档处理     ｜  PDF 文件操作与转换工具
# brew install rav1e                                # 多媒体库     ｜  高效 AV1 视频编码库
# brew install readline                             # 开发库       ｜  命令行编辑与历史记录库
# brew install rename                               # 命令行工具   ｜  批量文件重命名工具
# brew install ripgrep                              # 命令行工具   ｜  超快文本搜索工具
# brew install rubberband                           # 音频库       ｜  音频时间拉伸与音高调整库
# brew install scrcpy                               # 移动设备工具 ｜  Android 屏幕镜像与控制工具
# brew install sdl2                                 # 开发库       ｜  跨平台多媒体开发库
# brew install shaderc                              # 开发库       ｜  GLSL/HLSL 着色器编译器
# brew install shared-mime-info                     # 开发库       ｜  MIME 类型数据库
# brew install shellcheck                           # 开发工具     ｜  Shell 脚本静态分析工具
# brew install snappy                               # 压缩库       ｜  高速压缩与解压库
# brew install sniffnet                             # 网络工具     ｜  网络流量监控工具
# brew install speex                                # 音频库       ｜  语音压缩编解码库
# brew install speedtest-cli                        # 网络工具     ｜  命令行网速测试工具
# brew install sqlite                               # 数据库       ｜  轻量级嵌入式数据库
# brew install srt                                  # 多媒体库     ｜  安全可靠传输协议库
# brew install subversion                           # 版本控制     ｜  集中式版本控制系统
# brew install svt-av1                              # 多媒体库     ｜  可扩展的 AV1 视频编码库
# brew install syncthing                            # 文件同步     ｜  去中心化文件同步工具
# brew install tesseract                            # 图像处理     ｜  开源 OCR 引擎
# brew install the_silver_searcher                  # 命令行工具   ｜  快速代码搜索工具
# brew install theora                               # 视频库       ｜  Theora 视频压缩库
# brew install tldr                                 # 命令行工具   ｜  简化的命令说明文档
# brew install topgrade                             # 系统工具     ｜  批量升级系统与软件的工具
# brew install trash                                # 系统工具     ｜  安全的文件删除工具
# brew install tree                                 # 命令行工具   ｜  显示目录树结构
# brew install tree-sitter                          # 开发库       ｜  语法解析库
# brew install ttygif                               # 命令行工具   ｜  录制终端为 GIF 动画
# brew install ttyrec                               # 命令行工具   ｜  录制终端会话的工具
# brew install uchardet                             # 文本处理     ｜  字符编码检测库
# brew install unibilium                            # 开发库       ｜  终端信息处理库
# brew install unbound                              # 网络工具     ｜  递归 DNS 解析服务器
# brew install unpaper                              # 图像处理     ｜  扫描文档清理工具
# brew install utf8proc                             # 文本处理     ｜  Unicode 文本处理库
# brew install vapoursynth                          # 多媒体库     ｜  视频处理脚本框架
# brew install vde                                  # 网络库       ｜  虚拟分布式以太网库
# brew install vulkan-headers                       # 图形库       ｜  Vulkan API 头文件
# brew install vulkan-loader                        # 图形库       ｜  Vulkan API 加载器
# brew install w3m                                  # 网络工具     ｜  终端文本网页浏览器
# brew install watch                                # 命令行工具   ｜  周期性执行命令并显示输出
# brew install webp                                 # 图形库       ｜  WebP 图像格式处理库
# brew install wget                                 # 网络工具     ｜  HTTP/FTP 文件下载工具
# brew install wireguard-go                         # 网络工具     ｜  WireGuard VPN 实现
# brew install wireguard-tools                      # 网络工具     ｜  WireGuard VPN 管理工具
# brew install x264                                 # 多媒体库     ｜  H.264 视频编码库
# brew install x265                                 # 多媒体库     ｜  H.265/HEVC 视频编码库
# brew install xorgproto                            # 图形库       ｜  X.Org 协议头文件
# brew install xvid                                 # 视频库       ｜  MPEG-4 视频编解码库
# brew install xxhash                               # 加密库       ｜  高效哈希算法库
# brew install xz                                   # 压缩库       ｜  LZMA 压缩工具与库
# brew install yq                                   # 命令行工具   ｜  YAML/JSON/XML 处理工具
# brew install yt-dlp                               # 下载工具     ｜  YouTube 视频下载工具
# brew install z                                    # 命令行工具   ｜  快速跳转到常用目录
# brew install zeromq                               # 网络库       ｜  高性能消息传递库
# brew install zimg                                 # 图像处理     ｜  图像缩放与格式转换库
# brew install zip                                  # 压缩工具     ｜  ZIP 文件压缩与解压工具
# brew install zsh                                  # 命令行壳     ｜  功能强大的交互式 shell
# brew install zsh-autosuggestions                  # 命令行工具   ｜  Zsh 自动建议插件
# brew install zsh-completions                      # 命令行工具   ｜  Zsh 命令补全插件
# brew install zsh-syntax-highlighting              # 命令行工具   ｜  Zsh 语法高亮插件
# brew install zstd                                 # 压缩库       ｜  高性能压缩算法库
#
#
#
# brew install --cask 115browser                    # 浏览器       ｜  115 网络推出的快速浏览器
# brew install --cask 4k-video-downloader           # 下载工具     ｜  下载高品质视频与音频
# brew install --cask 86box                         # 模拟器       ｜  经典 PC 硬件模拟器
# brew install --cask a-better-finder-attributes    # 文件管理     ｜  修改文件属性与元数据
# brew install --cask a-better-finder-rename        # 文件管理     ｜  批量文件重命名工具
# brew install --cask adobe-acrobat-pro             # 文档处理     ｜  专业 PDF 编辑与管理工具
# brew install --cask adobe-creative-cloud          # 创意工具     ｜  Adobe 创意软件套件管理
# brew install --cask adrive                        # 云存储       ｜  阿里云盘客户端
# brew install --cask adguard                       # 网络工具     ｜  广告拦截与隐私保护工具
# brew install --cask airfoil                       # 音频工具     ｜  流式传输音频到多设备
# brew install --cask airbuddy                      # 系统工具     ｜  优化 AirPods 在 macOS 使用
# brew install --cask airparrot                     # 屏幕共享     ｜  无线屏幕镜像与流媒体工具
# brew install --cask airserver                     # 屏幕共享     ｜  将 Mac 变为 AirPlay 接收器
# brew install --cask alacritty                     # 终端工具     ｜  快速 GPU 加速终端模拟器
# brew install --cask aldente                       # 系统工具     ｜  电池健康管理与充电控制
# brew install --cask alfred                        # 生产力工具   ｜  快捷启动与工作流工具
# brew install --cask amiberry                      # 模拟器       ｜  Amiga 计算机模拟器
# brew install --cask anaconda                      # 数据科学     ｜  Python 数据科学平台
# brew install --cask android-file-transfer         # 文件管理     ｜  Android 与 macOS 文件传输
# brew install --cask appcleaner                    # 系统工具     ｜  彻底卸载 macOS 应用 Stu
# brew install --cask applite                       # 软件管理     ｜  图形化 Homebrew 软件安装工具
# brew install --cask arc                           # 浏览器       ｜  创新标签管理的现代化浏览器
# brew install --cask ares                          # 模拟器       ｜  多平台游戏机模拟器
# brew install --cask asset-catalog-tinkerer        # 开发工具     ｜  iOS 应用资源目录管理工具
# brew install --cask audacity                      # 音频编辑     ｜  开源音频录制与编辑软件
# brew install --cask aural                         # 音乐播放     ｜  高保真音乐播放器
# brew install --cask audio-hijack                  # 音频工具     ｜  捕获与录制系统音频
# brew install --cask backuploupe                   # 备份工具     ｜  Time Machine 备份分析工具
# brew install --cask balenaetcher                  # 系统工具     ｜  制作可启动 USB 驱动器
# brew install --cask betterdisplay                 # 显示管理     ｜  增强 macOS 显示器设置
# brew install --cask bettertouchtool               # 系统工具     ｜  自定义输入设备与窗口管理
# brew install --cask betterzip                     # 压缩工具     ｜  增强型压缩与解压工具
# brew install --cask beyond-compare                # 开发工具     ｜  文件与文件夹比较工具
# brew install --cask bilibili                      # 视频播放     ｜  B 站 macOS 客户端
# brew install --cask binance                       # 金融工具     ｜  币安加密货币交易客户端
# brew install --cask blender                       # 3D 建模      ｜  开源 3D 创作套件
# brew install --cask blu-ray-player-pro            # 媒体播放     ｜  专业蓝光光盘播放器
# brew install --cask blueharvest                   # 系统工具     ｜  清理 macOS 文件系统元数据
# brew install --cask bobhelper                     # 系统工具     ｜  macOS 系统优化与清理工具
# brew install --cask burn                          # 光盘刻录     ｜  简单光盘刻录工具
# brew install --cask busycal                       # 日历工具     ｜  功能强大的日历与提醒工具
# brew install --cask calibre                       # 电子书管理   ｜  电子书管理与转换工具
# brew install --cask cameracontroller              # 硬件控制     ｜  控制相机与麦克风的工具
# brew install --cask camtasia                      # 视频编辑     ｜  屏幕录制与视频编辑软件
# brew install --cask carbon-copy-cloner            # 备份工具     ｜  磁盘克隆与备份工具
# brew install --cask cemu                          # 模拟器       ｜  Wii U 游戏机模拟器
# brew install --cask chatgpt                       # AI 工具      ｜  OpenAI ChatGPT macOS 客户端
# brew install --cask cinebench                     # 性能测试     ｜  CPU 与 GPU 性能基准测试
# brew install --cask claude                        # AI 工具      ｜  Anthropic AI 助手客户端
# brew install --cask clash-verge-rev               # 网络工具     ｜  代理与 VPN 管理工具
# brew install --cask clicker-for-netflix           # 媒体播放     ｜  增强 Netflix 播放体验
# brew install --cask clock-signal                  # 模拟器       ｜  复古计算机与游戏机模拟器
# brew install --cask cloudflare-warp               # 网络工具     ｜  Cloudflare VPN 客户端
# brew install --cask coderunner                    # 开发工具     ｜  轻量级代码运行与调试工具
# brew install --cask command-x                     # 系统工具     ｜  增强 macOS 剪贴板管理
# brew install --cask commandq                      # 系统工具     ｜  快速切换与关闭应用
# brew install --cask console                       # 系统工具     ｜  macOS 控制台日志查看器
# brew install --cask cool-retro-term               # 终端工具     ｜  复古风格终端模拟器
# brew install --cask coolterm                      # 硬件工具     ｜  串口与终端仿真工具
# brew install --cask cork                          # 系统工具     ｜  管理 macOS 应用偏好设置
# brew install --cask coteditor                     # 文本编辑     ｜  轻量级纯文本编辑器
# brew install --cask crossover                     # 虚拟化工具   ｜  在 macOS 运行 Windows 应用
# brew install --cask crunch                        # 图像处理     ｜  批量图像压缩与优化工具
# brew install --cask cryptomator                   # 加密工具     ｜  云存储文件加密工具
# brew install --cask cyberduck                     # 文件传输     ｜  FTP/SFTP 与云存储客户端
# brew install --cask datagraph                     # 数据可视化   ｜  数据分析与图表绘制工具
# brew install --cask data-rescue                   # 数据恢复     ｜  专业数据恢复工具
# brew install --cask db-browser-for-sqlite         # 数据库工具   ｜  SQLite 数据库管理工具
# brew install --cask dbgate                        # 数据库工具   ｜  多数据库管理与查询工具
# brew install --cask dcommander                    # 文件管理     ｜  双栏文件管理器
# brew install --cask deepl                         # 翻译工具     ｜  高质量文本翻译客户端
# brew install --cask deltachat                     # 通讯工具     ｜  基于邮件的去中心化聊天
# brew install --cask descript                      # 音频编辑     ｜  文本驱动的音频与视频编辑
# brew install --cask devcleaner                    # 开发工具     ｜  清理 Xcode 缓存与文件
# brew install --cask devonthink                    # 文档管理     ｜  智能文档与信息管理工具
# brew install --cask devtoys                       # 开发工具     ｜  开发者实用工具集合
# brew install --cask diagnostics                   # 系统工具     ｜  macOS 系统诊断工具
# brew install --cask diffusionbee                  # AI 工具      ｜  本地运行的 AI 图像生成器
# brew install --cask discord                       # 通讯工具     ｜  游戏与社区聊天平台
# brew install --cask disk-drill                    # 数据恢复     ｜  文件与分区恢复工具
# brew install --cask diskcatalogmaker              # 文件管理     ｜  磁盘与文件目录管理工具
# brew install --cask dolphin                       # 模拟器       ｜  GameCube 与 Wii 模拟器
# brew install --cask dosbox                        # 模拟器       ｜  DOS 环境模拟器
# brew install --cask dosbox-staging                # 模拟器       ｜  改进版 DOSBox 模拟器
# brew install --cask dosbox-x                      # 模拟器       ｜  增强型 DOS 模拟器
# brew install --cask douyin                        # 视频播放     ｜  抖音 macOS 客户端
# brew install --cask douyin-chat                   # 通讯工具     ｜  抖音聊天 macOS 客户端
# brew install --cask downie                        # 下载工具     ｜  视频与音频下载工具
# brew install --cask draw-things                   # AI 工具      ｜  AI 图像生成与编辑工具
# brew install --cask drawio                        # 图表工具     ｜  在线与离线流程图编辑器
# brew install --cask drivedx                       # 系统工具     ｜  磁盘健康监控与诊断
# brew install --cask dropzone                      # 生产力工具   ｜  拖放文件触发自动化任务
# brew install --cask dropshare                     # 文件共享     ｜  快速上传与分享文件
# brew install --cask eaglefiler                    # 文档管理     ｜  文档与邮件归档工具
# brew install --cask ea                            # 游戏平台     ｜  EA 游戏平台客户端
# brew install --cask easy-move+resize              # 窗口管理     ｜  快捷调整窗口大小与位置
# brew install --cask easydict                      # 翻译工具     ｜  快速词典与翻译工具
# brew install --cask easyfind                      # 文件管理     ｜  快速搜索文件与文件夹
# brew install --cask elgato-stream-deck            # 硬件工具     ｜  控制 Elgato Stream Deck
# brew install --cask element                       # 通讯工具     ｜  Matrix 协议的去中心化聊天
# brew install --cask elmedia-player                # 媒体播放     ｜  多格式视频播放器
# brew install --cask epic-games                    # 游戏平台     ｜  Epic Games Store 客户端
# brew install --cask escrcpy                       # 移动设备工具 ｜  增强版 Android 屏幕镜像
# brew install --cask excalidrawz                   # 图表工具     ｜  手绘风格白板绘图工具
# brew install --cask file-juicer                   # 文件处理     ｜  提取文件中的隐藏内容
# brew install --cask filepane                      # 文件管理     ｜  增强 Finder 拖放功能
# brew install --cask firealpaca                    # 图像编辑     ｜  轻量级数字绘画工具
# brew install --cask firefox                       # 浏览器       ｜  开源隐私保护浏览器
# brew install --cask flowvision                    # 生产力工具   ｜  任务与项目管理工具
# brew install --cask flykey                        # 生产力工具   ｜  快捷键查询
# brew install --cask fluor                         # 系统工具     ｜  快速切换 macOS 应用图标
# brew install --cask flycast                       # 模拟器       ｜  Dreamcast 与 arcade 模拟器
# brew install --cask flykey                        # 系统工具     ｜  自定义键盘快捷键工具
# brew install --cask foobar2000                    # 音乐播放     ｜  高保真音频播放器
# brew install --cask folx                          # 下载工具     ｜  功能丰富的下载管理器
# brew install --cask font-fira-code                # 字体         ｜  编程用等宽字体
# brew install --cask font-twitter-color-emoji      # 字体         ｜  Twitter 彩色表情符号字体
# brew install --cask fork                          # 版本控制     ｜  Git 图形化客户端
# brew install --cask forklift                      # 文件管理     ｜  强大的双栏文件管理器
# brew install --cask free42-decimal                # 模拟器       ｜  HP-42S 计算器模拟器
# brew install --cask fs-uae                        # 模拟器       ｜  Amiga 模拟器
# brew install --cask fs-uae-launcher               # 模拟器       ｜  FS-UAE 模拟器图形界面
# brew install --cask garagesale                    # 电商工具     ｜  eBay listing 管理工具
# brew install --cask gb-studio                     # 游戏开发     ｜  复古风格游戏开发工具
# brew install --cask gearboy                       # 模拟器       ｜  Game Boy 模拟器
# brew install --cask genesis-plus                  # 模拟器       ｜  Sega Genesis/Mega Drive 模拟器
# brew install --cask geogebra                      # 教育工具     ｜  数学与几何教学软件
# brew install --cask gimp                          # 图像编辑     ｜  开源图像编辑软件
# brew install --cask github                        # 版本控制     ｜  GitHub 桌面客户端
# brew install --cask gog-galaxy                    # 游戏平台     ｜  GOG 游戏平台客户端
# brew install --cask go2shell                      # 终端工具     ｜  Finder 快速打开终端
# brew install --cask google-chrome                 # 浏览器       ｜  谷歌 Chrome 浏览器
# brew install --cask google-drive                  # 云存储       ｜  谷歌云盘客户端
# brew install --cask google-earth-pro              # 地理工具     ｜  高级版谷歌地球
# brew install --cask gpg-suite                     # 安全工具     ｜  GPG 加密与签名工具
# brew install --cask graphicconverter              # 图像编辑     ｜  多功能图像转换与编辑
# brew install --cask grids                         # 社交工具     ｜  Instagram 桌面客户端
# brew install --cask gzdoom                        # 游戏引擎     ｜  增强型 Doom 游戏引擎
# brew install --cask hammerspoon                   # 自动化工具   ｜  Lua 驱动的 macOS 自动化
# brew install --cask handbrake                     # 视频转换     ｜  开源视频转码与压缩工具
# brew install --cask hazel                         # 文件管理     ｜  自动化文件整理工具
# brew install --cask heroic                        # 游戏平台     ｜  Epic Games 开源客户端
# brew install --cask hex-fiend                     # 开发工具     ｜  十六进制编辑器
# brew install --cask hookmark                      # 生产力工具   ｜  文件与笔记链接工具
# brew install --cask houdahspot                    # 文件管理     ｜  高级文件搜索工具
# brew install --cask iconjar                       # 设计工具     ｜  图标与资源管理工具
# brew install --cask iina                          # 媒体播放     ｜  现代 macOS 视频播放器
# brew install --cask imazing                       # 移动设备工具 ｜  iOS 设备管理与备份
# brew install --cask image2icon                    # 图像处理     ｜  将图像转换为 macOS 图标
# brew install --cask imageoptim                    # 图像处理     ｜  无损压缩图像工具
# brew install --cask inkscape                      # 图像编辑     ｜  开源矢量图形编辑器
# brew install --cask input-source-pro              # 系统工具     ｜  快速切换输入法
# brew install --cask insync                        # 云存储       ｜  谷歌云盘与 OneDrive 同步
# brew install --cask install-disk-creator          # 系统工具     ｜  创建 macOS 安装盘
# brew install --cask iterm2                        # 终端工具     ｜  功能强大的终端替代品
# brew install --cask itsycal                       # 日历工具     ｜  轻量级菜单栏日历
# brew install --cask jd-gui                        # 开发工具     ｜  Java 反编译工具
# brew install --cask jdownloader                   # 下载工具     ｜  跨平台下载管理器
# brew install --cask kaleidoscope                  # 开发工具     ｜  文件与图像差异比较工具
# brew install --cask karabiner-elements            # 系统工具     ｜  自定义键盘映射工具
# brew install --cask keyboardholder                # 系统工具     ｜  锁定键盘输入的工具
# brew install --cask keycastr                      # 系统工具     ｜  显示键盘输入的工具
# brew install --cask kigb                          # 模拟器       ｜  Game Boy 模拟器
# brew install --cask knockknock                    # 安全工具     ｜  显示 macOS 持久化进程
# brew install --cask kodi                          # 媒体播放     ｜  开源媒体中心软件
# brew install --cask krita                         # 图像编辑     ｜  专业数字绘画软件
# brew install --cask latexit                       # 文档工具     ｜  LaTeX 公式编辑器
# brew install --cask latest                        # 软件管理     ｜  检查与更新 macOS 应用
# brew install --cask licecap                       # 屏幕录制     ｜  录制屏幕为 GIF 动画
# brew install --cask lingon-x                      # 系统工具     ｜  管理 macOS 启动项
# brew install --cask linkliar                      # 网络工具     ｜  伪装 MAC 地址的工具
# brew install --cask locationsimulator             # 开发工具     ｜  模拟 macOS 位置服务
# brew install --cask loom                          # 视频工具     ｜  快速录制与分享视频
# brew install --cask loop                          # 生产力工具   ｜  任务与时间管理工具
# brew install --cask loopback                      # 音频工具     ｜  虚拟音频设备路由工具
# brew install --cask macai                         # AI 工具      ｜  macOS 原生 AI 助手
# brew install --cask maccleaner-pro                # 系统工具     ｜  系统清理与优化工具
# brew install --cask maccy                         # 剪贴板管理   ｜  轻量级剪贴板历史工具
# brew install --cask macdroid                      # 文件管理     ｜  Android 与 macOS 文件传输
# brew install --cask macdown                       # 文本编辑     ｜  Markdown 编辑与预览工具
# brew install --cask macfuse                       # 系统工具     ｜  macOS 文件系统扩展
# brew install --cask macgamestore                  # 游戏平台     ｜  Mac 游戏购买平台
# brew install --cask macpilot                      # 系统工具     ｜  高级 macOS 系统设置工具
# brew install --cask mactracker                    # 系统工具     ｜  macOS 硬件信息数据库
# brew install --cask macupdater                    # 软件管理     ｜  自动更新 macOS 应用
# brew install --cask macvim                        # 文本编辑     ｜  macOS 原生 Vim 编辑器
# brew install --cask macwhisper                    # 音频工具     ｜  本地语音转文字工具
# brew install --cask maintenance                   # 系统工具     ｜  macOS 系统维护工具
# brew install --cask makemkv                       # 媒体工具     ｜  转换 DVD/Blu-ray 为 MKV
# brew install --cask manico                        # 系统工具     ｜  快速切换 macOS 应用
# brew install --cask mdrp                          # 媒体播放     ｜  多功能媒体播放器
# brew install --cask mediainfo                     # 媒体工具     ｜  显示音视频文件详细信息
# brew install --cask melonds                       # 模拟器       ｜  Nintendo DS 模拟器
# brew install --cask messenger                     # 通讯工具     ｜  Facebook Messenger 客户端
# brew install --cask mgba                          # 模拟器       ｜  Game Boy Advance 模拟器
# brew install --cask microsoft-auto-update         # 软件管理     ｜  Microsoft 软件更新工具
# brew install --cask microsoft-edge                # 浏览器       ｜  微软 Edge 浏览器
# brew install --cask microsoft-teams               # 通讯工具     ｜  团队协作与会议平台
# brew install --cask mini-vmac                     # 模拟器       ｜  早期 Macintosh 模拟器
# brew install --cask mipony                        # 下载工具     ｜  轻量级下载管理器
# brew install --cask mist                          # 开发工具     ｜  静态网站生成器
# brew install --cask mkvtoolnix                    # 媒体工具     ｜  MKV 文件编辑与处理工具
# brew install --cask mochi-diffusion               # AI 工具      ｜  本地 AI 图像生成工具
# brew install --cask mono-mdk-for-visual-studio    # 开发工具     ｜  Mono 运行时 for Visual Studio
# brew install --cask moonlight                     # 游戏串流     ｜  NVIDIA GameStream 客户端
# brew install --cask mos                           # 系统工具     ｜  优化 macOS 鼠标滚动
# brew install --cask motrix                        # 下载工具     ｜  跨平台下载管理器
# brew install --cask mountain-duck                 # 文件传输     ｜  云存储挂载为本地磁盘
# brew install --cask multitouch                    # 系统工具     ｜  自定义触控板手势
# brew install --cask nestopia                      # 模拟器       ｜  NES/Famicom 模拟器
# brew install --cask neteasemusic                  # 音乐播放     ｜  网易云音乐 macOS 客户端
# brew install --cask netnewswire                   # 新闻阅读     ｜  RSS/Atom 新闻阅读器
# brew install --cask netron                        # 开发工具     ｜  神经网络模型可视化工具
# brew install --cask netspot                       # 网络工具     ｜  Wi-Fi 网络分析与优化
# brew install --cask nextcloud                     # 云存储       ｜  开源云存储客户端
# brew install --cask notchnook                     # 系统工具     ｜  优化 macOS 刘海屏空间
# brew install --cask notion                        # 生产力工具   ｜  全能笔记与项目管理工具
# brew install --cask numi                          # 计算工具     ｜  菜单栏计算器与单位转换
# brew install --cask nvidia-geforce-now            # 游戏串流     ｜  NVIDIA 云游戏平台客户端
# brew install --cask obs                           # 视频工具     ｜  开源屏幕录制与直播软件
# brew install --cask obsidian                      # 笔记工具     ｜  知识图谱与 Markdown 笔记
# brew install --cask omnidisksweeper               # 系统工具     ｜  磁盘空间清理与分析工具
# brew install --cask omnifocus                     # 任务管理     ｜  强大的任务与项目管理工具
# brew install --cask omnigraffle                   # 图表工具     ｜  专业流程图与图表绘制软件
# brew install --cask omnioutliner                  # 文档工具     ｜  大纲与结构化笔记工具
# brew install --cask omniplan                      # 项目管理     ｜  项目计划与甘特图工具
# brew install --cask one-switch                    # 系统工具     ｜  快速切换 macOS 设置
# brew install --cask only-switch                   # 系统工具     ｜  简洁的状态切换工具
# brew install --cask openemu                       # 模拟器       ｜  多平台复古游戏模拟器
# brew install --cask openvpn-connect               # 网络工具     ｜  OpenVPN 官方客户端
# brew install --cask oversight                     # 安全工具     ｜  监控麦克风与摄像头使用
# brew install --cask onyx                          # 系统工具     ｜  macOS 系统优化与维护工具
# brew install --cask pacifist                      # 系统工具     ｜  检查与提取 macOS 安装包
# brew install --cask paintbrush                    # 图像编辑     ｜  简单图像编辑与绘图工具
# brew install --cask paragon-extfs                 # 文件系统     ｜  macOS 读写 Linux extFS
# brew install --cask paragon-ntfs                  # 文件系统     ｜  macOS 读写 NTFS 磁盘
# brew install --cask parsec                        # 远程工具     ｜  低延迟远程桌面与游戏串流
# brew install --cask pearcleaner                   # 系统工具     ｜  彻底卸载 macOS 应用
# brew install --cask pdf-expert                    # 文档处理     ｜  高级 PDF 编辑与批注工具
# brew install --cask pdf-squeezer                  # 文档处理     ｜  压缩与优化 PDF 文件
# brew install --cask picgo                         # 图像工具     ｜  图片上传与管理工具
# brew install --cask plex                          # 媒体管理     ｜  个人媒体服务器与播放器
# brew install --cask popclip                       # 生产力工具   ｜  增强 macOS 文本选择菜单
# brew install --cask powershell                    # 命令行工具   ｜  跨平台 PowerShell 终端
# brew install --cask ppsspp                        # 模拟器       ｜  PSP 游戏机模拟器
# brew install --cask pritunl                       # 网络工具     ｜  开源 VPN 客户端
# brew install --cask qqlive                        # 视频播放     ｜  腾讯视频 macOS 客户端
# brew install --cask qqmusic                       # 音乐播放     ｜  QQ 音乐 macOS 客户端
# brew install --cask qspace-pro                    # 文件管理     ｜  多标签文件管理器
# brew install --cask qbittorrent                   # 下载工具     ｜  开源 BitTorrent 客户端
# brew install --cask qlmarkdown                    # 文档工具     ｜  Markdown 文件快速预览
# brew install --cask raze                          # 游戏引擎     ｜  增强型 Build 引擎游戏
# brew install --cask redream                       # 模拟器       ｜  Dreamcast 游戏机模拟器
# brew install --cask renamer                       # 文件管理     ｜  批量文件重命名工具
# brew install --cask retroarch                     # 模拟器       ｜  多平台游戏模拟器框架
# brew install --cask royal-tsx                     # 远程工具     ｜  远程桌面与服务器管理
# brew install --cask rustdesk                      # 远程工具     ｜  开源远程桌面软件
# brew install --cask screen-studio                 # 视频工具     ｜  屏幕录制与视频编辑工具
# brew install --cask screenflow                    # 视频编辑     ｜  专业屏幕录制与编辑软件
# brew install --cask scrivener                     # 写作工具     ｜  专业写作与长文档管理
# brew install --cask scummvm                       # 模拟器       ｜  经典冒险游戏模拟器
# brew install --cask secretive                     # 安全工具     ｜  管理 macOS 安全密钥
# brew install --cask sensei                        # 系统工具     ｜  系统性能监控与优化
# brew install --cask sequel-ace                    # 数据库工具   ｜  MySQL/MariaDB 管理工具
# brew install --cask session                       # 网络工具     ｜  安全的 SOCKS5 代理客户端
# brew install --cask sigil                         # 文档工具     ｜  EPUB 电子书编辑器
# brew install --cask signal                        # 通讯工具     ｜  加密即时通讯应用
# brew install --cask simplex                       # 通讯工具     ｜  去中心化隐私聊天工具
# brew install --cask sip                           # 系统工具     ｜  macOS 颜色拾取工具
# brew install --cask skype                         # 通讯工具     ｜  视频通话与即时通讯
# brew install --cask sloth                         # 系统工具     ｜  显示 macOS 活动进程
# brew install --cask sms-plus                      # 模拟器       ｜  Sega Master System 模拟器
# brew install --cask snes9x                        # 模拟器       ｜  Super Nintendo 模拟器
# brew install --cask snipaste                      # 截图工具     ｜  截图与贴图工具
# brew install --cask soundsource                   # 音频工具     ｜  macOS 音频输入输出管理
# brew install --cask spotify                       # 音乐播放     ｜  在线音乐流媒体客户端
# brew install --cask spotube                       # 音乐播放     ｜  开源 Spotify 客户端
# brew install --cask sqlpro-for-sqlite             # 数据库工具   ｜  SQLite 数据库管理工具
# brew install --cask stash                         # 版本控制     ｜  Git 图形化客户端
# brew install --cask stats                         # 系统监控     ｜  菜单栏系统资源监控
# brew install --cask steam                         # 游戏平台     ｜  Steam 游戏平台客户端
# brew install --cask stella                        # 模拟器       ｜  Atari 2600 游戏机模拟器
# brew install --cask subler                        # 媒体工具     ｜  音视频元数据编辑工具
# brew install --cask suspicious-package            # 系统工具     ｜  检查 macOS 安装包内容
# brew install --cask swish                         # 系统工具     ｜  增强 macOS 触控板手势
# brew install --cask switchhosts                   # 网络工具     ｜  Hosts 文件管理工具
# brew install --cask syncthing                     # 文件同步     ｜  去中心化文件同步客户端
# brew install --cask synology-chat                 # 通讯工具     ｜  Synology 聊天客户端
# brew install --cask synologyassistant             # 存储工具     ｜  Synology NAS 管理工具
# brew install --cask syntax-highlight              # 开发工具     ｜  macOS 语法高亮扩展
# brew install --cask tailscale                     # 网络工具     ｜  零配置 VPN 客户端
# brew install --cask telegram                      # 通讯工具     ｜  快速安全的即时通讯应用
# brew install --cask termius                       # 远程工具     ｜  SSH 与 SFTP 客户端
# brew install --cask texstudio                     # 文档工具     ｜  LaTeX 文档编辑器
# brew install --cask textmate                      # 文本编辑     ｜  强大的代码与文本编辑器
# brew install --cask textsniper                    # 图像工具     ｜  OCR 屏幕文本提取工具
# brew install --cask tg-pro                        # 系统工具     ｜  监控与控制 Mac 温度
# brew install --cask thunder                       # 下载工具     ｜  迅雷 macOS 客户端
# brew install --cask tinypng4mac                   # 图像处理     ｜  TinyPNG 图像压缩工具
# brew install --cask tm-error-logger               # 开发工具     ｜  Time Machine 错误日志工具
# brew install --cask tor-browser                   # 浏览器       ｜  匿名网络访问浏览器
# brew install --cask transmission                  # 下载工具     ｜  轻量级 BitTorrent 客户端
# brew install --cask transmit                      # 文件传输     ｜  高级 FTP/SFTP 客户端
# brew install --cask tripmode                      # 网络工具     ｜  控制 macOS 网络流量
# brew install --cask trim-enabler                  # 系统工具     ｜  启用 macOS SSD TRIM
# brew install --cask tunnelblick                   # 网络工具     ｜  OpenVPN 图形化客户端
# brew install --cask typora                        # 文本编辑     ｜  简洁 Markdown 编辑器
# brew install --cask ultimate-vocal-remover        # 音频工具     ｜  AI 驱动的人声分离工具
# brew install --cask unetbootin                    # 系统工具     ｜  创建可启动 USB 驱动器
# brew install --cask uninstallpkg                  # 系统工具     ｜  卸载 macOS 安装包
# brew install --cask utm                           # 虚拟化工具   ｜  macOS 原生虚拟机工具
# brew install --cask vamiga                        # 模拟器       ｜  Amiga 计算机模拟器
# brew install --cask veracrypt                     # 加密工具     ｜  磁盘与文件加密工具
# brew install --cask via                           # 键盘工具     ｜  自定义键盘布局工具
# brew install --cask vial                          # 键盘工具     ｜  键盘固件配置工具
# brew install --cask videofusion                   # 视频编辑     ｜  视频剪辑与特效工具
# brew install --cask vimr                          # 文本编辑     ｜  macOS 原生 Vim 编辑器
# brew install --cask virtualbuddy                  # 虚拟化工具   ｜  macOS 虚拟机管理工具
# brew install --cask virtualc64                    # 模拟器       ｜  Commodore 64 模拟器
# brew install --cask visual-studio                 # 开发工具     ｜  Microsoft Visual Studio IDE
# brew install --cask visual-studio-code            # 文本编辑     ｜  轻量级代码编辑器
# brew install --cask visualboyadvance-m            # 模拟器       ｜  Game Boy Advance 模拟器
# brew install --cask vmware-fusion                 # 虚拟化工具   ｜  运行 Windows 等虚拟机
# brew install --cask vnc-viewer                    # 远程工具     ｜  VNC 远程桌面客户端
# brew install --cask vsd-viewer                    # 文档工具     ｜  Visio 文件查看工具
# brew install --cask vuescan                       # 图像工具     ｜  扫描仪驱动与图像处理
# brew install --cask warp                          # 终端工具     ｜  现代化终端客户端
# brew install --cask webcatalog                    # 生产力工具   ｜  将网站转为桌面应用
# brew install --cask webull                        # 金融工具     ｜  股票与投资交易平台
# brew install --cask wechat                        # 通讯工具     ｜  微信 macOS 客户端
# brew install --cask weiyun                        # 云存储       ｜  腾讯微云客户端
# brew install --cask welly                         # 网络工具     ｜  BBS 客户端与终端工具
# brew install --cask whatroute                     # 网络工具     ｜  网络诊断与路由跟踪
# brew install --cask whatsapp                      # 通讯工具     ｜  WhatsApp 即时通讯客户端
# brew install --cask whisky                        # 虚拟化工具   ｜  在 macOS 运行 Windows 游戏
# brew install --cask windows-app                   # 远程工具     ｜  Windows 远程桌面客户端
# brew install --cask windows95                     # 模拟器       ｜  Windows 95 系统模拟器
# brew install --cask windterm                      # 终端工具     ｜  多协议终端与 SSH 客户端
# brew install --cask wireshark                     # 网络工具     ｜  网络数据包分析工具
# brew install --cask wombat                        # 生产力工具   ｜  任务与时间跟踪工具
# brew install --cask wwdc                          # 开发工具     ｜  访问 WWDC 视频与资源
# brew install --cask xemu                          # 模拟器       ｜  初代 Xbox 游戏机模拟器
# brew install --cask xnviewmp                      # 图像管理     ｜  多功能图像查看与管理
# brew install --cask xquartz                       # 图形工具     ｜  macOS X11 图形环境
# brew install --cask yesplaymusic                  # 音乐播放     ｜  开源音乐播放器
# brew install --cask yubico-authenticator          # 安全工具     ｜  YubiKey 认证管理工具
# brew install --cask zesarux                       # 模拟器       ｜  ZX Spectrum 模拟器
# brew install --cask zipic                         # 压缩工具     ｜  轻量级压缩与解压工具
# brew install --cask zotero                        # 文献管理     ｜  学术文献管理与引用工具
# brew install --cask zoom                          # 通讯工具     ｜  视频会议与远程协作
#
#
#
#
# -----------
# 协议：
# -----------
#
# 分发协议：MIT协议
#
# 注意：本规则所有程序代码和注释，均来自于 xAI Grok ( DeepThink )
