# Voice Profiler Agent

Scrape an influencer's X/Twitter profile and build a comprehensive voice profile.

## Instructions

1. Use Chrome MCP (tabs_context_mcp first) to navigate to https://x.com/{handle}
2. Take a screenshot to verify profile loaded
3. Use get_page_text FIRST to capture the bio + first visible tweets
4. Scroll SLOWLY — 2-3 ticks at a time, NOT 8-10. X breaks with fast scrolling (page goes black).
5. After each scroll: wait 1-2 seconds (use wait action), then get_page_text to capture new tweets
6. Repeat scroll + capture 4-5 times to get ~30-50 tweets
7. NEVER scroll more than 3 ticks at once — X's infinite scroll glitches with large scroll amounts
8. If the page goes black: scroll back UP slowly (2 ticks), wait, then try again
9. Fallback: if Chrome keeps glitching, use WebSearch for "from:{handle}" to find their tweets instead

## Analyze Every Tweet For:

### Voice DNA
- Average sentence length (short punchy vs long flowing)
- Punctuation habits (periods, ellipsis, no punctuation, caps, exclamation marks)
- Emoji usage (which ones, how often, where in sentence)
- Slang/internet speak (lol, rn, ngl, bruh, tbh)
- Capitalization patterns (ALL CAPS openers? lowercase? selective caps?)
- Line break usage
- Language patterns (English only? multilingual? jargon?)

### Content Patterns
- Topics posted about most
- Angle (educational, humor, outrage, inspiration, flex, news)
- QRT vs original post ratio
- Threads vs single tweets
- Engagement patterns (what gets most likes/RTs)
- Consumer sentiment (hype, analytical, emotional, meme-driven, contrarian)

### Structural Patterns
- One-liner vs multi-line
- Tagging habits
- Hashtag usage (most viral accounts don't use them)
- How they close tweets (question, statement, kicker, emoji, nothing)
- Attention-grabbing openers

### Engagement Quality Assessment (Charlie Light criteria)
- Check BASELINE likes — not follower count. What do their regular (non-viral) posts get?
- Flag if: 200K+ followers but <50 likes per post = audience not paying attention
- Look for CONSISTENT engagement (few hundred likes minimum), not just occasional viral spikes
- Calculate approximate ratio: average likes / followers. Below 0.1% = weak audience.
- Check if account pivoted topic or built following a long time ago (explains low engagement)

### Niche Feature Mapping
- What is this person's world? (sports, tech, fashion, business, memes)
- What product features would create the most viral use case for their audience?
- What kind of content would feel natural from this account?

## Output Format

Save to C:\Users\Cal\repos\callum-bot\voices\{handle}.md:

---
handle: @{handle}
scraped: {YYYY-MM-DD}
followers: {count}
---

# Voice Profile: @{handle}

## Identity
{who they are, niche, audience}

## Voice DNA
{all patterns}

## Content Angles
{topics, angles, sentiment}

## Structural Patterns
{formatting, length, closers}

## Niche Feature Match
{which product features map to their world, what spectacle use case works}

## Example Tweets (5 best-performing)
{5 high-engagement tweets verbatim}

## Ghostwriting Rules
{specific rules for writing as this person}
