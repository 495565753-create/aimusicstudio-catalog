# 灵感音乐在线曲库

此仓库向「灵感音乐」iPhone App 提供在线歌曲目录。当前目录为空，尚未接入满足 AI 创作来源、完整歌词、热度数据及流媒体授权要求的曲库。不能把普通歌曲、无歌词歌曲或未获授权的音频/歌词填入本目录。

每次发布前运行 App 工程中的 `scripts/check_catalog.py`，与旧版 `feed.json` 对比，要求至少新增 50 个唯一歌曲 ID。脚本只做技术校验，仍需人工核对版权、AI 来源和热门排名证据。App 打开或用户点击刷新时读取此文件；iOS 后台刷新由系统调度，不能保证准点。

曲目字段：`id`、`title`、`artist`、`audioURL`、`artworkURL`（可为 null）、`sourceURL`、`aiEvidenceURL`、`lyrics`、`rights`、`popularity`、`publishedAt`。时间使用不带小数秒的 ISO 8601 UTC 格式，如 `2026-10-19T00:00:00Z`。
