# Cross-Platform Trend Scout  -  Your AI Eyes Across Every Social Platform

An AI skill for [Sai](https://simular.ai/sai) that researches any idea, topic, or trend across 6 major platforms simultaneously. Find what's already viral, how top creators execute, what audiences love or hate, and what gaps exist for you to exploit.

> **Most AI agents are basically blind.** They can't see YouTube, can't browse TikTok, can't scroll Reddit. Sai is different  -  it operates inside a real browser with your real sessions. Log in once, and Sai sees everything you can. No API keys, no OAuth pain, no 403s.

## What It Does

Tell Sai a topic  -  a content idea, product concept, or market trend  -  and it goes to **X, Threads, LinkedIn, TikTok, YouTube, and Reddit** to find:

- 🔥 **Viral content**  -  What's blowing up right now?
- 📊 **Engagement patterns**  -  What formats, hooks, and angles work best?
- 👥 **Top creators**  -  Who's dominating this space?
- 💬 **Audience sentiment**  -  What do people love? What do they hate?
- 🗺️ **Competitive landscape**  -  Who are the existing players?
- 💡 **Content gaps**  -  What's NOT being said that should be?

Then it compiles everything into a structured **Trend Report** with a heat map, cross-platform comparison, and actionable recommendations.

## Example Prompts

```
"Research if AI slides tools have traction on social media"
"What's going viral about remote work tools right now?"
"I want to launch a productivity app  -  what are people saying about this space?"
"Compare how 'AI coding assistants' performs on TikTok vs YouTube vs Reddit"
"Find top-performing posts about meal prep AI across all platforms"
```

## Sample Output: Trend Heat Map

| Platform | Volume | Engagement | Sentiment | Score |
|----------|--------|------------|-----------|-------|
| YouTube  | 🔥 Very High | 🔥 Very High | 👍 Positive | 9/10 |
| Reddit   | 🔥 High | 🔥 High | 🤔 Mixed | 8/10 |
| X/Twitter | 📈 Medium | 📈 Medium | 👍 Positive | 7/10 |
| TikTok   | 🔥 High | 🔥 High | 👍 Positive | 8/10 |
| LinkedIn | 📉 Low | 📈 Medium | 👍 Positive | 5/10 |
| Threads  | 📉 Low | 📉 Low | 👍 Positive | 3/10 |

## How It Works

### 1. You provide a topic
A keyword, phrase, or question  -  as simple as "AI presentation tools" or as specific as "best CRM for solopreneurs 2026."

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
- **Trend Heat Map**  -  Volume, engagement, and sentiment across all platforms
- **Top Viral Posts**  -  Best-performing content with analysis of why it worked
- **Audience Breakdown**  -  Who's talking, what they want, what language they use
- **Competitive Landscape**  -  Existing players mapped by tier
- **Content Gaps & Opportunities**  -  What's NOT being covered
- **Actionable Recommendations**  -  Should you pursue this? Where? How?

### 4. Export options
- 📝 **In-chat report**  -  Structured markdown with tables and insights
- 📊 **Google Sheet**  -  Platform-by-platform data with overview dashboard
- 📄 **Google Doc**  -  Full research report for sharing

## Safety & Anti-Ban Measures

This skill is designed to protect your accounts:

- ✅ **Random delays** between every action (3-8 seconds)
- ✅ **Platform-specific rate limits** (e.g., max 3 searches on LinkedIn per session)
- ✅ **Read-only operation**  -  never likes, comments, follows, or interacts
- ✅ **Human-like scrolling**  -  2-4 scrolls per page with natural pauses
- ✅ **Varied search queries**  -  rephrases across platforms to avoid detection
- ✅ **CAPTCHA detection**  -  stops immediately and reports if any warning appears
- ✅ **Session time cap**  -  stays under 45 minutes total

## Platform-Specific Rate Limits

| Platform | Max Searches | Max Profile Visits | Notes |
|----------|-------------|-------------------|-------|
| X/Twitter | 40 | 30 | Most lenient |
| YouTube | Unlimited | Unlimited | Google is generous |
| Reddit | 50 page loads |  -  | Don't hammer |
| LinkedIn | 20 | 15 | ⚠️ Most aggressive detection |
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

- [Access Sai  -  Your Agentic AI Coworker](https://simular.ai/sai)
- Log into target platforms in your Sai VM (one-time setup)
- Google account connected (optional, for Sheet/Doc export)

## Why Sai, Not Just ChatGPT?

| | ChatGPT / Other AI | Sai |
|---|---|---|
| **Platform access** | ❌ Can't browse social media | ✅ Sees everything you can |
| **Real-time data** | ❌ Knowledge cutoff | ✅ Live search results |
| **Engagement metrics** | ❌ No access | ✅ Reads likes, views, comments |
| **Multi-platform** | ❌ One at a time, manually | ✅ 6 platforms, one command |
| **Export** | ❌ Copy-paste | ✅ Google Sheets/Docs |
| **Recurring** | ❌ Manual every time | ✅ Automated weekly workflows |

---

*Built for [Sai](https://simular.ai/sai) by Simular  -  the Autonomous Computer Company.*
