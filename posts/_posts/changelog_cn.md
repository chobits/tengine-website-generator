## 变更列表


#### Tengine-2.2.0 [2016-12-02]

*   Security: 进程将特殊构造的请求体写到临时文件时会触发段错误 (CVE-2016-4450) [0x7E]
*   Feature: 增加force_exit指令 [aholic, chobits]
*   Feature: debug pool模块，该模块可以获取nginx内存池的内存使用情况 [chobits]
*   Change: 合并HTTP/2模块，删除SPDY模块 [PeterDaveHello]
*   Change: 合并nginx-1.8.1版本的修改 [lhanjian, magicbear, chobits]
*   Change: 支持EPOLL_EXCLUSIVE [cfsego]
*   Change: 导出API: ngx_http_upstream_check_upstream_down [detailyang]
*   Change: 在TCP健康检查功能中关闭check_keepalive_requests特性 [cynron]
*   Change: 更新reqstatus模块 [cfsego]
*   Bugfix: 删除ngx_http_named_location中重复代码 [innomentats]
*   Bugfix: 修复session-sticky模块的bug [detailyang]
*   Bugfix: 修复rsolve.conf文件解析器的bug [zuopucuen]
*   Bugfix: 修复tfs模块编译警告 [monadbobo]
*   Bugfix: dynamic_resolver特性在proxy_pass指令使用变量时会触发段错误 [chobits]
*   Bugfix: 修复session-sticky模块设置无效的Set-Cookie值的bug [YanagiEiichi]
*   Bugfix: 修复dyups模块中cf变量未初始化的bug [wangfakang]
*   Bugfix: 修复健康检查模块中含有重复peers的bug [FqqCS, taoyuanyuan]
*   Bugfix: 修复concat模块中错误的javascript内容类型 [IYism]


#### Tengine-2.1.2 [2015-12-31]

*   Feature: ngx_http_reqstat_module模块可以跟踪记录请求的内部重定向 [cfsego]
*   Feature: 支持HTTP/2，支持向后兼容SPDY v3 [PeterDaveHello, cfsego]
*   Feature: ngx_debug_pool模块协助分析内存状况 [chobits]
*   Feature: 支持$upstream_cookie变量
*   Bugfix: 修复ngx_http_dyups_module模块对相同后端服务器合并的问题 [FqqCS, taoyuanyuan]
*   Bugfix: 修复不能编译lua-upstream-nginx-module模块的问题 [cfsego]
*   Bugfix: 修复ngx_http_concat_module模块对javascript无效的问题 [IYism]


#### Tengine-2.1.1 [2015-08-12]

*   Feature: 支持动态upstream更新 [yzprofile]
*   Feature: 增强ngx_http_reqstat_module模块 [cfsego]
*   Feature: 增加ssl_verify_client_exception指令 [InfoHunter]
*   Change: 降低解析配置的内存消耗 [ilexshen]
*   Change: trim模块增加$trim_bytes和$trim_original_bytes [taoyuanyuan]
*   Change: 升级debian二进制包的版本到2.1.0 [PeterDaveHello]
*   Change: 将ngx_http_spdy_module模块集成到travis-ci自动编译 [chobits]
*   Change: 更新SPDY/3.1 [chobits]
*   Change: SPDY时关闭proxy_request_buffering指令 [chobits]
*   Change: 增加编译选项支持设置linker [tanguofu]
*   Bugfix: 修复SPDY的Backport bug [nginx official, ym]
*   Bugfix: SPDY和SSL模块一起编译时报错 [ym]
*   Bugfix: 修复打开reuseport的bug [monadbobo]


#### Tengine-2.1.0 [2014-12-19]

*   Feature: 支持SO_REUSEPORT选项，以提升CPU负载均衡性和性能 [monadbobo]
*   Feature: 支持动态解析upstream中出现的域名 [InfoHunter]
*   Feature: rewrite指令支持重定向到命名location [yzprofile]
*   Feature: image_filter指令支持crop_keepx和crop_keepy参数 [Lax]
*   Feature: consistent_hash模块和session_sticky模块支持SSL会话保持 [dinic]
*   Feature: 支持travis-ci.org自动编译 [Jamyn]
*   Feature: 健康检查模块支持FASTCGI检查 [yzprofile]
*   Feature: 增强sysguard模块的功能 [InfoHunter]
*   Feature: 新增变量$normalized_request得到规范化的请求 [yunkai]
*   Feature: dso的include指令支持通配符 [monadbobo]
*   Feature: 新增gzip_clear_etag指令 [taoyuanyuan]
*   Feature: 为log_escape指令添加unprintable参数 [skoo87]
*   Change: 合并nginx-1.6.2版本的修改 [cfsego, taoyuanyuan, chobits]
*   Change: round robin负载均衡算法随机选择某个源站作为循环起点 [taoyuanyuan]
*   Change: 对共享内存中的碎片进行优化 [chobits]
*   Bugfix: SPDY/3关闭连接时去掉drop标志 [chobits]
*   Bugfix: 修复SPDY/3出现连接泄漏的问题 [chobits]
*   Bugfix: 修复limit_req模块将长度超过255个字符的key截断的问题 [chobits]
*   Bugfix: 解析/etc/resolv.conf中的IPv6地址出错 [lifeibo]
*   Bugfix: 通过红黑树查找到错误的upstream [taoyuanyuan]


#### Tengine-2.0.3 [2014-05-30]

*   Feature: 支持按指定关键字(域名，url等)收集Tengine运行状态 [cfsego]
*   Feature: 支持debian、ubuntu打包 [betetrpm, szepeviktor]
*   Change: 合并nginx-1.4.7的修改 [chobits]
*   Change: 使用红黑树优化upstream配置解析和查找 [SarahWang]
*   Change: 更新版权信息
*   Bugfix: 修复session-sticky模块相关问题 [dinic]
*   Bugfix: 修复DSO编译和安装模块的问题 [cfsego]
*   Bugfix: 修复spdy相关问题 [chobits]


#### Tengine-2.0.2 [2014-03-28]

*   Bugfix: 在读事件处理完后继续发送SPDY数据 [chobits]
*   Bugfix: CVE-2014-0133以及CVE-2014-0088 [chobits]


#### Tengine-2.0.1 [2014-03-06]

*   Feature: 请求体不缓存的机制支持chunked输入 [yaoweibin]
*   Feature: trim模块支持更多规则，支持根据变量启用 [taoyuanyuan]
*   Feature: 利用/etc/resolv.conf自动配置resolver [lifeibo, yaoweibin]
*   Feature: 增加$ascii_变量前缀，可以生成任意ASCII字符 [yzprofile]
*   Feature: 增加"image_filter_crop_offset"指令 [lax]
*   Change: 合并截至nginx-1.4.6版本的所有修改 [chobits, cfsego]
*   Bugfix: 修正使用长连接进行健康检查时报错的问题 [lilbedwin]
*   Bugfix: 修正使用WebSocket时nginx崩溃的问题 [Hao Chen]
*   Bugfix: 减少nginx处理大文件时的内存消耗 [cfsego]
*   Bugfix: 在未设置URI时，禁用跳转到named locations的重定向


#### Tengine-2.0.0 [2014-01-08]

*   Feature: 增强DSO模块，编译动态模块不再依赖原始编译环境 [monadbobo]
*   Feature: 支持SPDY v3协议，自动检测同一端口的SPDY请求和HTTP请求 [lilbedwin、chobits]
*   Feature: 支持设置proxy、memcached、fastcgi、scgi、uwsgi在后端失败时的重试次数 [supertcy]
*   Feature: tfs模块在RcServer心跳时汇报访问统计 [zhcn381]
*   Feature: if指令支持比较数值大小：'>'、'<'、'>='、'<=' [flygoast]
*   Feature: 健康检查模块支持长连接检查 [lilbedwin]
*   Feature: trim模块支持SSI和ESI的注释 [taoyuanyuan]
*   Feature: expires_by_types指令支持使用通配符，例如'text/*'匹配子类型 [zhcn381]
*   Feature: 增加$base64_decode_变量前缀，支持计算指定变量的base64解压结果 [yzprofile]
*   Feature: 增加$md5_encode_变量前缀，支持计算指定变量的md5哈希 [yzprofile]
*   Feature: 增加$time_http变量，支持按http格式输出当前时间 [flygoast]
*   Feature: 增加$full_request变量，取得原始的请求url，包括协议类型和域名 [yzprofile]
*   Feature: 增加$escape_uri_变量前缀，支持对指定变量进行url转义 [yzprofile]
*   Feature: 增加$raw_uri变量，支持取得不含参数的原始uri [flygoast]
*   Feature: 支持按微秒记录子请求的请求时间 [jinglong]
*   Feature: 增加API，支持对url进行base64编码 [lilbedwin]
*   Change: 合并nginx-1.4.4版本的修改 [cfsego]
*   Change: 修改stub_status模块，不对子请求进行统计 [jinglong]
*   Bugfix: 修正footer模块，不处理含有Content-Encoding头的响应 [yaoweibin]
*   Bugfix: 修正client_body_postpone_size指令设置为0时出现的问题 [yaoweibin]
*   Bugfix: 修正Lua模块编译时出现警告 [diwayou]


#### Tengine-1.5.2 [2013-11-22]

*   Security: 修复CVE-2013-4547安全漏洞
*   Bugfix: 修复limit_req模块中nodelay无效的问题 [cfsego]
*   Bugfix: 修复trim模块在替换javascript异常的问题 [taoyuanyuan]


#### Tengine-1.5.1 [2013-08-29]

*   Feature: 增加retry_cached_connection指令，可以关闭对后端长连接的无条件重试 [yaoweibin]
*   Feature: sysguard模块的sysguard_load指令中加入ncpu参数 [yzprofile]
*   Bugfix：修复referer模块在https协议时正则匹配失效的问题 [lilbedwin]
*   Bugfix：修复trim模块可能产生0长度块的问题 [taoyuanyuan]
*   Bugfix：修复在使用--without-dso选项时出现的编译错误 [zhuzhaoyuan]
*   Bugfix：修复两个编译警告 [zzjin, diwayou]


#### Tengine-1.5.0 [2013-07-31]

*   Feature: 增加DSO（动态模块加载）兼容性校验机制 [monadbobo]
*   Feature: 增加了请求体不缓存到磁盘的机制，HTTP代理和FastCGI模块收到部分请求体即可以转发给后端服务器 [yaoweibin]
*   Feature: 增加了trim模块，该模块可以自动删除HTML页面中无意义的空白符和注释，减小页面的大小 [taoyuanyuan]
*   Feature: 加入accept filter机制，支持在连接接收以后进行过滤处理 [yzprofile]
*   Feature: 现在server_tag指令可以改变默认错误页面的服务器标识 [zhuzhaoyuan]
*   Bugfix：修复access_log指令中buffer参数失效的问题 [cfsego]
*   Bugfix：修复session_sticky模块在某些情况下没有发出session cookie的问题 [dinic]


#### Tengine-1.4.6 [2013-05-14]

*   Bugifx：合并nginx-1.2.9的更新，修正CVE-2013-2070带来的安全问题。
    该安全问题在1.4.0以后版本开始出现 [yaoweibin]


#### Tengine-1.4.5 [2013-05-01]

*   Feature：增加一致性hash模块，可以为后端服务器提供一致性hash的负载均衡方法 [dinic]
*   Feature：通过keepalive_timeout指令可以设置后端keepalive连接的超时时间 [jinglong]
*   Feature：加入所有模块静态编译或者所有模块动态编译的编译选项 [monadbobo]
*   Change：更新Lua模块至0.7.19 [jinglong]
*   Change：合并Nginx-1.2.8的更新 [yaoweibin]
*   Bugfix：修正syslog和upstream_check模块在GCC-4.4.5上的编译警告 [magicbear]


#### Tengine-1.4.4 [2013-03-21]

*   Feature：增加session_sticky模块，可以为客户端和后端服务器提供会话保持功能 [dinic]
*   Feature：sysguard模块增加空闲内存监控功能 [lifeibo]
*   Feature：geoip模块增加对地区数据库的支持 [jasonlfunk]
*   Feature：log_empty_request指令增加对408响应的空请求支持 [yaoweibin]
*   Change：合并Nginx-1.2.5至Nginx-1.2.7的更新 [cfsego]
*   Change：默认关闭CPU亲缘性 [cfsego]
*   Bugfix：修正在Solaris 11上sysguard和upstream_check模块编译出错的问题 [lifeibo, yaoweibin]
*   Bugfix：修正TFS模块返回值可能错误的问题 [zhcn381]
*   Bugfix: 修正TFS模块上传大文件可能出错的问题 [zhcn381]


#### Tengine-1.4.3 [2013-01-21]

*   Feature：增加TFS模块，可以通过RESTful接口与TFS分布式文件系统通信 [zhcn381, monadbobo]
*   Feature：增加$sent_cookie_XXX系列变量，可以获取响应中Set-Cookie头的cookie值 [skoo87]
*   Feature：syslog指令的发送地址支持域名 [cfsego]
*   Change：upstream块中的server指令增加id属性 [yaoweibin]
*   Bugfix：DSO模块修正reload时可能失败的问题 [monadbobo]
*   Bugfix：修复upstream_check模块当超时时间长于检查时间可能导致段错误的问题 [yaoweibin]
*   Bugfix：修复user_agent模块在请求缺少User-Agent头会段错误的问题 [dinic]
*   Bugfix：修复sysguard模块在Mac OS下面不能工作的问题 [lizi]


#### Tengine-1.4.2 [2012-11-22]

*   Feature：增加--dso-tool-path配置选项，可以选择dso_tool脚本的安装目录 [monadbobo]
*   Feature：增加$unix_time变量，表示当前的时间戳秒数 [yaoweibin]
*   Feature：Makefile中增加test命令以便运行测试用例 [yaoweibin]
*   Feature：sysguard模块可在location里面配置 [lifeibo]
*   Change：合并Nginx-1.2.4和Nginx-1.2.5的更新 [zhuzhaoyuan]
*   Change：增加对input_filter函数返回值的检查，防止第三方模块调用出错 [cfsego]
*   Bugfix：修复limit_req指令不能使用4个参数的问题，感谢LazyZhu的报告 [monadbobo]
*   Bugfix：修复在cygwin下面编译sysinfo文件出错的问题，感谢Cao Peiran的报告 [lifeibo]
*   Bugfix：修复user-agent模块安装时需要拷贝browsers配置文件的问题，感谢Jianbin Xiao的报告 [monadbobo]
*   Bugfix：修复DSO模块RPM打包安装目录出错的问题，感谢Jianbin Xiao和Ren Xiaolei的报告 [monadbobo]


#### Tengine-1.4.1 [2012-10-10]

*   Feature： 添加jemalloc库的支持 [fanjizhao]
*   Feature： 加入$dollar变量, 它的值就是美元符号 [zhuzhaoyuan]
*   Feature： 为worker_cpu_affinity指令加入off选项 [cfsego]
*   Change： 当工作进程异常退出以后，新进程不会绑定CPU亲缘性 [cfsego]
*   Bugfix: 修正在Mac OS操作系统下，Lua模块与LuaJIT动态编译时出现的错误 [monadbobo]
*   Bugfix: 修正动态编译第三方filter模块时出现的模块执行顺序错误 [monadbobo]


#### Tengine-1.4.0 [2012-09-05]

*   Feature： 增加动态模块加载支持（DSO），要添加一个模块不再需要重新编译tengine了 [monadbobo]
*   Feature： 更新Lua模块到最新的稳定版本 [chaoslawful, agentzh, jinglong]
*   Feature： 为健康检查模块增加json和csv格式的输出 [yaoweibin]
*   Feature： 增加log_empty_request指令，可以用来关掉空请求日志——那些连接了但没发数据的连接 [zhuzhaoyuan]
*   Feature： 给concat模块增加concat_delimiter指令，设置文件间的间隔内容 [dinic]
*   Feature： 增加concat_ignore_file_error指令并允许concat的语法更宽松 [dinic]
*   Feature： 给error_page指令增加default选项，以恢复所有的错误页面为默认值 [jinglong]
*   Feature： 给proc模块增加priority指令，可设置proc进程的优先级 [yzprofile]
*   Feature： 给proc模块增加delay_start指令，可设置延迟加载时间 [yzprofile]
*   Change： 集成最新nginx稳定版本1.2.3的内容 [zhuzhaoyuan]
*   Bugfix： 修正一个geo模块设了range但是没有默认值时产生的段错误问题 [yzprofile]
*   Bugfix： 修正一个proc模块的空指针问题 [yzprofile]
*   Bugfix： 修正一个健康检查模块的socket泄漏问题 [yaoweibin]
*   Bugfix： 修正limit_req模块的若干问题 [monadbobo]
*   Bugfix： 修正若干日志输出类型错误的问题 [yaoweibin]
*   Bugfix： 修正perl模块和proc一起打开的一个编译错误 [yzprofile]


#### Tengine-1.3.0 [2012-05-25]

*   Feature：加入Lua模块，可以在配置中使用Lua语言 [chaoslawful, agentzh]
*   Feature：加入procs模块，可以更方便的开启独立进程 [yzprofile]
*   Change：user_agent模块中参数nongreedy改名为greedy [dinic]
*   Bugfix：修复syslog指令中因为指针未初始化引起的段错误 [cfsego]
*   Bugfix：修复syslog指令打开--with-ipv6选项引起的编译错误 [cfsego]


#### Tengine-1.2.5 [2012-05-09]

*   Feature：增加upstream_check模块，对后端服务器做主动健康检查，以自动的下线失效的服务器 [yaoweibin]
*   Feature：允许syslog输出日志时指定程序的标识（program identifier） [cfsego]
*   Change：合并nginx-1.0.14至nginx-1.0.15之间的修改 [zhuzhaoyuan]
*   Change：将accept_mutex_delay的默认值从500毫秒更改为100毫秒以提高性能 [zhuzhaoyuan]
*   Bugfix：修复syslog的一个在后端服务器连接不上导致端错误的bug [cfsego]
*   Bugfix：修复access_log可能和buffer参数冲突的bug [cfsego]


#### Tengine-1.2.4 [2012-03-30]

*   Feature：增加user_agent模块 [dinic]
*   Feature：增加log_escape指令 [agentzh, skoo87]
*   Change：合并nginx-1.0.12至nginx-1.0.14之间的修改 [zhuzhaoyuan]
*   Bugfix：修复limit_req模块的一个bug [liseen.wan]
*   Bugfix：修复subrequest的一个bug [lifeibo]


#### Tengine-1.2.3 [2012-02-27]

*   Feature：增加request_time_cache指令，用来控制是否启用精确的响应时间 [yzprofile]
*   Feature：增加slice模块，获得一个文件的一个片段，可以添加头和尾 [zhuzhaoyuan]
*   Change：合并nginx-1.0.11至nginx-1.0.12之间的修改 [zhuzhaoyuan]
*   Change：去掉无用的user-agent判断 [zhuzhaoyuan]
*   Bugfix：修复upstream中的一个process_header的bug [lifeibo]
*   Bugfix：修复expires_by_types的一个bug [lifeibo]


#### Tengine-1.2.2 [2012-01-11]

*   Feature：增加input body filter机制 [cfsego]
*   Feature：对mail部分支持ssl的dialog [cfsego]
*   Change：合并进nginx-1.0.10至nginx-1.0.11之间的修改 [zhuzhaoyuan]
*   Change：默认关掉lingering_close [zhuzhaoyuan]
*   Bugfix：修正日志管道时的bug [cfsego]
*   Bugfix：修正limit_req的forbid_action无效的bug [monadbobo]
*   Bugfix: 修正backtrace模块backtrace_max_stack_size的问题 [monadbobo]
*   Bugfix：修正内容为空footer模块输出不正确的问题 [dinic]
*   Bugfix：修正syslog时hostname最后一个字母丢失的问题 [cfsego]


#### Tengine-1.2.1 [2011-12-06]

*   Bugfix：修正默认错误日志和访问日志不存在时启动报错的bug [yzprofile]


#### Tengine-1.2.0 [2011-11-29]

*   Feature：错误日志和访问日志支持输出到syslog [cfsego]
*   Feature：错误日志和访问日志支持输出到管道的方式 [cfsego]
*   Feature：增加realloc相关的API，包括内存池 [gongyuan]
*   Feature：HTTP日志支持更多的有关时间的变量 [skoo87]
*   Feature：增加backtrace模块，在coredump时输出调用栈 [monadbobo]
*   Feature：limit_req功能增强，增加白名单，可以有多个条件 [monadbobo]
*   Feature：sysguard模块，load和内存占用偏高时进行保护 [lifeibo]
*   Feature：增加API（ngx_http_header_in/ngx_http_header_out），用来取输入和输出的HTTP头信息 [lifeibo]
*   Feature：增加两个变量$request_time_msec和$request_time_usec，分别是相应时间的毫秒表示和微秒表示 [jinglong]
*   Feature：增加footer模块，可以在HTML末尾添加内容（支持变量） [yunxing]
*   Feature：增加变量$conn_requests，记录当前request是连接上的第几个 [lieyuan]
*   Feature：增加变量$host_comment，插入注释功能，以说明哪台机器产生的请求 [yunxing]
*   Feature：访问日志增加ratio参数，抽样功能，可以减少日志的记录量 [cfsego]
*   Feature：增加server_admin、server_info指令，出错信息提示，更友好的错误页面 [lieyuan]
*   Feature：增加命令行参数-d，把配置文件的内容全部打印出来 [piaoliang]
*   Feature：增加指令expires_by_types，可以根据types来设置超时 [lifeibo]
*   Feature：增加命令行参数-l，可以列出所有的directives [dinic]
*   Feature：增加ngx_atoll的api，可以将字符串转换成64位整数，支持32位与64位系统 [lifeibo]
*   Feature：status line（302，405）现在采用RFC 2616的标准 [zhuzhaoyuan]
*   Feature：ngx_escape_uri/ngx_unescape_uri现在支持PHP/Java的编解码格式 [zhuzhaoyuan]
*   Feature：配置文件include多个文件时按照字母顺序进行包含 [zhuzhaoyuan]
*   Feature：error_page指令增强，支持default，可以把把上一级设置的error_page重新设定 [zhuzhaoyuan]
*   Feature：增加对每请求的响应时间的统计（cacti，tsar） [jinglong]
*   Feature：增加指令server_tag，更强大的控制HTTP服务器的Server头是否显示以及内容是什么 [jinglong]
*   Feature：自动调整worker进程的数目和绑定CPU亲缘性 [cfsego]
*   Feature：增加指令ssl_pass_phrase_dialog，SSL对key进行加密功能 [cfsego]
*   Feature：增加-s选项的start参数 [zhuzhaoyuan]
*   Feature：增加-m选项，可以把已编译的模块列出来 [zhuzhaoyuan]
*   Change：更改msie_padding的默认值为关掉 [zhuzhaoyuan]
*   Bugfix：修复open_file_cache在已经检测到缓存文件发生变化后，仍然返回过时的文件状态信息的问题 [cfsego]
*   Bugfix：修复upsteam在subrequest in memory且keepalive时会导致timeout的bug [lifeibo]
*   Bugfix：修复$sent_http_connection和$sent_http_keep_alive记录不正确的问题 [zhongsheng]
*   Bugfix：修正error_page不能发现重复的code的问题，不能正常继承上一级设置的问题 [zhuzhaoyuan]
*   Bugfix：修正Nginx在处理FastCGI时有重复HTTP头会core dump的bug [monadbobo]
*   Bugfix：修正Nginx对CPU亲缘性设置不正确的bug [cfsego]