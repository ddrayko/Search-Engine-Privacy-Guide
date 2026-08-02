# 🔍 Search Engine Privacy Guide

> **Did you know a single Google search reveals a lot about you?** Your query, your IP, your device, your location, your browsing habits, and, over time, a frighteningly accurate profile of who you are. Choose your search engine wisely.

A deep, no-nonsense comparison of search engines through a **privacy-only lens**: jurisdiction, data retention, ad-tracking, index sourcing, fingerprinting exposure, and practical setup guidance.

![Markdown](https://img.shields.io/badge/format-Markdown-blue)
![Privacy](https://img.shields.io/badge/focus-Privacy-success)

---

## 📑 Table of Contents

- [Why This Matters](#-why-this-matters)
- [TL;DR, One Line Per Engine](#-tldr--one-line-per-engine)
- [What a Single Search Actually Reveals](#-what-a-single-search-actually-reveals)
- [Full Comparison Table](#-full-comparison-table)
- [Privacy-Only Ranking](#-privacy-only-ranking-best-to-worst)
- [Key Concepts Explained](#-key-concepts-explained)
- [Threat Models: Who Are You Protecting Against?](#-threat-models-who-are-you-protecting-against)
- [How to Choose Based on Your Use Case](#-how-to-choose-based-on-your-use-case)
- [Practical Setup Notes](#-practical-setup-notes)
- [Self-Hosting SearXNG, Deeper Dive](#-self-hosting-searxng--deeper-dive)
- [Common Mistakes That Undo Your Privacy](#-common-mistakes-that-undo-your-privacy)
- [FAQ](#-faq)
- [Glossary](#-glossary)
- [Sources](#-sources)

---

## 💡 Why This Matters

Search engines occupy a unique position in the privacy landscape: unlike a social network, where you knowingly post content, a search bar receives your **unfiltered intent**, questions you wouldn't ask a friend, symptoms you're worried about, relationships you're questioning, places you're planning to go, things you're planning to buy, people you're researching. It's arguably the most intimate data stream you generate every day, and it's easy to forget that every keystroke on a non-private engine can be logged, timestamped, geolocated, and tied back to you.

A single query rarely feels sensitive. **The pattern over thousands of queries is what builds the profile.**

---

## ⚡ TL;DR, One Line Per Engine

| | Engine | Verdict |
|---|---|---|
| 🥇 | **Self-hosted SearXNG** | The strongest option, you control the server, the logs, and the source engines. No third party profiles you. |
| 🥈 | **Startpage** | Near-Google result quality, but Google never sees who's actually searching. |
| 🥉 | **Mojeek** | Fully independent index, UK-based, genuinely no tracking. |
| | **DuckDuckGo** | Solid mainstream default; Bing-based index; US jurisdiction. |
| | **Brave Search** | Independent index, "private by default," US jurisdiction. |
| | **Qwant** | EU-hosted (France), no persistent tracking, but leans on Bing for part of its index. |
| | **Ecosia** | Eco-focused, Bing-powered, moderate privacy, ad-funded tree planting. |
| | **Yandex** | Large independent index, Russian jurisdiction, significant data collection. |
| | **Google / Bing / Yahoo** | Mainstream engines that build detailed behavioral profiles and track extensively across their ecosystems. |

---

## 🕵️ What a Single Search Actually Reveals

Even one isolated query, sent to a tracking-friendly engine, can expose:

- **Your IP address** → approximate location (city-level or better), your ISP, sometimes your employer or university network
- **Your device fingerprint** → browser version, screen resolution, installed fonts, timezone, language settings, combined, these can uniquely identify a device even without cookies
- **Your account identity** → if you're logged into Google/Microsoft/Yahoo in the same browser session, the query is directly tied to your real name, email, and every other service you use
- **Referrer data** → what page you came from, what you clicked on next
- **Timing patterns** → what time of day/night you search, which correlates with routine, work schedule, sleep habits
- **Intent signals** → health concerns, financial situations, relationship issues, legal questions, political views, sexual orientation, all inferable from search terms over time

None of this requires you to "log in" anywhere. Cookies, IP correlation, and browser fingerprinting alone are often enough to build a persistent profile across sessions, even in so-called "incognito" windows (which only prevent *local* history, not server-side tracking).

---

## 📊 Full Comparison Table

| Engine | Jurisdiction | Result Source | Data Retention / Profiling | Targeted Ads? | Privacy Strengths | Limitations |
|---|---|---|---|---|---|---|
| **SearXNG (self-hosted)** | Wherever you host it | Metasearch aggregator (Google, Bing, Brave, etc., configurable) | No centralized logs if configured correctly; you own and control all logging | No (unless you add your own) | Open source, fully decentralized, no account required, no third-party tracker sees your queries, you choose which upstream engines to query | Requires technical setup and maintenance; result quality depends on your configuration and chosen sources; a *public* SearXNG instance still requires trusting that instance's admin |
| **Startpage** | Netherlands (EU) | Primarily Google results via anonymizing proxy, plus own index | Does not store IP addresses, no account-linked history, no long-term behavioral profile | Contextual ads only, not based on cross-session profiling | Google-quality results without Google ever seeing the requester; strict no-tracking policy; encrypts requests; no persistent tracking cookies | Originally a US company (Ideal Group), now Dutch-owned; structurally dependent on Google's index; optional features (saved settings) can create a semi-persistent identifier if enabled |
| **DuckDuckGo** | United States | Primarily Bing, plus own crawler and other partners | No account-linked history, does not sell personal data, may retain short-lived anonymized logs | Contextual ads based on the search term only, not a long-term profile | Very easy to use, "no tracking" by default, transparent privacy policy, integrated browser and browser extensions available | US jurisdiction (subject to US surveillance law/FISA requests); dependent on Bing's index; "!bang" redirects send queries directly to third-party sites (e.g. Amazon, Wikipedia) which can track you there |
| **Brave Search** | United States | Independent index (Brave's own crawler), supplemented by other sources | Does not collect personal data, no account-linked history, no ad-profiling | Optional ads, not based on long-term behavioral profiling when enabled | "Private by default," genuinely independent of Google/Bing, strong integration with the Brave browser, growing independent index | US jurisdiction; younger/smaller index than Google or Bing; some advanced features (Brave Rewards, sync) are optional but require an account |
| **Mojeek** | United Kingdom | Fully independent index (own crawler, no reliance on Google/Bing) | No tracking, no user profiling, no IP logging tied to identity | No behavioral ad targeting | Genuinely independent crawler (rare among privacy engines), UK-based, transparent no-tracking policy, ad-free option available | Smaller index than Google/Bing means lower result coverage for obscure or long-tail queries; UK jurisdiction (Investigatory Powers Act considerations) |
| **Qwant** | France (EU) | Own index for some categories, Bing for others depending on query type | No IP storage, no account-linked personal history, no persistent tracking cookies | Ads present, in principle contextual rather than heavily profiled | EU-hosted (GDPR-governed), French/European alternative, stated "no tracking" policy, no resale of personal data | Ad-funded business model; partial dependency on Bing undercuts claims of full independence; has had financial and organizational instability over the years |
| **Ecosia** | Germany (EU) | Primarily Bing (with some own-index elements depending on configuration) | Does not sell data, does not build a full advertising profile, but does retain some anonymized logs and may use cookies | Ads present (partially fund tree-planting); limited but non-zero targeting | Eco-oriented business model, transparent about funding, no aggressive profiling comparable to Google | Strong dependency on Bing; some technical data (IP, etc.) passes through Microsoft's infrastructure; privacy protections weaker than Startpage/DDG/Mojeek |
| **Yandex** | Russia | Independent index (large, primarily focused on Russian-language content but global coverage) | Extensive data collection tied to Yandex accounts and services; used for ad personalization | Yes, heavily targeted ads across the Yandex ecosystem | Large independent index (genuine Google/Bing alternative in scale) | Russian jurisdiction with associated legal-access and data-sovereignty concerns; significant data collection; generally not recommended for privacy-focused use |
| **Google** | United States | Own massive index | Builds a highly detailed profile (search history, location, YouTube activity, Gmail metadata where linked, cross-device tracking) | Heavily targeted ads based on your full profile | Best-in-class relevance, deep ecosystem integration | Very poor privacy: extensive tracking, cross-service data correlation, long data retention |
| **Bing** | United States (Microsoft) | Own index | User profiling tied to Microsoft account and browsing activity | Targeted ads based on Microsoft/Windows/Edge profile | Deep integration with Windows, Office, Edge | Significant tracking and profiling, US jurisdiction |
| **Yahoo** | United States | Primarily powered by Bing (via partnership) | Retains logs, builds advertising profiles | Targeted ads | General portal (mail, news, etc.) | Weak privacy; inherits Bing's tracking plus its own Yahoo/Verizon Media layer |

---

## 🏆 Privacy-Only Ranking (Best to Worst)

Ranked purely on privacy protection, not relevance, not ethics/environment, not independence from Big Tech indices.

1. **Self-hosted SearXNG**, No third-party server ever profiles you; you decide which upstream engines to query, and you control every log. The strongest possible setup, especially when combined with a VPN or Tor to also hide your IP from your ISP.

2. **Startpage**, Strict no-tracking policy, no IP storage, no long-term profile, and delivers Google's index without Google ever seeing the actual requester.

3. **Mojeek**, Fully independent crawler with a clean no-tracking policy, one of the very few engines that is both privacy-respecting *and* not dependent on Google/Bing's index.

4. **DuckDuckGo**, Excellent for a mainstream, zero-setup engine: no account required, no data resale, ads not based on a persistent profile. Main caveats are US jurisdiction and Bing dependency.

5. **Brave Search**, "Private by default" with a genuinely independent index and no ad-profiling. Still US-based, but the policy is unambiguous.

6. **Qwant**, EU-hosted (GDPR), no tracking cookies, no data resale, but the ad-funded model and partial Bing dependency put it a notch below Startpage/DDG/Mojeek on strict technical grounds.

7. **Ecosia**, Reasonable privacy stance with an eco-angle, but heavy reliance on Bing and some retained technical data make it less strict than the engines above.

8. **Bing**, Real user profiling and targeted advertising tied to a Microsoft account, though somewhat less aggressive in some respects than Google.

9. **Yahoo**, History of tracking practices, dependent on Bing plus its own ad layer, weak privacy overall.

10. **Yandex**, Large independent index but extensive data collection and a jurisdiction with real data-access concerns.

11. **Google**, The most powerful and relevant engine, but also the one building the most detailed cross-service profile. Weakest privacy posture of the group.

---

## 🧠 Key Concepts Explained

<details>
<summary><strong>What "no tracking" actually means</strong></summary>

<br>

A privacy policy saying "we don't track you" typically covers:
- No persistent unique identifier tied to your searches across sessions
- No IP address stored long-term or linked to a profile
- No sale or sharing of personal data with data brokers
- No behavioral ad targeting based on search history

It usually does **not** mean zero data ever touches a server, most engines still process your query in real time to return results, and may keep short-lived, anonymized logs for abuse prevention or performance tuning.

</details>

<details>
<summary><strong>Metasearch vs. independent index</strong></summary>

<br>

- **Metasearch engines** (SearXNG) don't crawl the web themselves, they query other engines (Google, Bing, Brave, etc.) on your behalf and aggregate results, often stripping identifying details before forwarding the request.
- **Independent index engines** (Google, Bing, Brave, Mojeek, Yandex) run their own web crawlers and maintain their own index, this is expensive and technically hard, which is why very few genuinely independent indices exist.
- Engines like DuckDuckGo, Qwant, Ecosia, and Startpage are **hybrids**: they layer their own privacy technology and/or partial indexing on top of another engine's (usually Bing's or Google's) core index.

</details>

<details>
<summary><strong>Jurisdiction matters</strong></summary>

<br>

Where a company is legally based determines what government data requests it can be compelled to comply with:

- **US-based** (Google, Bing, DuckDuckGo, Brave, Yahoo): subject to US legal processes including national security letters and FISA orders, which can come with gag orders preventing the company from even disclosing the request.
- **EU-based** (Startpage – Netherlands, Qwant – France, Ecosia – Germany): governed by GDPR, which imposes strict data minimization, purpose limitation, and user rights requirements (access, deletion, portability).
- **UK-based** (Mojeek): subject to the Investigatory Powers Act, which has broader surveillance and bulk-collection powers than GDPR-only jurisdictions.
- **Russia-based** (Yandex): subject to Russian data-localization laws and security service access mechanisms (e.g., SORM), a materially different risk profile from Western jurisdictions.
- **Self-hosted**: jurisdiction is wherever *you* host it, a meaningful advantage if you control that choice (e.g., a VPS in a privacy-friendly country, or your own home server behind your own network).

</details>

<details>
<summary><strong>Fingerprinting: the tracking that survives cookies and VPNs</strong></summary>

<br>

Even without cookies or a logged-in account, your browser exposes a combination of characteristics, screen resolution, installed fonts, GPU/canvas rendering quirks, timezone, language, installed extensions, that together form a **fingerprint** unique enough to re-identify you across sessions and even across different IP addresses. A privacy-respecting search engine reduces *server-side* tracking, but doesn't by itself protect against fingerprinting; that requires browser-level hardening (e.g., Firefox with `resistFingerprinting`, or a fingerprint-resistant browser like Tor Browser).

</details>

---

## 🎯 Threat Models: Who Are You Protecting Against?

Not everyone needs the same level of protection. Be honest about your actual threat model, over-engineering your setup can add friction without meaningfully improving your privacy, while under-engineering leaves real gaps.

| Threat Model | Who This Applies To | Recommended Setup |
|---|---|---|
| **Ad companies / data brokers** | Most people who just don't want to be profiled for advertising | DuckDuckGo or Startpage as a browser default, quick win, zero friction |
| **Search engine operator itself** | Anyone who doesn't want a single company (Google especially) building a lifelong behavioral profile | Startpage, Mojeek, or Brave Search, genuine no-tracking policies |
| **Your ISP / network operator** | People on shared, monitored, or untrusted networks (work, school, some countries) | Add a VPN or Tor on top of any privacy engine, the engine alone doesn't hide traffic from your network |
| **Government-level surveillance / legal requests** | Journalists, activists, people in high-risk jurisdictions | Self-hosted SearXNG + Tor, hosted in a jurisdiction outside your threat actor's legal reach |
| **Local device access (someone using your computer)** | Shared devices, family computers | Browser-level private/incognito mode is enough, this is a different problem from server-side tracking entirely |

---

## 🧭 How to Choose Based on Your Use Case

**Maximum privacy, technically comfortable:**
→ **Self-hosted SearXNG**, ideally paired with a VPN or Tor to also hide your IP from your ISP. This is the ceiling for privacy among search options.

**Maximum privacy, simple setup:**
→ **Startpage** (Google-quality results, zero profiling) or **Mojeek** (fully independent, no tracking). Either works well as a browser default with no technical overhead.

**Best mainstream, zero-hassle default:**
→ **DuckDuckGo**, the easiest upgrade path away from Google/Bing/Yahoo with essentially no learning curve.

**You want a European engine specifically:**
→ **Qwant** (France) or **Startpage** (Netherlands) for privacy-first EU options, or **Ecosia** (Germany) if the environmental angle matters to you too.

**You want to avoid Google and Microsoft/Bing indices entirely:**
→ **Brave Search** or **Mojeek** for independent indices, or **SearXNG** configured to query non-Big-Tech sources.

**You just want something better than Google without thinking about it:**
→ **DuckDuckGo** or **Startpage** as your browser's default search engine, already a large privacy improvement over Google/Bing/Yahoo with zero configuration effort.

**You're a developer, researcher, or power user:**
→ **Self-hosted SearXNG** gives you full control over source engines, result caching, and even API-style access for scripting or integration into other tools.

---

## 🛠️ Practical Setup Notes

- **Combine layers**: a privacy-respecting search engine + a privacy-respecting browser (Brave, Firefox with hardening, LibreWolf) + a VPN or Tor addresses different threat vectors (search-engine profiling, browser fingerprinting, ISP/network-level tracking), using just one doesn't cover the others.
- **Public SearXNG instances** (e.g. listed at searx.space) are a middle ground: better than using Google directly, but you're trusting that instance operator's configuration and logging practices, not equivalent to self-hosting.
- **Browser-level defaults**: most browsers let you set a default search engine and even add custom search engines via OpenSearch, useful for quickly switching between Startpage/Mojeek/DDG/your own SearXNG instance depending on context.
- **Logged-in accounts defeat everything**: if you stay logged into a Google or Microsoft account while using a "private" engine in the same browser, cross-site tracking and account-linked identifiers can still tie your activity back to you. Use separate browser profiles or containers if you need a hard separation.

---

## 🐳 Self-Hosting SearXNG, Deeper Dive

For anyone running their own infrastructure (VPS, homelab, Proxmox, Docker host), self-hosting SearXNG is the single highest-leverage move on this list.

### How it works
SearXNG is a **metasearch engine**: it doesn't crawl the web itself. Instead, it forwards your query to a configurable list of upstream engines (Google, Bing, Brave, DuckDuckGo, Wikipedia, Startpage, and dozens more), strips identifying headers/parameters before forwarding, aggregates the results, deduplicates them, and returns a single clean result page, all without any upstream engine ever seeing *you* directly, only the SearXNG server.

### Typical deployment
- Runs as a lightweight **Docker container** (official image available) or as a bare-metal Python/uWSGI service
- Needs a **reverse proxy** (nginx or Caddy) in front of it with HTTPS if exposed to the internet
- Configuration lives in a single `settings.yml` file where you can:
  - Enable or disable individual upstream engines
  - Set result caching behavior
  - Control logging (or disable it entirely)
  - Set rate limits to prevent abuse if publicly exposed
  - Customize the UI theme and default search categories (web, images, news, maps, etc.)

### Why self-hosting beats even the best third-party privacy engine
Every third-party engine, no matter how strict its stated policy, ultimately requires **trust**: you're trusting that Startpage really doesn't log IPs, that Mojeek really doesn't build profiles, that their stated policy matches their actual server-side behavior, and that neither will ever be compelled or compromised into changing that behavior silently. Self-hosting removes that trust requirement entirely, the logs (or absence of them) are provably whatever you configure them to be, because you're the one running the server.

### Trade-offs to be aware of
- You are responsible for **uptime, updates, and security patching** of the instance
- Some upstream engines (notably Google) actively try to detect and block automated/proxied traffic, which can require occasional configuration tuning (rotating user agents, rate limiting) to keep results flowing reliably
- Result quality is only as good as the upstream engines you enable, disabling everything except small independent engines will reduce coverage

---

## ⚠️ Common Mistakes That Undo Your Privacy

- **Using a private search engine but staying logged into Google/Microsoft in the same browser**, account-linked tracking can still follow you.
- **Assuming "incognito mode" hides you from the search engine**, it only prevents local browser history; the server still sees your IP and query exactly as before.
- **Using `!bangs` on DuckDuckGo without realizing they redirect you directly to the target site** (Amazon, YouTube, etc.), which then tracks you exactly as it normally would.
- **Running a public SearXNG instance you don't control and assuming it's equivalent to self-hosting**, you're trusting a stranger's server configuration and logging practices.
- **Ignoring browser fingerprinting**, switching search engines does nothing to stop fingerprint-based tracking across sites; that's a browser-level problem requiring separate hardening.
- **Forgetting the network layer**, a privacy-respecting search engine doesn't hide your traffic from your ISP or network operator; that requires a VPN or Tor on top.

---

## ❓ FAQ

**Is DuckDuckGo actually private, or is that just marketing?**
Its stated policy is genuinely strong (no account-linked history, no data resale, no long-term ad profiling), and it's a real, meaningful upgrade over Google. The caveats are US jurisdiction and dependency on Bing's index for most results.

**Is a VPN enough on its own, without changing my search engine?**
No, a VPN hides your IP/location from the search engine and your ISP, but the search engine itself can still build a profile from your queries, cookies, and account logins regardless of which IP the request came from.

**Does using Tor make any privacy search engine "perfect"?**
It gets very close for network-level anonymity, but Tor doesn't stop an engine from fingerprinting your browser or correlating queries within a single session. Combining Tor with a genuinely no-tracking engine (or self-hosted SearXNG) is about as strong as it gets for most threat models.

**Why isn't Yandex ranked higher despite having its own independent index?**
Index independence is one dimension of "privacy from Big Tech dependency," but it says nothing about *how much data the operator itself collects*. Yandex collects extensively for ad personalization and operates under Russian data-access law, both of which outweigh the benefit of index independence for a privacy-focused ranking.

**Is it worth switching if I "have nothing to hide"?**
Privacy isn't about hiding wrongdoing, it's about controlling who gets to build a profile of your interests, health concerns, finances, and relationships, and who gets to monetize, sell, or be compelled to hand over that profile. The "nothing to hide" framing misses that the value of privacy is about power and control over your own data, not guilt.

---

## 📖 Glossary

| Term | Meaning |
|---|---|
| **Metasearch engine** | An engine that aggregates results from other search engines rather than crawling the web itself (e.g. SearXNG) |
| **Fingerprinting** | Identifying a device/browser via a combination of technical characteristics, without relying on cookies |
| **FISA** | US Foreign Intelligence Surveillance Act, legal basis for certain US government data requests to companies |
| **GDPR** | EU General Data Protection Regulation, strict data protection law governing EU-based companies |
| **SORM** | Russian system for lawful interception of electronic communications by security services |
| **Bang (!bang)** | A DuckDuckGo shortcut that redirects your query directly to another site's own search (e.g. `!w` for Wikipedia) |
| **Anonymizing proxy** | A server that forwards your request to another service without revealing your identity/IP to that service (used by Startpage for Google results) |
| **Data broker** | A company that collects and sells personal data aggregated from multiple sources |

---

## 📚 Sources

- [PrivacyTools.io, Private Search Engines](https://privacytools.io/fr/private-search)
- [Experte.com, Anonymous Search Engines](https://www.experte.com/fr/securite-informatique/moteurs-recherche-anonyme)
- [Panda Security, Best Privacy Search Engines](https://www.pandasecurity.com/fr/mediacenter/les-10-meilleurs-moteurs-de-recherche-pour-la-vie-privee/)
- [BeVisible, Google Alternatives](https://www.bevisible.fr/alternatives-a-google/)
- [Norton, Best Private Search Engines](https://us.norton.com/blog/privacy-tips/best-private-search-engines)

---

**Research:** Perplexity and myself

**Writing:** Claude and myself

**Sentence rephrasing:** Claude

---

*This comparison focuses specifically on privacy, not raw search relevance, ethical business practices, or environmental impact, though those are noted where they intersect with privacy behavior (e.g., ad-funded models).*
