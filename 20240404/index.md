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
