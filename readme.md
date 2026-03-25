🧠 MASTER PROMPT — AIOps Intelligence Hub (Single-Page HTML)
Use this prompt with Claude Code (claude-code CLI or claude.ai Projects) to generate a world-class, production-ready HTML page.

ROLE & CONTEXT
You are a Senior Frontend Architect with 15 years of experience building enterprise-grade, dark-themed observability UIs for companies like Datadog, Grafana Labs, and New Relic. You specialize in:
Single-file, zero-dependency HTML/CSS/JS applications
Grafana-inspired dark UI design systems with glassmorphism
AIOps and SRE domain knowledge
Accessibility-first (WCAG 2.1 AA), performance-optimized code
Smooth animations, micro-interactions, and scroll-driven effects

TASK
Build a single, self-contained HTML file — aiops-intelligence-hub.html — that serves as the definitive showcase page for the Albertsons Enterprise AIOps Intelligence Suite. This is a premium, story-driven marketing + technical documentation page, NOT a dashboard. Think: Apple product page meets Grafana design system.

DESIGN SYSTEM (MUST FOLLOW EXACTLY)
Color Palette (CSS Custom Properties)
:root {
  /* Brand */
  --albertsons-blue: #0033A0;
  --albertsons-blue-dark: #001f5c;
  --albertsons-blue-light: #0047BB;
  --grafana-orange: #FF7733;
  --grafana-orange-dark: #E65C1A;
  --grafana-red: #E02F44;
  --grafana-green: #73BF69;
  --grafana-yellow: #FADE2A;

  /* Backgrounds */
  --dark-bg: #111217;
  --dark-surface: #1A1D26;
  --dark-elevated: #242933;
  --glass-bg: rgba(26, 29, 38, 0.85);
  --glass-border: rgba(255, 255, 255, 0.12);
  --glass-highlight: rgba(255, 255, 255, 0.05);

  /* Text */
  --text-primary: #F2F3F5;
  --text-secondary: #A9B2C3;
  --text-muted: #6B7280;

  /* Status */
  --success: #52C41A;
  --warning: #FAAD14;
  --danger: #F5222D;
  --info: #1890FF;

  /* Shadows & Glows */
  --shadow-sm: 0 2px 12px rgba(0,0,0,0.4);
  --shadow-md: 0 6px 24px rgba(0,0,0,0.5);
  --shadow-lg: 0 12px 48px rgba(0,0,0,0.6);
  --glow-orange: 0 0 20px rgba(255,119,51,0.3);
  --glow-blue: 0 0 20px rgba(0,51,160,0.3);

  /* Spacing */
  --spacing-xs: 0.5rem;
  --spacing-sm: 1rem;
  --spacing-md: 1.5rem;
  --spacing-lg: 2rem;
  --spacing-xl: 3rem;

  /* Border Radius */
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-xl: 20px;

  /* Transitions */
  --transition-fast: 0.2s ease;
  --transition-base: 0.3s ease;
  --transition-slow: 0.4s ease;
}

Typography
Font: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', Roboto, sans-serif
Hero H1: clamp(2.4rem, 5.5vw, 4rem) — animated gradient text (white → orange → blue)
Section H2: clamp(1.8rem, 3vw, 2.8rem) — white with subtle glow
Card H3: 1.3rem — text-primary
Body: 1rem / 1.7 line-height — text-secondary
Component Library to implement:
Glass Card
.glass-card {
  background: var(--glass-bg);
  border: 1px solid var(--glass-border);
  border-radius: var(--radius-lg);
  backdrop-filter: blur(20px);
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
}
.glass-card:hover {
  border-color: var(--grafana-orange);
  box-shadow: var(--shadow-lg), var(--glow-orange);
  transform: translateY(-4px);
}

Status Badge
.badge { padding: 0.3rem 0.8rem; border-radius: 20px; font-size: 0.78rem; font-weight: 700; }
.badge-success { background: rgba(82,196,26,0.15); color: var(--success); border: 1px solid rgba(82,196,26,0.3); }
.badge-warning { background: rgba(250,173,20,0.15); color: var(--warning); border: 1px solid rgba(250,173,20,0.3); }
.badge-info    { background: rgba(24,144,255,0.15); color: var(--info);    border: 1px solid rgba(24,144,255,0.3); }
.badge-orange  { background: rgba(255,119,51,0.15); color: var(--grafana-orange); border: 1px solid rgba(255,119,51,0.3); }

Section Label
.section-label {
  display: inline-flex; align-items: center; gap: 0.5rem;
  background: rgba(255,119,51,0.12); border: 1px solid rgba(255,119,51,0.3);
  border-radius: 20px; padding: 0.4rem 1rem;
  color: var(--grafana-orange); font-size: 0.8rem; font-weight: 700; letter-spacing: 0.08em; text-transform: uppercase;
}


PAGE ARCHITECTURE — ALL SECTIONS REQUIRED
1. <head> — Complete Meta & SEO
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Albertsons AIOps Intelligence Hub — Enterprise Observability Platform</title>
<meta name="description" content="Six AI-powered capabilities transforming reliability, performance, and incident response across Albertsons' cloud-native infrastructure.">
<meta name="keywords" content="AIOps, SLO, Alert Clustering, Flamegraph AI, Forecasting, RCA, Service Insights, Observability, Grafana, Kubernetes, AKS, GKE, Azure OpenAI">
<meta name="author" content="Albertsons Enterprise Observability Team">
<meta property="og:title" content="Albertsons AIOps Intelligence Hub">
<meta property="og:description" content="AI-powered observability for the modern enterprise">


2. STICKY HEADER / NAV
Logo left: 🔶 icon + "AIOps Hub" + subtitle "Albertsons Enterprise Observability"
Nav links (smooth scroll anchors): Overview · Alert Clustering · Flamegraph AI · Forecasting · RCA Hub · Service Insights · SLO Framework
Right: "🔍 Search" input (filters visible section content on type) + "Open Grafana →" CTA button
On scroll: header gains extra blur + subtle shadow
Mobile: hamburger menu that slides in a drawer
Active nav link highlight: orange underline on current section in view (IntersectionObserver)

3. HERO SECTION
Full-width, animated radial gradient background (blue + orange + purple pulses)
Animated floating particle dots (pure CSS, no canvas)
Eyebrow label: 🧠 AIOps Intelligence Suite
H1: "The Future of Enterprise Observability is Intelligent" — animated gradient text cycling white → orange → blue → white
Subheadline (2-3 sentences): Position the suite as Albertsons' response to the challenge of operating thousands of microservices on AKS — moving from reactive dashboards to predictive, AI-powered operational intelligence
Stats row (animated count-up on scroll into view):
6 AI-Powered Modules
90% Alert Noise Reduction
< 5min MTTR Improvement
99.9% SLO Target Coverage
CTA buttons: Primary "Explore All Capabilities →" (scrolls to overview) + Secondary "View in Grafana"
Scrolling ticker below hero: ALERT CLUSTERING · FLAMEGRAPH AI · METRICS FORECAST · RCA HUB · SERVICE INSIGHTS · ESOB SLO FRAMEWORK ·

4. OVERVIEW / MODULE GRID SECTION (id="overview")
Section label: ⚡ Platform Overview
H2: "Six Capabilities. One Intelligent Platform."
Subtext: Enterprise AIOps built on Google SRE principles — bringing ML, LLM, and predictive analytics into Grafana
6 clickable module cards in a responsive CSS Grid (3-col desktop, 2-col tablet, 1-col mobile):
#
Icon
Module Name
Tagline
Badge
1
🔔
Alert Clustering
Signal Unification Engine
ML-Powered
2
🔥
Flamegraph AI
LLM Performance Diagnosis
GPT-4.1
3
📈
Metrics Forecast
Predictive Time-Series Analytics
Prophet
4
🔍
RCA Hub
Root Cause Intelligence
GA
5
🛡️
Service Insights
SAAFE Prioritization Engine
GA
6
📊
ESOB SLO Framework
Enterprise Reliability Standard
GA

Each card: icon in orange-glow circle, title, badge, 2-sentence tagline, "Learn More →" link. Clicking smooth-scrolls to that module's deep-dive section. Hover: lift + orange border glow.

5. MODULE SECTIONS — DEEP DIVES (One per module)
Each module section MUST follow this pattern:
[Section with alternating layout: text left / visual right, then next module flips to visual left / text right]

- id="[module-slug]"
- Full-bleed dark background with subtle colored ambient glow unique to each module
- Section label with module icon + "MODULE 1 OF 6" etc.
- H2: Module name
- Story paragraph: 2–3 paragraphs telling the AIOps journey (problem → insight → solution)
- Key Benefits: 4–6 icon + title + description items in a 2-column grid
- Architecture/How It Works: numbered step-by-step flow (with connecting lines in CSS)
- Tech Stack pills: e.g., Python · APScheduler · MongoDB · Azure Storage · HDBSCAN · Sentence Transformers
- Visual mockup: ASCII-art-inspired CSS-drawn "terminal" or "dashboard panel" on the opposite side
- "Jump to next module →" link

MODULE 1: Alert Clustering (id="alert-clustering")
Story content:
Open with the problem: "On any given day, our platforms generate thousands of alerts... Most represent the same 2–3 underlying issues."
The insight: "What if we could make alerts understand each other?"
The solution: ML-driven, service-graph-aware intelligence layer
Key Benefits:
🎯 90% Noise Reduction — Transform 1,000 scattered alerts into 10 precise, business-impacting clusters
🔗 Service Graph Awareness — Enriched with topology context before ML even runs
⚡ 5-Minute Cycle — APScheduler continuously processes new Parquet files every 5 minutes
🧠 Semantic Understanding — HDBSCAN + Sentence Transformers group by meaning, not just keywords
📊 Cluster Scoring — ML-ranked clusters drive priority automatically
🚀 Faster RCA — Engineers jump directly to root cause, not symptom storms
How It Works (Numbered Flow):
Alerts Arrive → MongoDB → Azure File Storage (Parquet) → alertsdata/incoming/
Scheduler Wakes → APScheduler runs every 5 minutes, scans new files
Enrichment → Service graph topology, severity, cluster/namespace context added
Embedding → Sentence Transformers convert alert text to semantic vectors
Clustering → HDBSCAN groups semantically similar alerts into clusters
Scoring → ML scores each cluster by impact, severity, blast radius
Output → Engineers receive ranked, enriched, deduplicated incident clusters
Tech Stack: Python · APScheduler · MongoDB · Azure File Storage · Apache Parquet · HDBSCAN · Sentence Transformers · Grafana
Visual mockup (CSS terminal): Show a mock "CLUSTER OUTPUT" terminal with 3-4 colored cluster rows, each with a count badge

MODULE 2: Flamegraph AI (id="flamegraph-ai")
Story content:
Open with: "Performance issues rarely announce themselves clearly. They hide deep within call stacks..."
The pain: Engineers staring at flame graphs for hours, hunting hotspots
The question: "What if analyzing a flame graph could be as simple as asking a question?"
The answer: GPT-4.1-powered analysis directly inside Grafana
Key Benefits:
🔥 Instant Hotspot Detection — AI identifies the slowest functions in seconds
🤖 Plain English Diagnosis — GPT-4.1 explains bottlenecks in human-readable form
⚡ Reduced MTTD — Mean Time to Diagnose drops dramatically
👥 Democratized Analysis — Any developer, not just perf experts, can ask questions
🛠️ Actionable Fixes — AI recommends specific optimizations, not just observations
📊 Deep Grafana Integration — Native panel plugin, no context switching
How It Works:
Open Profiling Data → Grafana → Explore → Pyroscope data source
Render Flamegraph → Standard Grafana flamegraph panel loads call stack
Click "Ask AI" → AI Analysis button appears in panel toolbar
Send to GPT-4.1 → Profiling data serialized, enriched with service context, sent to LLM
AI Responds → Plain-English analysis: hotspots, root cause, recommended optimizations
Engineer Acts → Clear, prioritized fix list — no guesswork
Tech Stack: GPT-4.1 · Pyroscope · Grafana Plugin API · Python · Azure OpenAI Service · eBPF Profiling
Visual mockup: CSS-drawn flamegraph bar with colored layers + an AI "chat bubble" overlay with mock analysis text

MODULE 3: Metrics Forecast (id="forecasting")
Story content:
Open with: "Every modern digital ecosystem runs on time-series signals... But 'right now' is not enough."
The gap: "Between observability and predictive operations"
The vision: "Metrics Forecast gives you the future — before it happens"
Key Benefits:
🔮 Multi-Horizon Forecasting — Hours, days, weeks ahead with confidence intervals
📐 PromQL Native — Any existing metric query becomes forecastable instantly
🏔️ Prophet-Powered — Facebook's battle-tested time-series model handles seasonality
⚡ Proactive Capacity Planning — Spot CPU/memory saturation days before customer impact
💰 Cost Optimization — Prevent emergency over-provisioning
🔔 Pre-emptive Alerting — Trigger alerts on predicted thresholds, not actual breaches
How It Works:
Select Metric → PromQL query enters Metrics Forecast panel
Historical Fetch → System pulls 14–90 days of metric history
Prophet Training → Model trains on historical data, learns seasonality + trend
Projection → 24h / 7d / 30d forecast generated with confidence bands
Overlay → Historical + forecast rendered in unified Grafana visualization
Alert Config → Optional: set predicted-value alert thresholds
Tech Stack: Prophet (Meta) · PromQL · Grafana · Python · Azure ML · Prometheus
Visual mockup: CSS-drawn time-series chart line that curves upward with a dashed "forecast" continuation and confidence interval shading

MODULE 4: RCA Hub (id="rca-hub")
Story content:
Open with: "Finding the root cause takes more time than fixing it."
The chaos: "Teams scramble across dashboards — alerts here, traces there, logs in another tool"
The bold question: "What if RCA didn't need to be a treasure hunt?"
The answer: "RCA Hub — a 360° incident intelligence workspace"
Key Benefits:
🕸️ Dependency Graph — Visual service topology with live failure propagation overlay
⏱️ Event Timeline — Chronological view of all events, alerts, deployments across services
📡 Golden Signals — Latency, traffic, errors, saturation for any selected service
🤖 LLM Summarization — GPT-4.1 generates human-readable RCA summary in seconds
🔗 Cross-Service Correlation — Automatically links related alerts across service boundaries
🚀 MTTD/MTTR Reduction — From hours of manual investigation to minutes
How It Works:
Navigate → Grafana → More Apps → AIOPS → RCA Hub
Select Service → Filter by environment, cluster, service type
View Context → Dependency graph + alerts + golden signals load instantly
Explore Timeline → Click any event to expand correlated signals
Generate RCA → Click "Summarize with AI" → GPT-4.1 composes structured RCA
Export → Copy RCA summary to incident ticket (Jira / ServiceNow)
Tech Stack: GPT-4.1 · Azure OpenAI Service · Grafana · Prometheus · Jaeger / Tempo · Graph DB (Neo4j / Azure Cosmos) · Python FastAPI
Visual mockup: CSS-drawn mini service dependency graph (nodes + edges with one red "failing" node)

MODULE 5: Service Insights (id="service-insights")
Story content:
Open with: "You cannot fix what you cannot see — and you cannot prioritize what you do not understand."
The reality: Saturation warnings, error spikes, anomaly signals — scattered across tools
The insight: "What if we had a single pane of intelligence that tells us which services need attention, why, and how urgently?"
The SAAFE model: Saturation · Amend · Anomaly · Failure · Error
Key Benefits:
🛡️ SAAFE Scoring — Five event categories weighted by business impact
📊 Ranked Service List — Most critical to least, eliminating guesswork
🔍 Event Drill-Down — Click any service to see contributing SAAFE signals
🤖 AI Explanation — LLM explains why a service is ranked high
📈 Trend Tracking — Score history shows if a service is improving or deteriorating
👥 Team Routing — Assign services to owning teams directly from the UI
How It Works:
Event Ingestion → AKS events stream into processing pipeline continuously
Categorization → Each event tagged as S/A/A/F/E with severity weight
Scoring → Weighted score computed per service per time window
Ranking → Services sorted by composite SAAFE score
LLM Enrichment → AI adds a 2-3 sentence "why is this critical?" summary
Dashboard → Engineers open Service Insights, see ranked list instantly
SAAFE Model Explanation Panel (visual grid with 5 colored cards):
🔴 Saturation — Resource limits approaching critical thresholds
🟡 Amend — Config changes, rollouts, or modifications detected
🟠 Anomaly — Statistical deviation from normal behavior detected
🔴 Failure — Pod crashes, node failures, service unavailability
🟠 Error — Error rate spikes, 5xx surges, exception storms
Tech Stack: Python · Kubernetes Events API · GPT-4.1 · Azure OpenAI Service · Grafana · Prometheus · Azure Event Hub

MODULE 6: ESOB SLO Framework (id="slo-framework")
Story content:
Open with: "Reliability is not optional — it's foundational."
The problem: Thousands of microservices, hundreds of teams, no common reliability language
The questions: "How do we create a unified, enterprise-wide language for reliability?"
The birth: "ESOB SLO Framework — the central nervous system for service reliability"
Built on Google SRE best practices, tailored for AKS
Key Benefits:
📐 Standardized Definitions — SLI, SLO, Error Budget defined identically across all 200+ services
🔔 Multi-Window Burn Rate Alerts — Detect both fast-burning incidents AND slow-burning reliability debt
📊 Portfolio → Service Drill-Down — C-level to service owner views in one hierarchy
⚡ Error Budget Tracking — Real-time burn rate, budget remaining, risk level per service
🔧 App-Level Overrides — Teams customize SLO targets with governance guardrails
👥 Role-Based Views — Leaders see portfolio health; SREs see burn rates; devs see service details
Key Concepts Panel (3-card grid):
SLI (Service Level Indicator) — The actual measurement: "99.2% of requests succeeded in <200ms"
SLO (Service Level Objective) — The target: "99.5% of requests must succeed in <200ms"
Error Budget — The tolerance: "0.3% of requests can fail before we must act"
Multi-Window Burn Rate (visual table):
Window
Burn Rate
Alert Severity
5 min
> 14.4x
🔴 Critical Page
30 min
> 6x
🔴 Critical Page
1 hour
> 3x
🟡 Warning
6 hour
> 1x
🟠 Ticket

Tech Stack: Prometheus · Grafana · PromQL · Alertmanager · Python · Azure AKS · GitOps

6. PLATFORM IMPACT SECTION (id="impact")
Background: subtle grid pattern
H2: "Measurable Impact Across the Enterprise"
4 large metric cards with animated count-up:
90% — Alert Noise Reduction
5 min — Average Investigation Time
200+ — Services Covered
99.9% — SLO Target Precision
Below: Horizontal timeline of AIOps evolution: 2022: Manual dashboards → 2023: Alert rules → 2024: ML alert grouping → 2025: Full AIOps suite

7. HOW EVERYTHING CONNECTS — ARCHITECTURE SECTION (id="architecture")
H2: "A Unified Intelligence Layer"
CSS-drawn architecture diagram showing data flow:
[Kubernetes AKS] → [Prometheus / Pyroscope] → [AIOps Processing Layer]
                                                        ↓
[Alert Clustering] [Flamegraph AI] [Forecasting] [RCA Hub] [Service Insights] [SLO Framework]
                                                        ↓
                                              [Grafana Unified UI]
                                                        ↓
                                    [SREs / Developers / Leaders / On-Call]

Each layer is a styled horizontal band with icons
Animated arrows connecting the layers (CSS animation)

8. TECHNOLOGY STACK SECTION (id="tech-stack")
H2: "Built on Industry-Leading Technology"
Logo grid (text-based "logos" in styled pills, 3-4 rows): Row 1: Grafana · Prometheus · Kubernetes (AKS) · Pyroscope Row 2: Python · FastAPI · GPT-4.1 · Azure OpenAI Service · Prophet (Meta) Row 3: HDBSCAN · Sentence Transformers · MongoDB · Azure File Storage Row 4: Apache Parquet · APScheduler · Alertmanager · Azure Event Hub

9. FREQUENTLY ASKED QUESTIONS (id="faq")
H2: "Common Questions"
CSS accordion (click to expand, smooth height animation, no JS libraries)
8 Q&A pairs:
Q: "Is this a replacement for Grafana?" A: No — it extends Grafana with AI layers
Q: "Which clusters are supported?" A: AKS and GKE are fully supported today
Q: "How is alert clustering different from Alertmanager grouping?" A: Semantic ML vs rule-based
Q: "Is RCA Hub production-ready?" A: Yes — RCA Hub is fully production-ready and GA
Q: "What LLM powers Flamegraph AI and RCA?" A: GPT-4.1 via Azure OpenAI Service
Q: "How far can Metrics Forecast predict?" A: Configurable; tested up to 30 days
Q: "Can teams override SLO targets in the ESOB framework?" A: Yes, with governance guardrails
Q: "How does the SAAFE model score services?" A: Weighted event count by category and severity

10. CALL TO ACTION / FOOTER SECTION
CTA Banner:
Dark gradient background with orange glow
H2: "Ready to Transform Your Observability?"
Body: "Join the teams already using AIOps to prevent incidents, accelerate recovery, and improve reliability."
Two buttons: "Open Grafana →" + "Contact the AIOps Team"
Footer:
Logo + tagline: "Albertsons Enterprise Observability · AIOps Intelligence Suite"
3-column links: Modules | Resources | Team
Bottom bar: "© 2026 Albertsons Companies, Inc. · Built by the Enterprise Observability Team"
Subtle animated gradient line at very top of footer

INTERACTIVE FEATURES (ALL REQUIRED)
JavaScript Features (vanilla JS, no frameworks):
Sticky Header Shadow — window.addEventListener('scroll', ...) adds .scrolled class to header past 50px
Active Nav Highlighting — IntersectionObserver watches all [id] sections, highlights matching nav link
Smooth Scroll — CSS scroll-behavior: smooth + JS for nav links
Animated Count-Up — IntersectionObserver triggers number animation when stats enter viewport
Search Filter — Header search input oninput filters visible module cards and section titles
Accordion FAQ — Click Q → toggle max-height, rotate arrow icon, smooth transition
Module Card Navigation — Clicking overview card smooth-scrolls to that module's section
Reading Progress Bar — Thin orange bar at very top of page, fills as user scrolls
"Back to Top" Button — Appears after 300px scroll, smooth scrolls to hero
Mobile Hamburger Menu — Toggle nav drawer on small screens
Scroll-Triggered Fade-In — IntersectionObserver on sections: opacity 0 → 1, translateY 30px → 0
Tech Stack Tooltip — Hover tech pill shows short description

ACCESSIBILITY (WCAG 2.1 AA)
<a class="skip-link">Skip to main content</a> as first element in body
All interactive elements have :focus-visible styles (orange outline)
All images/icons have aria-label or alt
Color contrast: text-primary (#F2F3F5) on dark-bg (#111217) = 15:1 ratio ✅
role="navigation", aria-label="Main navigation" on <nav>
Accordion uses aria-expanded, aria-controls, role="button"
All section headings in proper H1 > H2 > H3 hierarchy
prefers-reduced-motion media query disables animations

PERFORMANCE REQUIREMENTS
Single file, ZERO external dependencies (no CDN, no fonts, no images)
All icons: Unicode emoji or SVG inline
All animations: CSS transforms only (GPU-accelerated, no layout thrashing)
Max file size: under 150KB unminified
<link rel="preconnect"> for any future external resources
Lazy loading with IntersectionObserver (not loading="lazy" which requires src)

CSS ANIMATIONS TO INCLUDE
/* Hero gradient text animation */
@keyframes gradientShift { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }

/* Floating particles */
@keyframes float { 0%, 100% { transform: translateY(0px) rotate(0deg); } 50% { transform: translateY(-20px) rotate(180deg); } }

/* Gentle ambient glow pulse */
@keyframes gentleGlow { 0% { opacity: 0.4; transform: scale(1); } 100% { opacity: 0.7; transform: scale(1.15); } }

/* Count-up (handled by JS, just apply transition) */

/* Scroll fade-in */
.reveal { opacity: 0; transform: translateY(30px); transition: opacity 0.6s ease, transform 0.6s ease; }
.reveal.visible { opacity: 1; transform: translateY(0); }

/* Stagger children */
.stagger > *:nth-child(1) { transition-delay: 0.1s; }
.stagger > *:nth-child(2) { transition-delay: 0.2s; }
.stagger > *:nth-child(3) { transition-delay: 0.3s; }
/* ...etc */

/* Progress bar */
@keyframes none; /* JS-driven width */

/* Architecture layer pulse */
@keyframes architecturePulse { 0%, 100% { box-shadow: 0 0 0 0 rgba(255,119,51,0.4); } 50% { box-shadow: 0 0 0 8px rgba(255,119,51,0); } }


VISUAL MOCKUPS (CSS-ONLY, NO IMAGES)
Alert Clustering Terminal Mockup
┌─────────────────────────────────────────────┐
│  🔔  CLUSTER OUTPUT  ·  5-min window         │
├─────────────────────────────────────────────┤
│  🔴 CLUSTER-001  [47 alerts]  Payment-API   │
│     "High error rate + DB timeout cascade"  │
│                                             │
│  🟡 CLUSTER-002  [23 alerts]  Auth-Service  │
│     "CPU saturation + pod restarts"         │
│                                             │
│  🟠 CLUSTER-003  [18 alerts]  CDN-Layer     │
│     "Latency spike — upstream dependency"   │
│                                             │
│  ✅ 882 other alerts de-duplicated          │
└─────────────────────────────────────────────┘

Style this as a CSS-only card with monospace font, colored cluster rows, and a blinking cursor.
Flamegraph Bar Mockup
A CSS horizontal bar chart with 5-6 colored bars of decreasing width, each labeled with function names, with an AI chat bubble overlapping it showing mock analysis.
Forecast Chart Mockup
CSS-drawn SVG or pure CSS line that curves upward, transitions to dashed (the forecast portion), with a shaded confidence interval band below the dashed line.
Dependency Graph Mockup
Pure CSS positioned elements: 5-6 circular nodes connected by lines (CSS borders/pseudo-elements), one node colored red (failing), arrows using CSS border trick.

FILE STRUCTURE (SINGLE FILE)
<!DOCTYPE html>
<html lang="en">
<head>
  <!-- Meta, SEO, Preconnects -->
  <style>
    /* ALL CSS inline — organized with section comments */
    /* 1. Reset & Base */
    /* 2. Design Tokens (CSS Custom Properties) */
    /* 3. Typography */
    /* 4. Layout & Grid */
    /* 5. Header & Nav */
    /* 6. Buttons & Badges */
    /* 7. Hero Section */
    /* 8. Overview Grid */
    /* 9. Module Sections (1-6) */
    /* 10. Impact Section */
    /* 11. Architecture Section */
    /* 12. Tech Stack */
    /* 13. FAQ Accordion */
    /* 14. CTA & Footer */
    /* 15. Animations */
    /* 16. Responsive (Mobile-First) */
    /* 17. Accessibility & Reduced Motion */
  </style>
</head>
<body>
  <!-- Skip Link -->
  <!-- Reading Progress Bar -->
  <!-- Header + Nav -->
  <!-- Hero -->
  <!-- Overview Grid -->
  <!-- 6 Module Sections -->
  <!-- Impact -->
  <!-- Architecture -->
  <!-- Tech Stack -->
  <!-- FAQ -->
  <!-- CTA + Footer -->
  <!-- Back to Top Button -->
  <script>
    /* ALL JavaScript inline */
    // 1. Reading progress bar
    // 2. Header scroll effect
    // 3. IntersectionObserver — nav active states
    // 4. IntersectionObserver — scroll reveal
    // 5. Count-up animation
    // 6. Search filter
    // 7. FAQ accordion
    // 8. Smooth scroll (polyfill for Safari)
    // 9. Mobile hamburger menu
    // 10. Back to top button
  </script>
</body>
</html>


QUALITY STANDARDS
No Lorem Ipsum — All text must be real AIOps content from the domain descriptions above
No placeholder comments like <!-- Add content here --> — All sections fully built
No external CDN — Zero network dependencies
No React / Vue / Alpine — Pure HTML + CSS + Vanilla JS
Responsive at 320px, 768px, 1024px, 1440px — Test each breakpoint
Works offline — Open in a browser with no internet connection
Print stylesheet — @media print styles for clean printing
Dark mode only — This is a Grafana-native dark UI (no light mode toggle needed)
Code quality: Well-commented, consistent indentation, semantic HTML5 elements

OUTPUT
Produce the complete file aiops-intelligence-hub.html with:
No truncation — the full file, every section, completely built
Estimated size: 100–150KB
All 10 sections implemented
All 12 JavaScript features working
All 6 module deep-dives with full content
All CSS animations included
Mobile responsive
This is a showcase-quality deliverable. Make it exceptional.


