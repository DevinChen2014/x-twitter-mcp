# X / Twitter MCP

This public listing provides connection metadata and client examples for the hosted SocialDataX X / Twitter MCP service. The implementation is privately hosted; this directory contains public connection materials only.

## Service

- Hosted MCP endpoint: `https://mcp.socialdatax.com/x/mcp`
- Hosted transport: `streamable-http`
- Authentication: `Authorization: Bearer <SOCIALDATAX_API_KEY>`
- Product: `SocialDataX` / `社媒数据助手`
- Website and API Key access: <https://socialdatax.com/ai?from=github>
- Registry name: `com.52choujiang/x-insights`
- Future registry name: `com.socialdatax/x-insights`
- Current public capability version: `0.1.3`, 18 tools, including user search; hosted server card and authenticated tools/list verified on 2026-10-08.
- Official Registry: [`0.1.3`](https://registry.modelcontextprotocol.io/v0.1/servers/com.52choujiang%2Fx-insights/versions/0.1.3), verified active and latest on 2026-10-08.

## Scope

Use this service for public X / Twitter post search, user search, post details, first-level comments, comment replies, public user info, user posts, and video speech-to-text. It does not provide account login, posting, editing, liking, commenting, following, or other account actions.

## Tools

| Tool | Purpose |
| --- | --- |
| `socialdatax_get_points_balance` | Query the current API Key account's SocialDataX points balance / 积分余额、剩余积分或点数. |
| `x_search_users` | Search users by name or keyword; continue with `page_token` and the same keyword. |
| `x_search_suggestions` | Get keyword suggestions for post search; no pagination or recommended users. |
| `x_search_posts` | Search public posts; use when a search term is available, and continue with `page_token`. |
| `x_get_post_detail_by_post_id` | Read post details from a post ID. |
| `x_get_post_detail_by_post_url` | Read post details from a post URL. |
| `x_get_post_comments_by_post_id` | Read first-level comments from a post ID. |
| `x_get_post_comments_by_post_url` | Read first-level comments from a post URL. |
| `x_get_post_comment_replies_by_comment_id` | Read replies from a post ID and first-level comment ID. |
| `x_get_user_info_by_user_id` | Read public user info from a user ID. |
| `x_get_user_info_by_username` | Read public user info from a username. |
| `x_get_user_info_by_profile_url` | Read public user info from a profile URL. |
| `x_get_user_posts_by_user_id` | Read public user posts from a user ID. |
| `x_get_user_posts_by_username` | Read public user posts from a username. |
| `x_get_user_posts_by_profile_url` | Read public user posts from a profile URL. |
| `x_submit_video_speech_text_by_post_url` | Submit the current post's first video with an available MP4 variant for speech-to-text by post URL. |
| `x_submit_video_speech_text_by_post_id` | Submit the current post's first video with an available MP4 variant for speech-to-text by post ID. |
| `x_get_video_speech_text_job` | Continue querying the same speech-to-text job ID until terminal. |

When a post ID, post URL, username, or profile URL is already available, use the corresponding detail, comment, user, or user-post tool instead of searching again.

## Quick Start

Use the hosted endpoint directly when the client supports authenticated `streamable-http`:

```json
{
  "mcpServers": {
    "socialdatax-x": {
      "type": "streamable_http",
      "url": "https://mcp.socialdatax.com/x/mcp",
      "headers": {"Authorization": "Bearer <SOCIALDATAX_API_KEY>"}
    }
  }
}
```

For command/stdio-only clients, use `npx -y mcp-remote https://mcp.socialdatax.com/x/mcp --header "Authorization: Bearer <SOCIALDATAX_API_KEY>"`. See the files in [examples](examples/).

Request or manage API access at <https://socialdatax.com/ai?from=github>. Never commit a real API Key.
