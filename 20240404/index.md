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
