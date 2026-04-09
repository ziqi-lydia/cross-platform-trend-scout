---
name: cross-platform-trend-scout
description: Research any idea, topic, or trend across X, Threads, LinkedIn, TikTok, YouTube, and Reddit simultaneously. Discover viral content, engagement patterns, top creators, and audience sentiment — then compile a structured research report with actionable recommendations.
---

# Cross-Platform Trend Scout

Research any idea (content concept, product idea, market trend) across 6 major platforms simultaneously. Find what's already viral, how top creators execute, what audiences love or hate, and what gaps exist for you to exploit.

**Sai's unfair advantage:** Unlike blind API-based agents that can't see most platforms, Sai operates inside a real browser with real sessions. If you're logged in, Sai can see everything you can — no API keys, no OAuth pain, no 403s. Just log into each platform once in your VM, and Sai handles the rest.

## When to Use
- "Research if [topic] has traction on social media"
- "What's going viral about [product/niche] right now?"
- "I have a content idea about [X] — is anyone else doing this?"
- "Find top-performing posts about [keyword] across all platforms"
- "I want to launch [product] — what are people saying about this space?"
- "Compare how [topic] performs on TikTok vs YouTube vs Reddit"

## Required Context (ask if not provided)
- **Research topic**: The idea, keyword, or trend to investigate (1-3 keywords or a short phrase)
- **Research goal**: Content ideation? Product validation? Competitive research? Trend sizing?
- **Platforms**: Which to search (default: all 6). User can exclude any.
- **Time window**: Last 7 days, 30 days, 90 days? (default: last 30 days)
- **Language**: English, Chinese, both? (default: English)
- **Output format**: In-chat report, Google Sheet, Google Doc, or all?

## ⚠️ Safety & Anti-Ban Rules (CRITICAL — follow strictly)

These rules exist to protect the user's accounts. Violating them risks temporary or permanent bans.

### Pacing & Rate Limits
- **Random delays between every action**: `await page.wait({ waitTime: 3 + Math.random() * 5 })` (3-8 seconds)
- **Between platform switches**: Wait 10-20 seconds before opening the next platform
- **Between search result clicks**: Wait 5-10 seconds
- **Maximum actions per platform per session**:
  - X/Twitter: 40 searches + 30 profile visits
  - LinkedIn: 20 searches + 15 profile visits  
  - TikTok: 30 searches + 25 video views
  - YouTube: No practical limit (Google is lenient)
  - Reddit: 50 page loads (generous but don't hammer)
  - Threads: 25 searches + 20 profile visits
- **Total session length**: Keep under 45 minutes. If research requires more, split into 2 sessions.

### Behavioral Safety
- **Read-only operation.** NEVER like, comment, follow, share, repost, or interact with any content.
- **No rapid-fire scrolling.** Scroll like a human: 2-4 scroll actions per page, with 2-3 second pauses.
- **No downloading or saving media** (videos, images) from any platform — only text metadata.
- **Don't visit the same profile more than twice** in one session.
- **Vary search query phrasing** — don't search the exact same string on multiple platforms. Rephrase naturally.
- **If any CAPTCHA or "unusual activity" warning appears**: STOP immediately. Report to user. Do NOT retry.

### Data Collection Ethics
- Only collect publicly visible information (post text, engagement counts, usernames, post URLs)
- Do NOT collect or store email addresses, phone numbers, or private account details
- If a profile is private/locked, skip it — do not attempt to access

## Platform Search Strategies

### 📱 Platform 1: X (Twitter)

**Why X first:** Fastest pulse on real-time trends. High signal-to-noise ratio for tech, business, and cultural trends.

```javascript
// Step 1: Open X search with the research topic
var xPage = await browser.newtab("https://x.com/search?q=" + encodeURIComponent("[topic]") + "&src=typed_query&f=top")
await xPage.wait({ waitTime: 3 + Math.random() * 4 })
var xSnap = await xPage.snapshot()
```

**Collect from top results (first 10-15 posts):**
```javascript
var xFindings = {
  platform: "X (Twitter)",
  query: "[topic]",
  topPosts: [
    {
      author: "@handle (Display Name)",
      followerEstimate: "10K-50K",  // if visible
      date: "Mar 15, 2026",
      content: "First 280 chars of the post...",
      engagement: { likes: 0, reposts: 0, replies: 0, bookmarks: 0, views: 0 },
      mediaType: "text | image | video | thread | link",
      sentiment: "positive | negative | neutral | mixed",
      postUrl: "https://x.com/...",
      keyInsight: "What makes this post notable"
    }
  ],
  trendSignals: {
    totalPostsEstimate: "~500 in last 30 days",
    engagementRange: "10-5,000 likes",
    topHashtags: [],
    dominantSentiment: "positive",
    audienceType: "developers | marketers | consumers | mixed"
  }
}
```

**Advanced X searches to try (pick 2-3 relevant ones):**
```javascript
// High-engagement posts only
"[topic] min_faves:100"

// Exclude retweets for original takes
"[topic] -filter:retweets"

// Recent only (if time-sensitive)
"[topic] since:2026-03-01"

// Video content (often higher engagement)
"[topic] filter:videos"

// Conversations (find debates & discussions)
"[topic] min_replies:10"
```

**Wait before moving to next platform:**
```javascript
await xPage.wait({ waitTime: 10 + Math.random() * 10 })
```

---

### 🧵 Platform 2: Threads

**Why Threads:** Growing rapidly, especially for lifestyle/creator/brand content. Less noise than X.

```javascript
var threadsPage = await browser.newtab("https://www.threads.net/search?q=" + encodeURIComponent("[topic]") + "&serp_type=default")
await threadsPage.wait({ waitTime: 4 + Math.random() * 4 })
var threadsSnap = await threadsPage.snapshot()
```

**Collect from top 8-12 results:**
```javascript
var threadsFindings = {
  platform: "Threads",
  query: "[topic]",
  topPosts: [
    {
      author: "@handle",
      date: "...",
      content: "...",
      engagement: { likes: 0, replies: 0, reposts: 0 },
      mediaType: "text | image | carousel | video",
      sentiment: "...",
      postUrl: "https://www.threads.net/...",
      keyInsight: "..."
    }
  ],
  trendSignals: {
    volumeEstimate: "low | medium | high",
    contentStyle: "casual conversations | hot takes | brand marketing | educational",
    audienceType: "..."
  }
}
```

**Wait before next platform:**
```javascript
await threadsPage.wait({ waitTime: 10 + Math.random() * 10 })
```

---

### 💼 Platform 3: LinkedIn

**Why LinkedIn:** Best for B2B signals, professional sentiment, and thought leadership content.

```javascript
var liPage = await browser.newtab("https://www.linkedin.com/search/results/content/?keywords=" + encodeURIComponent("[topic]") + "&datePosted=%22past-month%22&sortBy=%22date_posted%22")
await liPage.wait({ waitTime: 5 + Math.random() * 5 })
var liSnap = await liPage.snapshot()
```

**Collect from top 8-10 posts:**
```javascript
var linkedinFindings = {
  platform: "LinkedIn",
  query: "[topic]",
  topPosts: [
    {
      author: "Name (Title at Company)",
      date: "...",
      content: "First 300 chars...",
      engagement: { likes: 0, comments: 0, reposts: 0 },
      postType: "text | article | carousel | video | poll | document",
      sentiment: "...",
      postUrl: "https://www.linkedin.com/feed/update/...",
      keyInsight: "..."
    }
  ],
  trendSignals: {
    professionalInterest: "high | medium | low",
    dominantAngle: "educational | promotional | thought leadership | hiring",
    industryVerticals: [],
    notableVoices: []
  }
}
```

**LinkedIn safety note:** LinkedIn is the most aggressive at detecting automation. Extra caution:
- Do NOT switch between "Content" and "People" search rapidly
- Maximum 3 searches per session on LinkedIn
- Do NOT click into individual profiles from search results (read from the feed only)

**Wait before next platform:**
```javascript
await liPage.wait({ waitTime: 15 + Math.random() * 10 })
```

---

### 🎵 Platform 4: TikTok

**Why TikTok:** Pulse of consumer trends, Gen Z sentiment, and viral content formats. Massive discovery engine.

```javascript
var ttPage = await browser.newtab("https://www.tiktok.com/search?q=" + encodeURIComponent("[topic]"))
await ttPage.wait({ waitTime: 5 + Math.random() * 5 })
var ttSnap = await ttPage.snapshot()
```

**Collect from top 10-15 video results:**
```javascript
var tiktokFindings = {
  platform: "TikTok",
  query: "[topic]",
  topVideos: [
    {
      creator: "@handle",
      title: "Video caption/description...",
      views: 0,
      likes: 0,
      comments: 0,
      shares: 0,
      duration: "15s | 30s | 60s | 3min+",
      format: "talking head | text overlay | tutorial | skit | slideshow | voiceover",
      hooks: "First 3 seconds hook description",
      hashtags: [],
      sound: "original | trending sound name",
      videoUrl: "https://www.tiktok.com/...",
      keyInsight: "Why this video worked"
    }
  ],
  trendSignals: {
    totalViewsRange: "1K - 10M+",
    dominantFormat: "...",
    trendingHashtags: [],
    trendingSounds: [],
    contentGaps: "What's NOT being covered that should be",
    audienceAge: "Gen Z | Millennial | Mixed"
  }
}
```

**TikTok-specific tips:**
- Switch to "Top" tab for highest-performing content (not just recent)
- Check "Videos" tab specifically (not "Users" or "Sounds")
- Note the video FORMAT — this is critical for content ideation (talking head? text-on-screen? etc.)
- Do NOT play videos or interact — just read metadata from search results

**Wait before next platform:**
```javascript
await ttPage.wait({ waitTime: 10 + Math.random() * 10 })
```

---

### 🎬 Platform 5: YouTube

**Why YouTube:** Long-form content depth, tutorial/review intent, and Google's second-largest search engine.

```javascript
var ytPage = await browser.newtab("https://www.youtube.com/results?search_query=" + encodeURIComponent("[topic]") + "&sp=CAMSAhAB")
// sp=CAMSAhAB = sort by view count + this month filter
await ytPage.wait({ waitTime: 3 + Math.random() * 3 })
var ytSnap = await ytPage.snapshot()
```

**Collect from top 10-12 results:**
```javascript
var youtubeFindings = {
  platform: "YouTube",
  query: "[topic]",
  topVideos: [
    {
      channel: "Channel Name",
      subscribers: "100K",
      title: "...",
      views: 0,
      publishedDate: "2 weeks ago",
      duration: "12:34",
      format: "tutorial | review | vlog | reaction | listicle | explainer | interview",
      thumbnailStyle: "face + text | product shot | before-after | clickbait",
      likes: null,  // only visible after clicking into video
      comments: null,
      videoUrl: "https://www.youtube.com/watch?v=...",
      keyInsight: "..."
    }
  ],
  trendSignals: {
    viewsRange: "1K - 5M",
    topChannelSizes: [],
    dominantFormat: "...",
    averageDuration: "10-15 min",
    contentAge: "mostly recent | mix | mostly older",
    searchVolumeSuggestions: []  // from YouTube's autocomplete
  }
}
```

**YouTube autocomplete trick (bonus signal):**
```javascript
// Check what YouTube suggests — these are high-volume related queries
await ytPage.goto({ url: "https://www.youtube.com" })
await ytPage.wait({ waitTime: 2 })
// Type query slowly in search box to see autocomplete suggestions
var searchBox = await ytPage.snapshot()
// Find the search input ref and type slowly
await ytPage.type({ ref: "[search_ref]", text: "[topic]" })
await ytPage.wait({ waitTime: 2 })
var suggestions = await ytPage.snapshot()
// Record the autocomplete suggestions — these indicate search demand
```

**Wait before next platform:**
```javascript
await ytPage.wait({ waitTime: 8 + Math.random() * 7 })
```

---

### 💬 Platform 6: Reddit

**Why Reddit:** Unfiltered opinions, detailed discussions, pain points, and product feedback. The "truth layer" of the internet.

```javascript
var redditPage = await browser.newtab("https://www.reddit.com/search/?q=" + encodeURIComponent("[topic]") + "&t=month&sort=top")
await redditPage.wait({ waitTime: 4 + Math.random() * 4 })
var redditSnap = await redditPage.snapshot()
```

**Collect from top 10-15 posts:**
```javascript
var redditFindings = {
  platform: "Reddit",
  query: "[topic]",
  topPosts: [
    {
      subreddit: "r/...",
      title: "...",
      upvotes: 0,
      comments: 0,
      author: "u/...",
      age: "2 days ago",
      flair: "Discussion | Question | Showcase | Rant",
      contentPreview: "First 200 chars...",
      sentiment: "positive | negative | neutral | skeptical | enthusiastic",
      postUrl: "https://www.reddit.com/...",
      keyInsight: "...",
      topComment: "Most upvoted comment and its sentiment"
    }
  ],
  trendSignals: {
    relevantSubreddits: ["r/...", "r/..."],
    dominantSentiment: "...",
    commonPainPoints: [],
    commonPraises: [],
    featureRequests: [],
    competitorMentions: [],
    audienceType: "..."
  }
}
```

**Reddit-specific strategies:**
- Note which SUBREDDITS the topic appears in — this tells you the audience
- Read top comments — Reddit's real value is in the comments, not just posts
- Look for "vs" or "alternative" posts — these reveal competitive landscape
- Search for "[topic] sucks" or "[topic] love" for polarized sentiment

## Cross-Platform Synthesis

After collecting data from all platforms, compile the master analysis:

```javascript
var masterReport = {
  topic: "[research topic]",
  researchDate: new Date().toISOString().slice(0, 10),
  platformsCovered: ["X", "Threads", "LinkedIn", "TikTok", "YouTube", "Reddit"],
  
  // 1. TREND HEAT MAP
  trendHeatMap: {
    X:        { volume: "high|med|low", engagement: "high|med|low", sentiment: "pos|neg|mixed", score: "8/10" },
    Threads:  { volume: "...", engagement: "...", sentiment: "...", score: "..." },
    LinkedIn: { volume: "...", engagement: "...", sentiment: "...", score: "..." },
    TikTok:   { volume: "...", engagement: "...", sentiment: "...", score: "..." },
    YouTube:  { volume: "...", engagement: "...", sentiment: "...", score: "..." },
    Reddit:   { volume: "...", engagement: "...", sentiment: "...", score: "..." }
  },
  
  // 2. TOP PERFORMING CONTENT (across all platforms)
  viralFormula: {
    winningFormats: [
      { format: "...", platforms: ["TikTok", "YouTube"], avgEngagement: "...", example: "..." }
    ],
    winningHooks: [
      "Hook pattern 1: [example]",
      "Hook pattern 2: [example]"
    ],
    winningAngles: [
      "Angle 1: [description] — works on [platforms]",
      "Angle 2: [description] — works on [platforms]"
    ],
    optimalLength: {
      shortForm: "15-30s TikTok, 280-char X, 3-line Threads",
      longForm: "10-15min YouTube, 1500-word LinkedIn article, Reddit deep dive"
    }
  },
  
  // 3. AUDIENCE BREAKDOWN
  audienceMap: {
    demographics: "Who is talking about this?",
    platforms: "Where is the most passionate audience?",
    painPoints: ["Top pain point 1", "Top pain point 2"],
    desires: ["What they wish existed", "Features they want"],
    language: "Key phrases and jargon the audience uses"
  },
  
  // 4. COMPETITIVE LANDSCAPE
  existingPlayers: [
    {
      name: "Creator/Brand name",
      platform: "Primary platform",
      approach: "How they cover this topic",
      strengths: "What they do well",
      weaknesses: "What they miss",
      engagement: "Typical engagement level"
    }
  ],
  
  // 5. CONTENT GAPS & OPPORTUNITIES
  opportunities: [
    {
      gap: "What's NOT being said/made",
      platforms: ["Where this gap exists"],
      difficulty: "easy | medium | hard",
      potentialImpact: "high | medium | low",
      executionIdea: "How you could fill this gap"
    }
  ],
  
  // 6. RECOMMENDATIONS
  recommendations: {
    shouldYouPursueThis: "YES / MAYBE / NO — with reasoning",
    bestPlatforms: ["Ranked by opportunity"],
    contentStrategy: [
      {
        platform: "...",
        format: "...",
        frequency: "...",
        firstPostIdea: "Specific post/video concept"
      }
    ],
    timing: "Is this trending up, peaking, or declining?",
    differentiation: "How to stand out from existing content"
  }
}
```

## Output Formats

### Option A: In-Chat Summary Report
Present findings as a structured markdown report with clear sections, tables, and bullet points.

```
## 🔍 Cross-Platform Trend Report: [Topic]
**Date:** [Date] | **Platforms:** X, Threads, LinkedIn, TikTok, YouTube, Reddit

### 📊 Trend Heat Map
| Platform | Volume | Engagement | Sentiment | Score |
|----------|--------|------------|-----------|-------|
| X        | 🔥 High | 🔥 High   | 👍 Positive | 8/10 |
| TikTok   | 🔥 High | 🔥 High   | 👍 Positive | 9/10 |
| YouTube  | 📈 Med  | 🔥 High   | 👍 Positive | 7/10 |
| Reddit   | 📈 Med  | 📈 Med    | 🤔 Mixed   | 6/10 |
| LinkedIn | 📉 Low  | 📈 Med    | 👍 Positive | 5/10 |
| Threads  | 📉 Low  | 📉 Low    | 👍 Positive | 3/10 |

### 🏆 Top Viral Posts (All Platforms)
1. **[Platform] @handle** — [content summary] — [engagement numbers]
   → Why it worked: [analysis]
...

### 🎯 Opportunities
1. ...

### 📋 Recommended Action Plan
1. ...
```

### Option B: Google Sheet Export
```javascript
var sheet = await google.sheets.createSpreadsheet({
  title: "Trend Scout: [Topic] - " + new Date().toISOString().slice(0, 10),
  sheets: ["Overview", "X", "Threads", "LinkedIn", "TikTok", "YouTube", "Reddit", "Top Content", "Recommendations"]
})

// Overview tab
await google.sheets.updateValues({
  spreadsheetId: sheet.id,
  range: "'Overview'!A1:F8",
  values: [
    ["Platform", "Volume", "Engagement", "Sentiment", "Score", "Best Post URL"],
    ["X", "High", "High", "Positive", "8/10", "..."],
    // ... one row per platform
  ]
})

// Per-platform tabs with detailed post data
// Top Content tab with cross-platform ranking
// Recommendations tab with action items

console.log("Report exported: " + sheet.spreadsheetUrl)
```

### Option C: Google Doc Report
```javascript
var doc = await google.docs.createDocument({ title: "Trend Report: [Topic]" })
await google.docs.batchUpdate({
  documentId: doc.documentId,
  requests: [
    { insertText: { location: { index: 1 }, text: reportMarkdown } }
  ]
})
```

## Execution Order & Time Estimate

| Step | Platform | Est. Time | Actions |
|------|----------|-----------|---------|
| 1 | X | 5-7 min | 2-3 searches, scan top 15 posts |
| 2 | Threads | 3-5 min | 1-2 searches, scan top 10 posts |
| 3 | LinkedIn | 4-6 min | 1-2 searches, scan top 10 posts |
| 4 | TikTok | 5-7 min | 1-2 searches, scan top 15 videos |
| 5 | YouTube | 5-7 min | 1-2 searches + autocomplete, scan 12 videos |
| 6 | Reddit | 4-6 min | 2-3 searches, scan top 15 posts + comments |
| 7 | Synthesis | 3-5 min | Compile cross-platform report |
| **Total** | | **30-45 min** | |

## Error Handling

- **Platform not logged in**: Inform user: "You're not logged into [platform]. I can still search, but results may be limited. Want to log in first, or should I proceed with public-only results?"
- **CAPTCHA / Rate limit**: STOP immediately. Inform user. Suggest waiting 15-30 minutes before retrying that platform.
- **No results found**: Try alternative keyword phrasings. If still nothing, report that the topic has low presence on that platform (which is itself a valuable finding).
- **Platform down / loading error**: Skip and note in report. Move to next platform.

## Recurring Research Setup
For ongoing trend monitoring, suggest:
```
"Want me to run this research weekly? I can track how [topic] trends evolve 
across platforms and flag any viral breakouts or sentiment shifts."
```
If yes, set up a weekly workflow via scheduleWorkflow.
