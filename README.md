# Cross-Platform Trend Scout â€” Your AI Eyes Across Every Social Platform

An AI skill for [Sai](https://simular.ai/sai) that researches any idea, topic, or trend across 6 major platforms simultaneously. Find what's already viral, how top creators execute, what audiences love or hate, and what gaps exist for you to exploit.

> **Most AI agents are basically blind.** They can't see YouTube, can't browse TikTok, can't scroll Reddit. Sai is different â€” it operates inside a real browser with your real sessions. Log in once, and Sai sees everything you can. No API keys, no OAuth pain, no 403s.

## What It Does

Tell Sai a topic â€” a content idea, product concept, or market trend â€” and it goes to **X, Threads, LinkedIn, TikTok, YouTube, and Reddit** to find:

- ðŸ”¥ **Viral content** â€” What's blowing up right now?
- ðŸ“Š **Engagement patterns** â€” What formats, hooks, and angles work best?
- ðŸ‘¥ **Top creators** â€” Who's dominating this space?
- ðŸ’¬ **Audience sentiment** â€” What do people love? What do they hate?
- ðŸ—ºï¸ **Competitive landscape** â€” Who are the existing players?
- ðŸ’¡ **Content gaps** â€” What's NOT being said that should be?

Then it compiles everything into a structured **Trend Report** with a heat map, cross-platform comparison, and actionable recommendations.

## Example Prompts

```
"Research if AI slides tools have traction on social media"
"What's going viral about remote work tools right now?"
"I want to launch a productivity app â€” what are people saying about this space?"
"Compare how 'AI coding assistants' performs on TikTok vs YouTube vs Reddit"
"Find top-performing posts about meal prep AI across all platforms"
```

## Sample Output: Trend Heat Map

| Platform | Volume | Engagement | Sentiment | Score |
|----------|--------|------------|-----------|-------|
| YouTube  | ðŸ”¥ Very High | ðŸ”¥ Very High | ðŸ‘ Positive | 9/10 |
| Reddit   | ðŸ”¥ High | ðŸ”¥ High | ðŸ¤” Mixed | 8/10 |
| X/Twitter | ðŸ“ˆ Medium | ðŸ“ˆ Medium | ðŸ‘ Positive | 7/10 |
| TikTok   | ðŸ”¥ High | ðŸ”¥ High | ðŸ‘ Positive | 8/10 |
| LinkedIn | ðŸ“‰ Low | ðŸ“ˆ Medium | ðŸ‘ Positive | 5/10 |
| Threads  | ðŸ“‰ Low | ðŸ“‰ Low | ðŸ‘ Positive | 3/10 |

## How It Works

### 1. You provide a topic
A keyword, phrase, or question â€” as simple as "AI presentation tools" or as specific as "best CRM for solopreneurs 2026."

### 2. Sai searches all 6 platforms
Each platform gets a tailored search strategy:

| Platform | Why It Matters | What Sai Collects |
|----------|---------------|-------------------|
| **X/Twitter** | Real-time pulse, tech & culture trends | Top posts, engagement metrics, hashtags, sentiment |
| **YouTube** | Long-form depth, tutorial intent, search volume | Videos, view counts, channel sizes, autocomplete suggestions |
| **Reddit** | Unfiltered opinions, pain points, product feedback | Threads, upvotes, comments, subreddit distribution |
| **LinkedIn** | B2B signals, professional sentiment | Posts, industry verticals, enterprise angles |
| **TikTok** | Consumer trends, Gen Z sentiment, viral formats | Videos, views, content formats, trending sounds |
| **Threads** | Lifestyle/creator content, brand marketing | Posts, engagement, content style |

### 3. Cross-platform synthesis
Sai compiles findings into:
- **Trend Heat Map** â€” Volume, engagement, and sentiment across all platforms
- **Top Viral Posts** â€” Best-performing content with analysis of why it worked
- **Audience Breakdown** â€” Who's talking, what they want, what language they use
- **Competitive Landscape** â€” Existing players mapped by tier
- **Content Gaps & Opportunities** â€” What's NOT being covered
- **Actionable Recommendations** â€” Should you pursue this? Where? How?

### 4. Export options
- ðŸ“ **In-chat report** â€” Structured markdown with tables and insights
- ðŸ“Š **Google Sheet** â€” Platform-by-platform data with overview dashboard
- ðŸ“„ **Google Doc** â€” Full research report for sharing

## Safety & Anti-Ban Measures

This skill is designed to protect your accounts:

- âœ… **Random delays** between every action (3-8 seconds)
- âœ… **Platform-specific rate limits** (e.g., max 3 searches on LinkedIn per session)
- âœ… **Read-only operation** â€” never likes, comments, follows, or interacts
- âœ… **Human-like scrolling** â€” 2-4 scrolls per page with natural pauses
- âœ… **Varied search queries** â€” rephrases across platforms to avoid detection
- âœ… **CAPTCHA detection** â€” stops immediately and reports if any warning appears
- âœ… **Session time cap** â€” stays under 45 minutes total

## Platform-Specific Rate Limits

| Platform | Max Searches | Max Profile Visits | Notes |
|----------|-------------|-------------------|-------|
| X/Twitter | 40 | 30 | Most lenient |
| YouTube | Unlimited | Unlimited | Google is generous |
| Reddit | 50 page loads | â€” | Don't hammer |
| LinkedIn | 20 | 15 | âš ï¸ Most aggressive detection |
| TikTok | 30 | 25 | Moderate |
| Threads | 25 | 20 | Moderate |

## Advanced Search Strategies

### X/Twitter
```
"[topic] min_faves:100"          # High-engagement only
"[topic] -filter:retweets"       # Original takes only
"[topic] filter:videos"          # Video content
"[topic] min_replies:10"         # Active discussions
```

### YouTube
- Autocomplete analysis for search demand signals
- Sort by view count + time filter for trending content
- Channel size vs. view count ratio for virality detection

### Reddit
- Subreddit distribution tells you the audience
- Top comments > post content for real sentiment
- "vs" and "alternative" posts reveal competitive landscape
- Sentiment polarity searches: `[topic] sucks` vs `[topic] love`

## Estimated Research Time

| Step | Platform | Time | Actions |
|------|----------|------|---------|
| 1 | X/Twitter | 5-7 min | 2-3 searches, top 15 posts |
| 2 | Threads | 3-5 min | 1-2 searches, top 10 posts |
| 3 | LinkedIn | 4-6 min | 1-2 searches, top 10 posts |
| 4 | TikTok | 5-7 min | 1-2 searches, top 15 videos |
| 5 | YouTube | 5-7 min | 1-2 searches + autocomplete |
| 6 | Reddit | 4-6 min | 2-3 searches, top 15 posts |
| 7 | Synthesis | 3-5 min | Cross-platform report |
| **Total** | | **30-45 min** | |

## Recurring Research

Want to track trends over time? Set up a weekly workflow:

> "Run this research every Monday and flag any viral breakouts or sentiment shifts."

Sai can schedule recurring trend reports via its workflow engine.

## Requirements

- [Access Sai â€” Your Agentic AI Coworker](https://simular.ai/sai)
- Log into target platforms in your Sai VM (one-time setup)
- Google account connected (optional, for Sheet/Doc export)

## Why Sai, Not Just ChatGPT?

| | ChatGPT / Other AI | Sai |
|---|---|---|
| **Platform access** | âŒ Can't browse social media | âœ… Sees everything you can |
| **Real-time data** | âŒ Knowledge cutoff | âœ… Live search results |
| **Engagement metrics** | âŒ No access | âœ… Reads likes, views, comments |
| **Multi-platform** | âŒ One at a time, manually | âœ… 6 platforms, one command |
| **Export** | âŒ Copy-paste | âœ… Google Sheets/Docs |
| **Recurring** | âŒ Manual every time | âœ… Automated weekly workflows |

---

*Built for [Sai](https://simular.ai/sai) by Simular â€” the Autonomous Computer Company.*
