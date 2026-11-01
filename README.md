# 憩梦AI播客 · v3 站点预览

本分支把本地已定稿的 v3 播客站点放上来，供人工审阅。它**不是**正式发布，也**不**切换现在的发布入口。

当前 GitHub Pages 仍从默认分支 `main` 的根目录发布，地址是 [https://oycw1688.github.io/qimeng-podcast/](https://oycw1688.github.io/qimeng-podcast/)，没有绑定自定义域名。把本分支合并进 `main` 之前，需要负责人先确认正式发布面是继续用 GitHub Pages，还是改用 `podcast.qidream.cn`。在那之前不要合并。

## 本分支有什么

- 首页 `index.html`：章节播放器。摘要卡片、大标题随章节变化、章节切换、只听本章、逐句文稿、往期列表。
- `covers/`：周一到周日七张封面，播放器按节目日期选色。
- `ep/20261031/`、`ep/20261101/`：每期页面、`episode.json`、对谈脚本 JSON、`transcript.txt`、完整 MP3。
- `feed.xml`：EP.01 与 EP.02。文件里的绝对地址仍是本地定稿时写的 `https://podcast.qidream.cn/...`，这只是稿件内容，不代表已经改了 DNS 或 Pages 源。
- `docs/憩梦AI播客制作发布规范.md`：制作与发布规范。

播放器里的音频、封面、往期链接用相对路径，在本仓库目录里可以直接打开预览。RSS 里的订阅地址和音频外壳地址是绝对地址，指向 `podcast.qidream.cn`。

## 和 main 简易站的路径关系

`main` 上的简易站仍留在 git 历史里。本分支保留这些旧文件，避免已有链接立刻失效：

| 旧路径（main 简易站） | 处理 |
|---|---|
| `episodes/2026-10-31.mp3` | 保留。约 2.4MB、64kbps 单声道、时长约 5 分 6 秒。这是 Pages 上 EP.01 的旧音频。 |
| `cover_small.jpg` | 保留。简易站首页用过。 |
| `cover.jpg`、`.nojekyll` | 保留。 |

新结构以 `ep/YYYYMMDD/` 为准。v3 的 EP.01 是另一条成片，放在 `ep/20261031/qimeng_ai_20261031.mp3`（约 6MB、128kbps 立体声、约 6 分 16 秒），不是把旧文件改个名。EP.02（2026-11-01）只存在于新结构里。

## 故意不放进来的东西

- `.edgeone/`：EdgeOne 部署镜像。放进来容易被当成已经切到 `podcast.qidream.cn`。
- `.env`：空文件，也不入库。
- 不改 DNS，不加 `CNAME`，不改 Pages 的发布分支，不合并进 `main`。

## 审阅时建议看的点

1. 首页和 `ep/20261101/`、`ep/20261031/` 能否播放，章节能否跳转。
2. 七色封面是否按星期对应（周六孔雀青、周日香槟米金）。
3. 合并前是否要改写 `feed.xml` 和页面里的 canonical / RSS 绝对地址。若正式入口仍是 GitHub Pages，这些地址需要先改，否则订阅端会去拉 `podcast.qidream.cn`。
