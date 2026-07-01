---
name: youtube-community-insight-feed
description: Use this skill when the user wants to view the latest YouTube Community post from their saved insight channels, including the original post text, attached images, channel name, post date, and source link. Trigger when the user asks to check, show, browse, collect, or review Community posts from saved YouTube insight channels. Do not use for YouTube video summaries, transcript analysis, channel discovery, or broad content recommendation unless the request specifically involves YouTube Community posts.
---

# YouTube Community Insight Feed

## Purpose

Show the latest YouTube Community post from each saved insight channel, with the original post text, attached images, post date, channel name, and source link.

## Default Channels

Use these saved YouTube insight channels by default:

```text
DEFAULT_CHANNELS:
- https://www.youtube.com/@human_Intelligence_korea
- https://www.youtube.com/@B_ZCF
```

## Workflow

1. Open each saved channel's Community tab and fetch the most recent visible Community post.
2. Collect the channel name, post date or relative time, original post text, attached images, and source URL.
3. Preserve the original meaning of the post; do not summarize unless the user asks for a summary.
4. Present one result per channel in a clear feed format.
5. If a channel has no visible Community post or access fails, report that channel separately with the reason.

## Output

Return results in this format:

```markdown
## Channel Name

Post date:
...

Original post:
...

Images:
- ...

Source:
...
```

When attached images are available, show the image URLs or render the images directly if the environment supports it.

If the post text is very long, provide a concise excerpt and include the source link instead of reproducing excessive text.

## Assumptions

- Show only the latest 1 Community post per saved channel.
- The default channel list is part of this skill and can be edited later.
- The task requires current web access because YouTube Community posts change over time.
- If YouTube blocks access, requires login, hides images, or prevents reliable extraction, report the limitation clearly.
- Focus on Community posts and attached images, not videos, transcripts, shorts, or general channel recommendations.

## Test Prompts

1. Show the latest Community post from each saved YouTube insight channel, including original text and images.
2. Check my default YouTube insight channels and display the newest Community post from each one.
3. Open the saved YouTube channels' Community tabs and show the latest post, attached images, date, and source link.
