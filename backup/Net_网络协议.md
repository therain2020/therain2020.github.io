### 应用层网络协议
- HTTP——Hypertext Transfer Protocol，基于TCP，用于传输超文本和多媒体内容，为Web浏览器和Web服务器之间的通信而设计
- SMTP——Simple Mail Transfer Protocol，基于TCP，用于发送电子邮件，只负责发送
- POP3/IMAP——邮件接收协议，基于TCP，用于电子邮件接收，IMAP比POP3强大，支持邮件搜索、标记、分类、归档等，且可以在多个设备之间同步邮件状态。
- FTP——File Transfer Protocol，基于TCP，用于在计算机之间传输文件，可以屏蔽操作系统和文件存储方式，但不安全，不会加密数据。敏感数据可以用更安全的SFTP传输。
- Telnet——远程登录协议，基于TCP，用于通过一个终端登录到其他服务器，但所有数据以明文形式发送，不安全，逐渐被SSH替代。
- SSH——Secure Shell Protocol，基于TCP协议，通过加密和认证机制实现安全的访问和文件传输等业务
- RTP——Real-time Transport Protocol，基于UCP，也支持TCP。提供了端到端的实时传输数据的功能，但不包含资源预留存，不保证实时传输质量，这些功能由WebRTC实现。
- DNS——Domain Name System，基于UDP，用于解决域名和IP地址的映射问题

### 传输层
- UDP
无连接的，尽最大努力的，简单高效

- TCP
面向连接的，可靠的


###网络层
- IP，TCP/TP协议中最重要的协议之一，属于网络层的协议，主要作用是定义数据包的格式，对数据包进行路由和寻址，以便于它们可以跨网络传播并到达正确的目的地。目前IP协议分为IPv4和IPv6，后者已经被提议取代前者。
- ARP，解决网络层地址和链路层地址之间的转换问题。因为一个IP数据报在物理上传输的过程中，总是需要知道下一跳（物理上的下一个目的地）该去哪里，但IP属于逻辑地址，而MAC地址才是物理地址，ARP协议解决了IP地址转MAC地址的一些问题。
- ICMP——Internet Control Message Protocol，用于传输网络状态和错误消息，进而用于网络诊断和故障排查。例如Ping工具就用了ICMP来测试网络连通性。
- NAT——Network Address Translation，用于内部网到外部网的地址转换过程中，具体的说在局域网（LAN）中，各主机使用同一个局域网（LAN）下的IP地址，但在局域网（WAN）外，广域网（LAN）中，需要一个统一的IP地址来标识该局域网在整个Internet上的位置
- OSPF
- RIP
- BGP
