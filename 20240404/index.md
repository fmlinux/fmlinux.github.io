# 今日开源新闻汇总 2024-4-4
## 1.
Ubuntu 24.04 beta 版本原定于明天发布，但由于 XZ 安全问题，出于谨慎考虑，决定推迟一周以重建软件包。
<br>
Canonical 决定在为 xz-utils 软件包构建了受损的 XZ 代码后，重建 Ubuntu 24.04（Noble Numbat）的所有二进制包。虽然没有迹象表明其他软件包也受到影响，但出于谨慎，他们在编译恶意 XZ 包后，决定重建所有构建中的二进制文件。
<br>
![图片暂时迷路了！！:(](img/1.png)
<br>
由于重建软件包需要时间，Ubuntu 24.04 beta 版本的发布日期已从 4 月 4 日推迟到 4 月 11 日。
<br>
Ubuntu 24.04 Beta 延迟通知今天已发布到 Ubuntu Discourse。
<br>
官方的 Ubuntu 24.04 LTS 版本发布日期仍然预定于 4 月 25 日。
<br>
## 2.
由于 XZ 安全问题和恶意代码的远程代码执行风险，更多开源项目出于谨慎正在重新评估对 XZ 的依赖。最新采取行动的是 Fwupd Linux 固件更新工具和 LVFS，现在将优先选择 Zstd 压缩而不是 XZ。
<br>
Fwupd 依赖 XZ 压缩其大型 XML 负载，以加快网络下载速度并节省 CDN 资源。XZ 提供了比之前使用的 Gzip 更好的压缩效果。但鉴于对 XZ 项目的担忧，Richard Hughes 现在改用 Zstd。
<br>
![图片暂时迷路了！！:(](img/2.png)
<br>
Zstd 不仅更值得信赖，而且压缩后的元数据比 XZ 小约 3%，解压数据的速度也更快。
<br>
这一变更将应用于下周发布的 Fwupd 版本。有关 Fwupd 从 XZ 切换到 Zstd 的更多详情，请参阅[此博客文章](https://blogs.gnome.org/hughsie/2024/04/03/fwupd-and-xz-metadata/)。
<br>
## 3.
Sound Open Firmware 2.9 版本已发布，这个开源项目提供音频 DSP 固件基础设施和相应的 SDK。这项最初由 Intel 启动的工作，旨在开放更多的音频硬件固件，现已发展成为一个多供应商项目，AMD 和 Mediatek 等公司也围绕这个声音固件基础设施、音频驱动等参与其中。
<br>
在 Sound Open Firmware 2.9 中，Aria、Mixin/Mixout 和 DRC 的音频模块进行了“重大”性能优化。发布说明并未详细说明这些重大性能优化的具体内容。
<br>
![图片暂时迷路了！！:(](img/3.png)
<br>
Sound Open Firmware 2.9 还增强了其可加载模块支持，更多组件已迁移到 SOF 模块 API，并且修复了许多错误。
<br>
Sound Open Firmware 2.9 版本还为 Intel 和 NXP 硬件带来了新的拓扑结构。在 Intel 方面，最近有很多工作是关于 SOF 对 Lunar Lake (LNL) 平台支持的完善。
<br>
有关 Sound Open Firmware 2.9 版本的下载和更多详情，请通过 GitHub 查看。
<br>
## 4.
Valve的开源Linux图形驱动团队的Samuel Pitoiset已经在RADV Vulkan驱动中为Vulkan VK_EXT_device_address_binding_report扩展提供了支持，该扩展将包含在Mesa 24.1中。
<br>
VK_EXT_device_address_binding_report扩展最初在Vulkan 1.3.230中添加，它允许应用程序跟踪GPU虚拟地址空间的区域绑定，以便将这些区域与特定的Vulkan对象关联起来。能够将GPU出错的地址追溯到一个Vulkan对象，这在调试中非常有帮助。
<br>
![图片暂时迷路了！！:(](img/4.png)
<br>
Pitoiset在为Mesa RADV驱动配置VK_EXT_device_address_binding_report支持时，简单地总结道： 
<br>
*“对于调试GPU挂起非常有用。”*
<br>
这次合并今天已经进入Mesa Git，为本季度的Mesa 24.1稳定版本发布前的GPU调试提供帮助。RADV是第一个支持此VK_EXT_device_address_binding_report扩展的Mesa Vulkan驱动。
<br>
## 5.
David Malcolm的Red Hat编译器团队发布了他的年度博客文章，总结了即将发布的GCC 14稳定编译器版本中的静态分析改进。
<br>
Malcolm继续在GNU编译器集合的静态分析器支持（-fanalyzer）方面进行工作，并在这一领域取得了更多的增强。例如，GCC 14增加了一个新的“-Wanalyzer-infinite-loop”选项，尝试检测发生的简单无限循环案例。
<br>
在GCC 13的越界警告基础上，GCC 14编译器带来了缓冲区溢出的改进可视化。Malcolm设计了一些不错的基于文本的图表，更好地显示缓冲区溢出警告，以便开发者更容易理解问题。以下是David Malcolm分享的两个改进的ASCII艺术示例，用于可视化缓冲区溢出：
<br>
![图片暂时迷路了！！:(](img/5-1.png)
<br>
![图片暂时迷路了！！:(](img/5-2.png)
<br>
GCC 14分析器还改进了对C字符串操作的分析支持，现在通过-fanalyzer启用了新的基于污点的警告等。
<br>
稳定的GCC 14.1编译器版本预计在未来几周内发布。更多关于GCC 14静态分析器改进的详情，请访问Red Hat开发者博客。
<br>
## 6.
去年，X.Org Server默认禁用了字节交换客户端，因为它是X.Org/XWayland代码库中一个大而已知的攻击面。今天公开的四个新CVE中有三个就是关于字节交换代码的，这进一步证明了这一点。
<br>
字节交换客户端支持是围绕不同CPU字节序的X.Org/XWayland客户端能够连接到X.Org Server。如今，不同的CPU字节序并不常见，去年字节交换客户端支持在没有太多争议的情况下被安全禁用。今天公开的三个CVE涉及ProcXIGetSelectedEvents、ProcXIPassiveGrabDevice、ProcAppleDRICreatePixmap中的堆缓冲区过度读取/数据泄露以及由于字节交换处理而造成的问题。
<br>
![图片暂时迷路了！！:(](img/6.png)
<br>
今天提出的第四个问题是ProcRenderAddGlyphs中的使用后自由问题。
<br>
XWayland 23.2.5和X.Org Server 21.1.12今天发布，用于修复这四个最新的安全问题。详情请参阅今天的安全通告。
<br>
## 7.
荷兰的PC供应商NovaCustom专注于隐私/安全意识硬件和用户自由，宣布推出了V54和V56笔记本电脑。这些新款笔记本电脑搭载了Intel Core Ultra “Meteor Lake” SoCs，自称是世界上最快的Coreboot笔记本电脑。
<br>
NovaCustom V54是一款14英寸的Meteor Lake笔记本电脑，起价为1,420欧元，而V56是一款16英寸的Meteor Lake笔记本电脑，起价为1,460欧元。两款型号都使用了Dasharo版本的Coreboot。与最近的Intel CPU上的Dasharo/Coreboot一样，仍然涉及到FSP的固件二进制文件，但至少使用Coreboot比通常使用的专有供应商BIOS/固件更开放。这些基于Coreboot的Meteor Lake笔记本电脑确实增加了对Intel Boot Guard启动完整性功能的支持，供有兴趣的人使用。
<br>
很高兴看到更多由新的Intel Core Ultra “Meteor Lake” SoCs提供动力的Coreboot设备，它们的集成Arc Graphics特别好。NovaCustom V54/V56可以配置高达96GB的RAM，还有可选的NVIDIA GeForce RTX图形处理器，供那些不想利用Arc Graphics的用户使用。这些笔记本电脑有双M.2 PCIe 4.0 NVMe SSD插槽，电池续航时间长达8小时，以及比早期NovaCustom笔记本电脑更多的更新。
<br>
希望了解更多关于这些新的基于Intel Meteor Lake Coreboot的笔记本电脑的信息，可以在NovaCustom.com上找到所有V54和V56的详细信息。
<br>
![图片暂时迷路了！！:(](img/7.png)
<br>
## 8.
Google开源博客今天宣布了Jpegli，这是一个JPEG编码库，用于编码/解码，同时保持与JPEG的向后兼容性，同时为高质量JPEG压缩提供大约35%的压缩比改进。
<br>
Jpegli旨在成为一个远比传统JPEG处理更高效、更快的JPEG编码库。Jpegli的编码和解码符合原始JPEG标准，压缩图像应该更清晰，有更少的伪影，性能非常快，与libjpeg-turbo和MozJPEG等相媲美，并且支持每个组件10+位的编码。
<br>
Google博客文章解释了Jpegli的工作原理：
<br>
*“Jpegli通过使用许多新技术来减少噪点和提高图像质量；主要是从JPEG XL参考实现中的自适应量化启发式，改进的量化矩阵选择，精确计算中间结果，并有可能使用更高级的色彩空间。所有这些新方法都经过精心设计，使用传统的8位JPEG形式，因此新压缩的图像与现有的JPEG查看器兼容，如浏览器、图像处理软件等。”*
<br>
Google统计数据显示，Jpegli可以比传统的JPEG编解码器多压缩35%的高质量图像。目前，Jpegli代码至少存在于libjxl（JPEG-XL库）存储库中。
<br>
## 9.
著名的Linux内核维护者Greg Kroah-Hartman今天宣布Linux 6.7内核系列的生命周期（EOL）结束，敦促用户尽快升级到最新的Linux 6.8内核。
<br>
Linux内核6.7由Linus Torvalds于2024年1月7日发布，引入了诸如bcachefs文件系统等激动人心的新功能，这是一个为基于Linux的操作系统设计的写时复制（COW）文件系统，旨在与Btrfs和ZFS文件系统提供的现代功能竞争。
<br>
Linux 6.7还引入了对NVIDIA的GSP固件的支持，在Nouveau开源图形驱动程序中，为Btrfs文件系统引入了新功能，改进了EXT4文件系统，增加了一系列网络增强功能，以及众多新的和更新的驱动程序以更好地支持硬件。
<br>
经过仅仅十二次维护更新后，Linux 6.7内核系列现在被标记为EOL（生命周期结束），这意味着它将不再接收错误和安全修复。现在敦促使用Linux内核6.7的用户升级到Linux内核6.8版本。
<br>
*"请注意，这是最后发布的6.7.y内核。这个分支现在已经结束生命周期。请此时转移到6.8.y分支，"Greg Kroah-Hartman在Linux 6.7.12的邮件列表公告中说，这是该系列的最后一次维护更新。*
<br>
Linux内核6.8于2024年3月10日上个月发布，引入了诸如LAM（线性地址掩码）虚拟化支持KVM，新的Intel Xe DRM驱动程序，对CephFS的fscrypt支持，多尺寸THP（透明巨页）sysfs接口等新功能。
<br>
Linux 6.8已经为各种流行的GNU/Linux发行版提供动力，如Arch Linux和openSUSE Tumbleweed，并将成为即将发布的Fedora Linux 40和Ubuntu 24.04 LTS版本的默认内核。
<br>
Linux内核6.8今天也更新到了6.8.3版本，这将很快进入流行的GNU/Linux发行版的稳定软件仓库。Linux内核6.8.3包括相当多的变化，有4772次插入和2551次删除，在481个改变的文件中，因此这是一个强烈推荐的更新。
<br>
然而，我应该警告你，虽然Linux 6.8带来了前沿功能，但它也将是短暂的，只支持几个月。因此，如果你正在寻找内核的长期支持，你应该考虑转移到许多LTS内核系列之一，Linux 6.6 LTS是最新的，将支持到2026年12月。
<br>
