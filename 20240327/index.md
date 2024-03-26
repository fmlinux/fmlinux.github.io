# 今日开源新闻汇总2024-3-27
## 新闻1
开源的 Panthor DRM 驱动程序支持更新的 Arm Mali GPU，已在 3 月初排队进入 drm-misc-next，准备合并到 Linux 6.9。但最终没有在 Linux 6.9 合并窗口前被拉入 DRM-Next，因此被推迟到 Linux 6.10 周期。不过，本周该驱动程序和其他更改开始为 Linux 6.10 排队。
<br>
首次为 Linux 6.10 准备的 drm-misc-next 拉取已完成。这次拉取使得支持新型 Mali 图形“Gen10”的 Panthor DRM 驱动程序落地，这些图形依赖于命令流前端（CSF）。与此同时，Mesa 24.1 也进行了 Gallium3D 驱动程序的更改，以支持这个新的内核图形驱动程序。Mali GPU 支持也有新的固件要求。
<br>
除了引入 Panthor 驱动程序外，这次 drm-misc-next 拉取还包括改进 TTM 缓冲对象在空闲/繁忙处理中的放置、一个新的 CONFIG_DRM_WERROR 选项用于将 DRM 子系统代码的警告设置为错误，以及其他各种核心改进。较小的直接渲染管理器驱动程序也进行了一些小修复。
<br>
在组织方面，DRM-Misc 现已过渡到使用 GitLab 和 FreeDesktop.org 托管。
<br>
请查看这次拉取，了解初步为 Linux 6.10 准备的 DRM-Misc-Next 材料，预计在今年夏天。
<br>
## 新闻2
![图片暂时迷路了！！:(](img/1.png)
