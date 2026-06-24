
去，这工具直接把那些恶心人的视频下载网站全给端了。

你懂的那种网站——点一下下载按钮，弹出三个广告，跳转两次，最后给你塞个病毒。用一次恶心一次，但又不得不用。

现在不用忍了。

这个叫 ReClip 的东西，开源、免费、自托管，没有任何商业模式，没有付费版，没有追加销售，没有遥测，你的机器，你的数据，就这么纯粹。

功能上也不含糊：

1️⃣ 支持 YouTube、TikTok、Instagram、X 在内的 1000+ 网站，底层跑的是 yt-dlp，基本你能想到的平台都覆盖了

2️⃣ 下载前可以选分辨率，要 MP4 还是 MP3 随你

3️⃣ 支持批量下载，一次贴多个链接，还自动去重，不用你手动整理

4️⃣ 纯 Web UI，任何浏览器打开就能用，干净得像一张白纸

技术上更绝，整个项目就 Python + Flask 后端约 150 行代码，前端是原生 HTML/CSS/JS，没有任何框架，没有构建步骤，只有两个依赖：Flask 和 yt-dlp。整个项目一眼就能审计完，没有任何藏猫腻的空间。

部署也极简，有 brew 的话一条命令搞定，喜欢 Docker 也是一行命令跑起来，打开 localhost:8899 就能用。

🔗 : github.com/averygan/reclip

说真的，这种项目才是开源该有的样子。不靠你的注意力赚钱，不靠你的数据赚钱，就是一个纯粹好用的工具。


# ReClip

A self-hosted, open-source video and audio downloader with a clean web UI. Paste links from YouTube, TikTok, Instagram, Twitter/X, and 1000+ other sites — download as MP4 or MP3.

![Python](https://img.shields.io/badge/python-3.8+-blue)
![License](https://img.shields.io/badge/license-MIT-green)

https://github.com/user-attachments/assets/419d3e50-c933-444b-8cab-a9724986ba05

![ReClip MP3 Mode](assets/preview-mp3.png)

## Features

- Download videos from 1000+ supported sites (via [yt-dlp](https://github.com/yt-dlp/yt-dlp))
- MP4 video or MP3 audio extraction
- Quality/resolution picker
- Bulk downloads — paste multiple URLs at once
- Automatic URL deduplication
- Clean, responsive UI — no frameworks, no build step
- Single Python file backend (~150 lines)

## Quick Start

```bash
brew install yt-dlp ffmpeg    # or apt install ffmpeg && pip install yt-dlp
git clone https://github.com/averygan/reclip.git
cd reclip
./reclip.sh
```

Open **http://localhost:8899**.

Or with Docker:

```bash
docker build -t reclip . && docker run -p 8899:8899 reclip
```

## Usage

1. Paste one or more video URLs into the input box
2. Choose **MP4** (video) or **MP3** (audio)
3. Click **Fetch** to load video info and thumbnails
4. Select quality/resolution if available
5. Click **Download** on individual videos, or **Download All**

## Supported Sites

Anything [yt-dlp supports](https://github.com/yt-dlp/yt-dlp/blob/master/supportedsites.md), including:

YouTube, TikTok, Instagram, Twitter/X, Reddit, Facebook, Vimeo, Twitch, Dailymotion, SoundCloud, Loom, Streamable, Pinterest, Tumblr, Threads, LinkedIn, and many more.

## Stack

- **Backend:** Python + Flask (~150 lines)
- **Frontend:** Vanilla HTML/CSS/JS (single file, no build step)
- **Download engine:** [yt-dlp](https://github.com/yt-dlp/yt-dlp) + [ffmpeg](https://ffmpeg.org/)
- **Dependencies:** 2 (Flask, yt-dlp)

## Disclaimer

This tool is intended for personal use only. Please respect copyright laws and the terms of service of the platforms you download from. The developers are not responsible for any misuse of this tool.

## License

[MIT](LICENSE)
