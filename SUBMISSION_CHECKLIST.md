# X / Twitter MCP Directory Submission Checklist

## Metadata

- Registry name: `com.52choujiang/x-insights`
- Future registry name: `com.socialdatax/x-insights`
- Local metadata version: `0.1.4`
- Endpoint: `https://mcp.socialdatax.com/x/mcp`
- Auth: `Authorization: Bearer <SOCIALDATAX_API_KEY>`
- Website and API Key access: <https://socialdatax.com/ai?from=github>
- Transport: hosted `streamable-http`; command/stdio fallback uses `mcp-remote`
- License: MIT for public documentation and configuration examples only
- Product: `SocialDataX` / `社媒数据助手`
- 21 tools are listed in `server-card.json`; all three user-replies entry points returned five replies during authenticated production checks on 2026-10-16.

## Safety and publication checks

- No real API Key, private backend code, production configuration, internal sample, or account data is present.
- `server-card.json` and `registry/x/server.json` use public capability version `0.1.4` and the same endpoint.
- Hosted `0.1.4` with 21 tools was verified after deployment on 2026-10-16. Official Registry `0.1.4` was separately verified active/latest on the same day. Three user-replies entry points, continuation and HTTP returned nonempty results.
- The hosted card must expose `x_search_users`, `x_search_suggestions`, `x_search_posts`, `x_get_post_detail_by_post_url`, `x_get_post_comments_by_post_url`, `x_get_user_info_by_profile_url`, `x_submit_video_speech_text_by_post_url`, `x_submit_video_speech_text_by_post_id`, and `x_get_video_speech_text_job`.
- Search and list calls pass the opaque `page_token` returned by the service for continuation.
- `examples/codex_config.toml` uses `bearer_token_env_var = "SOCIALDATAX_API_KEY"`.
- `examples/cursor_mcp.json` uses the remote URL and `${env:SOCIALDATAX_API_KEY}`.
- `mcp.json` and `examples/claude_desktop_config.json` are explicit `mcp-remote` fallbacks.
- Validate JSON and the official Registry file before submission; do not treat a hosted server card as a Registry publication.

## Required files

`README.md`, `LICENSE`, `server-card.json`, `mcp.json`, `glama.json`, all files under `examples/`, and `assets/logo.png`.
