# 今日开源新闻汇总2024-3-25
## 新闻1
Linux 6.9 版本的 IO_uring 更新在几乎结束的合并窗口期间早期合并。这一轮又为这个精彩且创新的内核特性带来了一些新功能。
<br>
Linux 6.9 的 IO_uring 更新包括对每环 NAPI 的支持、对截断的支持、公开 SQPOLL 利用状态、使 task_work 内部循环更公平、multi-shot修复以及其他各种修复/清理。
<br>
由 Stefan Roesch 长期研究的 NAPI 忙轮询支持已经实现。利用 NAPI 忙轮询时，Stefan 测试的往返时间从 55 微秒降低到 38 微秒。补丁信息中有更多细节，供对这项新 IO_uring 功能感兴趣的人参考。
<br>
IO_uring 的截断（ftruncate）支持允许通过 IO_uring 进行原生截断，因此应用程序不再需要设置自己的线程池或卸载来进行非阻塞截断。
<br>
更多关于 Linux 6.9 的 IO_uring 更新的细节可以通过拉取请求查看，代码已经在今天的 Linux 6.9-rc1 版本发布前进入 Linux Git.
<br>
![图片暂时迷路了！！:(](img/1.png)
## 新闻2
