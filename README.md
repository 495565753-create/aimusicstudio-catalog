# 灵感音乐在线曲库

`feed.json` 是「灵感音乐」iPhone App 的在线目录。App 打开或手动刷新后读取它，无需更新 App。音频由 HTTPS 链接分段在线播放，不要求先下载整首歌。

首批 170 首来自 [Angelware Research 的 MiniMax Music 3.0 Research Collection](https://huggingface.co/datasets/AngelSoftware/minimax-music-3-dataset)，原始音频、歌词和每首的 AI 生成元数据均在该数据集内。发布者声明 [CC BY 4.0](https://huggingface.co/datasets/AngelSoftware/minimax-music-3-dataset/blob/main/LICENSE.md)；每条曲目保留来源、授权、作者署名及元数据链接。这里的歌曲属于开放 AI 曲库，没有单曲热度榜，因此不标记为热门歌曲。分类为流行、电子、爵士蓝调、世界民谣、古典、摇滚实验。

发布前运行 App 工程中的 `scripts/check_catalog.py`。该脚本检验必填字段和新增歌曲数；音频链接应额外抽检 HTTP Range 206。iOS 后台目录刷新由系统决定，不能保证准点；手动刷新可即时获取新目录。

曲目字段：`id`、`title`、`artist`、`audioURL`、`artworkURL`（可为 null）、`sourceURL`、`aiEvidenceURL`、`lyrics`、`rights`、`popularity`、`category`、`style`、`publishedAt`。时间使用不带小数秒的 ISO 8601 UTC 格式。每日本机 ACE-Step 歌曲的 MP3 和生成来源元数据放在 `audio/YYYY-MM-DD/`，通过 GitHub Raw 可直接播放，归类为「每日新歌」。
