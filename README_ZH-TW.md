# Youtube138 MCP Server

[English](./README_EN.md) | [简体中文](./README.md) | 繁體中文

## 🚀 使用 EMCP 平台快速體驗

**[EMCP](https://sit-emcp.kaleido.guru)** 是一個強大的 MCP 伺服器管理平台，讓您無需手動配置即可快速使用各種 MCP 伺服器！

### 快速開始：

1. 🌐 造訪 **[EMCP 平台](https://sit-emcp.kaleido.guru)**
2. 📝 註冊並登入帳號
3. 🎯 進入 **MCP 廣場**，瀏覽所有可用的 MCP 伺服器
4. 🔍 搜尋或找到本伺服器（`bach-youtube138`）
5. 🎉 點擊 **「安裝 MCP」** 按鈕
6. ✅ 完成！即可在您的應用中使用

### EMCP 平台優勢：

- ✨ **零配置**：無需手動編輯配置檔案
- 🎨 **視覺化管理**：圖形介面輕鬆管理所有 MCP 伺服器
- 🔐 **安全可靠**：統一管理 API 金鑰和認證資訊
- 🚀 **一鍵安裝**：MCP 廣場提供豐富的伺服器選擇
- 📊 **使用統計**：即時查看服務調用情況

立即造訪 **[EMCP 平台](https://sit-emcp.kaleido.guru)** 開始您的 MCP 之旅！


---

## 簡介

這是一個 MCP 伺服器，用於存取 Youtube138 API。

- **PyPI 套件名**: `bach-youtube138`
- **版本**: 2.0.0
- **傳輸協定**: stdio


## 安装

### 从 PyPI 安装:

```bash
pip install bach-youtube138
```

### 从源码安装:

```bash
pip install -e .
```

## 运行

### 方式 1: 使用 uvx（推荐，无需安装）

```bash
# 运行（uvx 会自动安装并运行）
uvx --from bach-youtube138 bach_youtube138

# 或指定版本
uvx --from bach-youtube138@latest bach_youtube138
```

### 方式 2: 直接运行（开发模式）

```bash
python server.py
```

### 方式 3: 安装后作为命令运行

```bash
# 安装
pip install bach-youtube138

# 运行（命令名使用下划线）
bach_youtube138
```

## 配置

### API 認證

此 API 需要認證。請設定環境變數:

```bash
export API_KEY="your_api_key_here"
```

### 環境變數

| 變數名 | 說明 | 必需 |
|--------|------|------|
| `API_KEY` | API 金鑰 | 是 |



### 在 Claude Desktop 中使用

编辑 Claude Desktop 配置文件 `claude_desktop_config.json`:


```json
{
  "mcpServers": {
    "youtube138": {
      "command": "uvx",
      "args": ["--from", "bach-youtube138", "bach_youtube138"],
      "env": {
        "API_KEY": "your_api_key_here"
      }
    }
  }
}
```

**注意**: 請將 `E:\path\to\youtube138\server.py` 替換為實際的伺服器檔案路徑。


## 可用工具

此服务器提供以下工具:


### `auto_complete`

Auto Complete

**端点**: `GET /auto-complete/`


**参数**:

- `q` (string) *必需*: Query for suggestions

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `trending`

Trending

**端点**: `GET /v2/trending`



---


### `home`

Home

**端点**: `GET /home/`


**参数**:

- `cursor` (string): Cursor token

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `search`

Search

**端点**: `GET /search/`


**参数**:

- `q` (string): Search query

- `cursor` (string): Cursor token

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `channel_channels`

Channel Channels

**端点**: `GET /channel/channels/`


**参数**:

- `id` (string): Channel ID

- `filter` (string): Filter key or token, default: all_collections Keys you can enter: all_collections: Returns channel collections subscriptions: Returns subscribed channels or custom collection token

- `cursor` (string): Example value: 

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `channel_search`

Channel Search

**端点**: `GET /channel/search/`


**参数**:

- `id` (string): Channel ID

- `q` (string): Search query

- `cursor` (string): Cursor token

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `channel_playlists`

Channel Playlists

**端点**: `GET /channel/playlists/`


**参数**:

- `id` (string): Channel ID

- `filter` (string): Filter key or token, default: all_collections Keys you can enter: all_collections: Returns playlist collections created_playlists_newest: Returns created playlists (by newest) created_playlists_last_video_added: Returns created playlists (by last video added) saved_playlists: Returns saved playlists or custom collection token

- `cursor` (string): Cursor token

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `channel_details`

Channel Details

**端点**: `GET /channel/details/`


**参数**:

- `id` (string) *必需*: Channel ID or URL e.g. UCJ5v_MCY6GNUBTO8-D3XoAg e.g. https://www.youtube.com/@WWE

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `channel_community`

Channel Community

**端点**: `GET /channel/community/`


**参数**:

- `id` (string): Channel ID

- `cursor` (string): Cursor token



---


### `channel_videos`

Channel Videos

**端点**: `GET /channel/videos/`


**参数**:

- `id` (string): Channel ID

- `filter` (string): Filter key, default: videos_latest Keys you can enter: videos_latest: Returns videos (by latest) streams_latest: Returns live streams (by latest) shorts_latest: Returns short videos (by latest) live_now: Returns current live streams

- `cursor` (string): Cursor token

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `channel_details_v2`

Channel Details (v2)

**端点**: `GET /v2/channel-details`


**参数**:

- `channel_id` (string) *必需*: Channel ID or URL e.g. UCJ5v_MCY6GNUBTO8-D3XoAg e.g. https://www.youtube.com/@WWE

- `hl` (string): Example value: en



---


### `video_comments`

Video Comments

**端点**: `GET /video/comments/`


**参数**:

- `id` (string): Video ID

- `cursor` (string): Cursor token

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `video_related_contents`

Video Related Contents

**端点**: `GET /video/related-contents/`


**参数**:

- `id` (string): Video ID

- `cursor` (string): Cursor token

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `video_streaming_data`

Video Streaming Data

**端点**: `GET /video/streaming-data/`


**参数**:

- `id` (string) *必需*: Video ID



---


### `video_details`

Video Details

**端点**: `GET /video/details/`


**参数**:

- `id` (string) *必需*: Video ID or URL e.g. kJQP7kiw5Fk e.g. https://youtu.be/kJQP7kiw5Fk e.g. https://www.youtube.com/watch?v=kJQP7kiw5Fk

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `video_details_v2`

Video Details (v2)

**端点**: `GET /v2/video-details`


**参数**:

- `video_id` (string) *必需*: Video ID or URL e.g. kJQP7kiw5Fk e.g. https://youtu.be/kJQP7kiw5Fk e.g. https://www.youtube.com/watch?v=kJQP7kiw5Fk

- `hl` (string): Example value: en



---


### `community_post_comments`

Community Post Comments

**端点**: `GET /community-post/comments/`


**参数**:

- `cursor` (string) *必需*: Cursor token You can get it from the Community Post Details endpoint.



---


### `community_post_details`

Community Post Details

**端点**: `GET /community-post/details/`


**参数**:

- `id` (string) *必需*: Community post ID



---


### `playlist_videos`

Playlist Videos

**端点**: `GET /playlist/videos/`


**参数**:

- `id` (string): Playlist ID

- `cursor` (string): Cursor token

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---


### `playlist_details`

Playlist Details

**端点**: `GET /playlist/details/`


**参数**:

- `id` (string) *必需*: Playlist ID

- `hl` (string): Example value: en

- `gl` (string): Example value: US



---



## 技术栈

- **传输协议**: stdio
- **HTTP 客户端**: httpx

## 开发

此伺服器由 [API-to-MCP](https://github.com/BACH-AI-Tools/api-to-mcp) 工具自動生成。

版本: 2.0.0
