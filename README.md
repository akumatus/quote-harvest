# Quote Harvest

A daily-growing, bilingual library of lines worth keeping: real quotes with real attributions, plus anonymous lines that genuinely circulate online. Harvested one morning at a time by the routine behind [Spuddy](https://github.com/akumatus/spuddy), a hand-crocheted potato desktop pet who hands you a little card of encouragement.

<!-- stats:start -->
| | English | 中文 |
|---|---:|---:|
| Quotes (attributed) | 1590 | 1015 |
| Lines (anonymous) | 132 | 414 |

Last harvest: 2026-09-26
<!-- stats:end -->

## What's in here

Two pools, two languages, four data files:

| File | What | Shape |
|---|---|---|
| [`data/quotes.en.json`](data/quotes.en.json) · [`data/quotes.zh.json`](data/quotes.zh.json) | Famous quotes with attributions | `[{ "text": "…", "source": "…" }]` |
| [`data/lines.en.json`](data/lines.en.json) · [`data/lines.zh.json`](data/lines.zh.json) | Anonymous internet lines | `["…"]` |

Browseable versions live next to them: [`quotes.en.md`](quotes.en.md), [`quotes.zh.md`](quotes.zh.md), [`lines.en.md`](lines.en.md), [`lines.zh.md`](lines.zh.md). Each day's additions are in [`changelog/`](changelog/).

**Quotes** come from novels, films, series, authors, and the occasional famous speech. Every entry is signed with a specific person or work a reader might actually recognize. Attribution follows common usage, not scholarship: *Gone with the Wind*, not "Margaret Mitchell, 1936, chapter 63".

**Lines** are the ones with no name to sign. They circulate on Tumblr, Instagram, X, 微博, 豆瓣, 小红书, 网易云 and the like, written by internet handles, small bloggers, or nobody knows who. Each was verified to actually circulate on the day it was added. None were written by a model.

## What doesn't get in

- Sourceless "quotes" and shrug labels (Anonymous, Unknown, 网络, 佚名) never enter the quotes pool.
- No proverbs, folk sayings, or classical Chinese: 俗语, 谚语, 古诗词, 文言 are all out.
- No slogans, no political figures, no song lyrics.
- No mutated or apocryphal "famous" quotes. If the person or work can't be confirmed to have said it, the line is dropped, not demoted.
- Nothing composed by the AI doing the harvesting. The routine searches, verifies, and sorts. It does not write.

## How it's updated

A scheduled [Claude Code](https://claude.com/claude-code) routine runs every morning. It hunts candidate lines on the open web, sorts each by provenance (recognizable name → quotes; verified circulating but unsigned → lines; everything else → dropped), appends the survivors to Spuddy's server, then regenerates this repo from the server's full library and pushes. Some days add a dozen lines. Some days add none. That is the point.

Entries are chronological, appended at the end, so `git log -p data/quotes.en.json` reads like a diary.

## Using it

Take the JSON. No API, no rate limit, no sign-up. Text is exactly as it circulates in common usage, so expect the popular wording rather than the critical edition.

Spotted a misattribution, or a line that breaks the rules above? Open an issue. The data files are regenerated from upstream on every run, so fixes are applied there and flow back here.

## 中文说明

这是一个每天增长的中英双语名句库，由桌宠 [Spuddy](https://github.com/akumatus/spuddy) 背后的每日例程自动收集。分两类：

- **名句**（`data/quotes.*.json`）：有真实出处的句子，来自小说、影视、作家与少数演讲，每条署名到一个读者叫得出的人或作品。
- **网络句**（`data/lines.*.json`）：确在网络流传、但没有一个叫得出名字的署名的句子。收录当天经搜索验证确在流传，没有一条是模型写的。

不收：无出处的句子、俗语谚语、古诗词文言、口号、政治人物语录、歌词、改装或伪托的名人名言。数据按收录顺序排列，每天的新增在 `changelog/` 里。发现错误出处或不该收的句子，欢迎开 issue。

## License

The compilation (selection, ordering, formatting, and this repository) is released under [CC0 1.0](LICENSE). Use it however you like, no attribution required. The quoted lines themselves remain the work of their authors and are reproduced here as short excerpts with attribution.
