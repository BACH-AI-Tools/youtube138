# Youtube138 MCP Server

[English](./README_EN.md) | 简体中文 | [繁體中文](./README_ZH-TW.md)

## 🚀 使用 EMCP 平台快速体验

**[EMCP](https://sit-emcp.kaleido.guru)** 是一个强大的 MCP 服务器管理平台，让您无需手动配置即可快速使用各种 MCP 服务器！

### 快速开始：

1. 🌐 访问 **[EMCP 平台](https://sit-emcp.kaleido.guru)**
2. 📝 注册并登录账号
3. 🎯 进入 **MCP 广场**，浏览所有可用的 MCP 服务器
4. 🔍 搜索或找到本服务器（`bach-youtube138`）
5. 🎉 点击 **"安装 MCP"** 按钮
6. ✅ 完成！即可在您的应用中使用

### EMCP 平台优势：

- ✨ **零配置**：无需手动编辑配置文件
- 🎨 **可视化管理**：图形界面轻松管理所有 MCP 服务器
- 🔐 **安全可靠**：统一管理 API 密钥和认证信息
- 🚀 **一键安装**：MCP 广场提供丰富的服务器选择
- 📊 **使用统计**：实时查看服务调用情况

立即访问 **[EMCP 平台](https://sit-emcp.kaleido.guru)** 开始您的 MCP 之旅！


---

## 简介

这是一个使用 [FastMCP](https://fastmcp.wiki) 自动生成的 MCP 服务器，用于访问 Youtube138 API。

- **PyPI 包名**: `bach-youtube138`
- **版本**: 1.0.0
- **传输协议**: stdio


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

### API 认证

此 API 需要认证。请设置环境变量:

```bash
export API_KEY="your_api_key_here"
```

### 环境变量

| 变量名 | 说明 | 必需 |
|--------|------|------|
| `API_KEY` | API 密钥 | 是 |



### 在 Claude Desktop 中使用

编辑 Claude Desktop 配置文件 `claude_desktop_config.json`:


```json
{
  "mcpServers": {
    "youtube138": {
      "command": "python",
      "args": ["E:\path\to\youtube138\server.py"],
      "env": {
        "API_KEY": "your_api_key_here"
      }
    }
  }
}
```

**注意**: 请将 `E:\path\to\youtube138\server.py` 替换为实际的服务器文件路径。


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

- **FastMCP**: 快速、Pythonic 的 MCP 服务器框架
- **传输协议**: stdio
- **HTTP 客户端**: httpx

## 开发

此服务器由 [API-to-MCP](https://github.com/BACH-AI-Tools/api-to-mcp) 工具自动生成。

版本: 1.0.0
