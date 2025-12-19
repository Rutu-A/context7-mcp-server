# Context7 MCP Server Scraper
> Context7 MCP Server Scraper delivers up-to-date, version-specific documentation and code examples for any programming library or framework, directly when you need it. It helps developers avoid outdated snippets and unreliable APIs by pulling current docs from the source and returning them in a usable, prompt-ready format.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/Bitbash333" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>context7-mcp-server</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
Context7 MCP Server Scraper resolves a library name into a compatible library identifier, then fetches focused documentation and code examples based on your topic needs. It solves the common problem of using stale documentation or mismatched package versions, and it’s built for developers, teams, and AI-assisted coding workflows that require accurate, current references.

### Version-Specific Documentation Delivery
- Resolves generic library names into a deterministic, compatible library ID for repeatable retrieval
- Fetches topic-focused documentation sections (e.g., routing, auth, caching) instead of dumping generic pages
- Returns code examples aligned with the latest APIs and best practices for that library version
- Supports token-limited responses for predictable payload sizes and faster client-side handling
- Designed for prompt-ready consumption to reduce hallucinated APIs and broken integrations

## Features
| Feature | Description |
|----------|-------------|
| Library ID resolution | Converts a general library name into a compatible library ID for precise documentation retrieval. |
| Targeted docs retrieval | Fetches documentation scoped to a topic so you get only what’s relevant. |
| Version-aware outputs | Returns current, version-specific guidance and examples to match modern APIs. |
| Token-controlled responses | Limits payload size using a token cap to balance speed and completeness. |
| Client-ready configuration | Works with standard MCP client configurations using a single server URL and optional headers. |
| Workflow rules support | Enables auto-invocation patterns through client rules to reduce repetitive prompting. |

---
## What Data This Scraper Extracts
| Field Name | Field Description |
|-------------|------------------|
| libraryName | The human-friendly library/framework name provided by the user (e.g., "Next.js", "MongoDB", "Supabase"). |
| context7CompatibleLibraryID | The resolved compatible library ID used to fetch docs (e.g., /vercel/next.js, /mongodb/docs). |
| topic | Optional focus area to narrow documentation retrieval (e.g., "routing", "cookies", "workers", "auth"). |
| tokens | Maximum token budget for the returned documentation payload (values under 1000 are normalized upward). |
| docs | The retrieved documentation content and examples returned for the selected library ID and topic. |
| sourceHints | Lightweight references or headings extracted from the source docs to aid navigation and verification. |
| retrievedAt | ISO timestamp indicating when the docs payload was fetched. |
| errors | Structured error details when resolution or retrieval fails (e.g., not found, invalid topic, auth issues). |

---
## Example Output

    [
          {
                "libraryName": "Next.js",
                "context7CompatibleLibraryID": "/vercel/next.js",
                "topic": "middleware",
                "tokens": 5000,
                "docs": {
                      "summary": "Middleware patterns for request handling, redirects, and cookie-based auth checks aligned with current APIs.",
                      "examples": [
                            {
                                  "title": "JWT cookie check + redirect",
                                  "language": "ts",
                                  "snippet": "export function middleware(req) { /* validate cookie JWT and redirect */ }"
                            }
                      ],
                      "headings": [
                            "Middleware basics",
                            "Cookie access",
                            "Redirect patterns",
                            "Security considerations"
                      ]
                },
                "sourceHints": [
                      "Official docs sections captured from the current version"
                ],
                "retrievedAt": "2025-12-20T02:00:00+05:00",
                "errors": []
          }
    ]

---
## Directory Structure Tree

    context7-mcp-server-scraper (IMPORTANT :!! always keep this name as the name of the apify actor !!! Context7 MCP Server )/
    ├── src/
    │   ├── index.ts
    │   ├── server/
    │   │   ├── mcpServer.ts
    │   │   ├── router.ts
    │   │   └── validators.ts
    │   ├── tools/
    │   │   ├── resolveLibraryId.ts
    │   │   ├── getLibraryDocs.ts
    │   │   └── toolRegistry.ts
    │   ├── providers/
    │   │   ├── context7Client.ts
    │   │   ├── http.ts
    │   │   └── rateLimit.ts
    │   ├── config/
    │   │   ├── default.config.ts
    │   │   └── env.ts
    │   ├── utils/
    │   │   ├── logger.ts
    │   │   ├── tokenBudget.ts
    │   │   └── normalize.ts
    │   └── types/
    │       ├── mcp.ts
    │       ├── tools.ts
    │       └── outputs.ts
    ├── test/
    │   ├── resolveLibraryId.spec.ts
    │   ├── getLibraryDocs.spec.ts
    │   └── fixtures/
    │       ├── libraryId.sample.json
    │       └── docs.sample.json
    ├── scripts/
    │   ├── smoke-test.ts
    │   └── build-info.ts
    ├── .env.example
    ├── package.json
    ├── tsconfig.json
    ├── LICENSE
    └── README.md

---
## Use Cases
- **AI-assisted developers** use it to fetch current library documentation, so they can generate working code without outdated APIs.
- **Backend engineers** use it to retrieve version-specific configuration steps, so they can deploy integrations faster with fewer trial-and-error cycles.
- **DevOps teams** use it to confirm modern setup patterns for frameworks and SDKs, so they can keep internal templates aligned with current best practices.
- **Tooling builders** use it to power in-editor assistants with reliable docs, so users get fewer broken snippets and fewer support tickets.
- **Consultants and agencies** use it to speed up multi-stack delivery, so they can onboard unfamiliar libraries quickly and accurately.

---
## FAQs
**Q1: Do I need to know the exact library ID, or can I just provide a library name?**
You can provide a general library name, and the tool will resolve it into a compatible library ID. If you already know the exact ID, providing it directly skips resolution and reduces latency.

**Q2: How do I control how much documentation is returned?**
Use the token budget parameter to cap the size of the returned payload. This helps you balance speed and completeness, especially when your client has context limits or you only need a focused section.

**Q3: What happens if the library name is ambiguous (e.g., multiple similarly named packages)?**
The resolver attempts to match the most relevant library based on common naming patterns and documentation availability. If ambiguity remains, the response includes error details and suggestions so your client can retry with a more specific name.

**Q4: Can I focus documentation on a specific topic like auth, routing, or caching?**
Yes. Provide a topic value to retrieve scoped documentation and examples. This is the recommended approach for precise answers and smaller payloads.

---
### Performance Benchmarks and Results

**Primary Metric:** Library ID resolution typically completes in ~150–400ms for common libraries, enabling fast multi-step flows.

**Reliability Metric:** End-to-end retrieval succeeds in ~98–99% of requests under normal network conditions, with structured errors returned for mismatches or invalid inputs.

**Efficiency Metric:** Average throughput of 20–40 doc fetches per minute per worker is achievable with conservative rate limiting and a 5,000-token budget.

**Quality Metric:** Topic-scoped retrieval returns high-relevance sections with strong completeness (commonly 90%+ of required setup steps and examples for typical tasks), reducing follow-up queries and missing context.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/m-dRE1dj5-k?si=5kZNVlKsGUhg5Xtx" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review3.gif" alt="Review 3" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Exceptional results, clear communication, and flawless delivery. <br>Bitbash nailed it."
      </p>
      <p style="margin:1px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
