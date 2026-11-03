# 5Tech Solutions Website v2.0 — UI/UX & Content Upgrade Specification

**Website:** https://5ts.io.vn/  
**Date:** 2026-11-03  
**Status:** Implementation-ready specification for Claude Code / Codex  
**Language:** Vietnamese primary, English secondary  
**Hosting decision:** **KEEP CURRENT GITHUB PAGES HOSTING**  
**DNS decision:** **KEEP P.A VIỆT NAM DNS UNCHANGED**

---

## 0. Instructions for the Coding Agent (READ FIRST)

You are acting as a **Senior Product Designer, Frontend Engineer, Technical SEO Specialist, Content Strategist, Accessibility Reviewer and QA Engineer** for 5Tech Solutions.

Your mission is to upgrade the **existing website in-place**, not replace its hosting or change its operating environment. First inspect the actual repository before making any assumptions about its framework, file structure, build pipeline, deployment branch, CNAME behavior or routes.

**Non-negotiable constraints**

1. Keep **https://5ts.io.vn/** live on **GitHub Pages**. Do **not** migrate to Vercel, Cloudflare Pages, Netlify or any paid platform.
2. Keep DNS at **P.A Việt Nam**. Do not change nameservers, A/AAAA/CNAME/MX/TXT records or the `family.5ts.io.vn` configuration.
3. Do not break the existing custom domain, HTTPS, deployment source or existing Vietnamese/English URLs. Preserve the `CNAME` custom-domain setup **as appropriate for the actual GitHub Pages deployment method**.
4. Start by inspecting the codebase; **reuse the current stack** (static HTML/CSS/JS, Astro, React/Vite, etc.) when practical. Avoid a framework rewrite for cosmetic purposes.
5. No backend server, SSR or serverless function is assumed to exist on GitHub Pages. All production output must be static.
6. No invented clients, endorsements, certifications, employee counts, testimonials, revenue figures, delivery guarantees, download numbers or technical achievements. Mark any unverified claims as `TODO: VERIFY` and exclude them from production copy.
7. Do not imply the **5Tech AI Software Factory** is a mature commercial product. Describe it accurately as a developing internal AI-assisted engineering workflow until demonstrated otherwise.
8. Protect existing SEO URLs, analytics IDs, consent rules, accessibility and current working links; test anything changed.
9. Never commit credentials, service-role keys, API tokens or private customer data.
10. Create a feature branch and Pull Request; **do not automatically merge or deploy to production without review**.

**Final deliverables from the coding agent:** functioning updated website, content in VI/EN, responsive UI, build/test result, SEO checklist, screenshots (desktop/mobile if available), concise change log and rollback steps.

---

## 1. Current Website — Verified Public Baseline

Public site checked on 2026-11-03: https://5ts.io.vn/ . These are visible website contents, **not proof of the repository's underlying implementation**.

| Current area | Publicly visible content | v2 action |
|---|---|---|
| Header | Services / Technology / Projects / About; VI/EN language selection; contact CTA | Keep and improve navigation, responsiveness, active states |
| Hero | “Ý tưởng của bạn. Giải pháp của chúng ta.” | Preserve brand warmth; add clear service description and conversion CTA |
| Services | Mobile Apps, Experience Design, AI & Backend | Expand with AI-assisted MVP and system integration while keeping claims truthful |
| Technology | Flutter/Mobile, Backend/API, AI/Integration | Organize into capabilities and outcomes, not logo clutter |
| Portfolio | GrowthInvesting; FamilyNestPro | Give each project a richer, verifiable case-study section |
| About | Vietnam-based creative software team | Strengthen technical credibility, values and working process |
| Contact | info@5ts.io.vn; +84 935 357 567; HCMC and Quảng Ngãi | Improve copy, structured contact methods, optional no-backend lead form |
| Visual style | Product-lab concept, illustrative mockups | Keep premium studio character; better hierarchy and distinction between concept art and actual products |

**Existing public links to preserve:**
- https://5ts.io.vn/
- https://family.5ts.io.vn/
- https://growthinvesting.vn/
- `mailto:info@5ts.io.vn`
- Existing `/en/` route, if confirmed in repository

**Important:** Domain and hosting configuration were described by the owner as GitHub-based. Verify the actual GitHub Pages source and `CNAME` handling before editing deployment code.

---

## 2. Product Vision and Positioning

### Proposed positioning

**5Tech Solutions — AI-Powered Digital Product Studio**

Primary offering: thoughtful mobile/web products and dependable engineering, with AI applied where it improves outcomes. AI-assisted development is a **delivery capability**, not a promise of fully autonomous production software.

**Differentiators to communicate honestly:**
- Cross-platform mobile experience with Flutter, Android and iOS.
- Frontend, backend, APIs and product architecture as an integrated delivery process.
- Strong attention to usability, product scope and maintainability.
- Demonstrable real products: FamilyNest Pro and GrowthInvesting.
- Experimentation with Claude Code, Codex and automation in an AI-assisted software workflow; avoid unverified productivity statistics.

### Audiences

1. **Startup founder / SME:** needs an MVP or production app.
2. **Product company:** needs mobile/frontend/backend engineering capacity.
3. **Business exploring AI:** wants practical AI integrations, not a buzzword pitch.
4. **Potential technology partner:** evaluates code quality, communication and domain knowledge.

### Conversion goal

Primary: qualified project inquiries via contact CTA.  
Secondary: visits to real project case studies and product sites.  
Tertiary: trust signals and inquiries from prospective partners.

---

## 3. Information Architecture

**Phase 1: retain the current website structure and existing URLs wherever possible.** If the current site is a single-page app or a static single page, build sections on that page instead of forcing multi-page routing.

Suggested order:

1. Header / Navigation
2. Hero / Value proposition
3. Proof bar (only verified statements, e.g. platforms supported, real products)
4. Services / What we build
5. Selected Work / Case Studies
6. Our Process / How we collaborate
7. AI-Assisted Engineering / Our approach
8. Technology / Capabilities
9. About / Values
10. FAQ
11. Contact / CTA
12. Footer / Legal

**Phase 2 optional** (only when repository routing, content requirements and SEO justify it):
- `/services/`
- `/work/`
- `/work/familynest-pro/`
- `/work/growthinvesting/`
- `/ai-software-factory/`
- `/contact/`
- `/en/` localized equivalents

For GitHub Pages, consider static HTML routes or pre-rendered pages. If the existing app uses client-side routing, ensure deep-link reloads are tested on GitHub Pages; do not rely on server rewrite rules that GitHub Pages lacks.

---

## 4. Visual Design System

### Design direction

**Contemporary, confident, engineering-led and human-friendly.** Evolve current site rather than creating an unrelated aesthetic.

- Use a light-first editorial layout or retain the current effective theme; allow dark panels sparingly for featured technical work.
- Typography: clear Vietnamese diacritics, strong hierarchy, balanced line lengths. Use system/local fallbacks and avoid unnecessary font load.
- Color: derive final brand tokens from existing 5Tech logo/assets. **Do not assume color codes without checking source assets.**
- Components: clean cards, soft borders, meaningful whitespace, accessible buttons and strong visual states.
- Motion: subtle entrance or hover animation only; honor `prefers-reduced-motion`.
- Imagery: prioritize **real screenshots** of FamilyNest Pro and GrowthInvesting with permission. If placeholders/concepts remain, clearly label as illustrations.
- Avoid random stock images, excessive gradients, glassmorphism everywhere and unsupported company achievements.

### Draft tokens — confirm against current brand

```css
:root {
  --color-bg: #f7f9fb;
  --color-surface: #ffffff;
  --color-text: #142333;
  --color-muted: #536273;
  --color-accent: #168a79; /* DRAFT: verify against brand */
  --color-accent-contrast: #ffffff;
  --color-border: #dce4e9;
  --radius-card: 16px;
  --container-max: 1200px;
}
```

These are **proposed** design tokens, not official logo colors.

### Responsive requirements

| Breakpoint | Expected behavior |
|---|---|
| 320–479px | Single-column hero/cards, no horizontal scrolling, thumb-friendly controls |
| 480–767px | Large mobile, comfortable reading, simplified navigation |
| 768–1023px | Tablet, two-column selected content, clear navigation |
| 1024px+ | Multi-column editorial sections, controlled max width |

Accessibility: WCAG 2.2 AA as target, visible focus rings, skip-link, semantic landmarks, sufficient contrast, 44px-ish touch targets when feasible, labeled menus, keyboard navigation and sensible image `alt` text.

---

## 5. Approved Draft Copy — Vietnamese

Use this as a starting copy deck, not as a substitute for verified product details. Copy should feel concise and natural, not like generic agency marketing.

### 5.1 Navigation

- Dịch vụ
- Sản phẩm
- Quy trình
- Công nghệ
- Về 5Tech
- Liên hệ
- VI / EN

### 5.2 Hero

**Eyebrow:** MOBILE · AI · SOFTWARE ENGINEERING

**H1:** `Ý tưởng của bạn. Chúng tôi biến thành sản phẩm.`

**Supporting copy:**  
`5Tech Solutions thiết kế và phát triển ứng dụng iOS, Android cùng các giải pháp web, backend và tích hợp AI. Chúng tôi kết hợp tư duy sản phẩm, kinh nghiệm kỹ thuật và quy trình làm việc minh bạch để đưa ý tưởng vào thực tế.`

**Primary CTA:** `Trao đổi về dự án` → `mailto:info@5ts.io.vn?subject=Trao%20%C4%91%E1%BB%95i%20d%E1%BB%B1%20%C3%A1n%20v%E1%BB%9Bi%205Tech`

**Secondary CTA:** `Khám phá sản phẩm` → projects section.

**Microcopy:** `Từ ý tưởng ban đầu đến sản phẩm có thể sử dụng.`

### 5.3 Services

**Section title:** `Từ ý tưởng đến trải nghiệm thực tế.`  
**Intro:** `Chúng tôi giúp đội ngũ sản phẩm giải quyết đúng vấn đề, chọn công nghệ phù hợp và phát triển có thể kiểm chứng.`

**Service 1 — Phát triển ứng dụng di động**  
`Thiết kế và xây dựng ứng dụng Flutter, Android và iOS với trọng tâm là trải nghiệm người dùng, hiệu năng và khả năng bảo trì.`  
Tags: `Flutter` · `Android` · `iOS`

**Service 2 — Web & Backend Engineering**  
`Xây dựng giao diện web, API, tích hợp dữ liệu và các thành phần backend phục vụ hoạt động thực tế của sản phẩm.`  
Tags: `Web` · `Python` · `API` · `Database`

**Service 3 — UI/UX & Product Design**  
`Làm rõ nhu cầu người dùng, thiết kế luồng sử dụng, prototype và giao diện dễ hiểu trước khi triển khai.`  
Tags: `UX Research` · `UI Design` · `Prototype`

**Service 4 — AI Integration & Automation**  
`Khám phá các ứng dụng AI có giá trị thực tiễn: trợ lý thông minh, xử lý thông tin và tự động hóa quy trình phù hợp với bài toán.`  
Tags: `AI Integration` · `Automation` · `Workflow`

**Service 5 — MVP & Product Delivery**  
`Xác định phạm vi phù hợp để ra mắt phiên bản đầu tiên, đo phản hồi và cải tiến từng bước mà không phát triển dàn trải.`  
Tags: `Discovery` · `MVP` · `Iteration`

### 5.4 Selected Work

**Title:** `Sản phẩm thực. Bài toán thực.`  
**Intro:** `Một số sản phẩm thể hiện cách chúng tôi tiếp cận trải nghiệm, kỹ thuật và những nhu cầu hằng ngày.`

**FamilyNest Pro**  
- Category: `Family · Productivity · Mobile`
- Headline: `Một không gian chung để gia đình phối hợp và chăm sóc nhau.`
- Description: `FamilyNest Pro hỗ trợ gia đình quản lý các hoạt động thường ngày thông qua mô hình năm sổ tay gia đình và định hướng trợ lý Nestmi AI.`
- Status: `Ứng dụng đã phát hành trên Android và iOS` (**owner-provided; verify current store links before publishing badges**)
- CTA: `Khám phá FamilyNest Pro` → https://family.5ts.io.vn/
- Notes: Use genuine app imagery; don't claim Nestmi features are live unless verified on current product.

**GrowthInvesting**  
- Category: `FinTech · Investment Tools`
- Headline: `Công cụ đồng hành cùng quá trình theo dõi và phân tích đầu tư.`
- Description: `GrowthInvesting tập trung hỗ trợ nhà đầu tư cá nhân theo dõi tín hiệu và lập kế hoạch đầu tư với thông tin dễ tiếp cận.`
- CTA: `Khám phá GrowthInvesting` → https://growthinvesting.vn/
- Notes: No claim of guaranteed performance or return.

**Case-study layout for each product:** Context → Users & Problems → Product Approach → Tech Stack (**verify**) → Screenshots → Public Result (**verified only**) → Visit Product.

### 5.5 Collaboration Process

**Title:** `Làm rõ trước. Xây đúng sau.`

1. `Khám phá` — Trao đổi mục tiêu, người dùng và ràng buộc.
2. `Định hình giải pháp` — Thống nhất phạm vi, UX và hướng kỹ thuật.
3. `Phát triển theo giai đoạn` — Triển khai các phần có thể xem và kiểm thử.
4. `Kiểm thử & hoàn thiện` — Review code, kiểm tra tính năng và trải nghiệm.
5. `Ra mắt & cải tiến` — Hỗ trợ phát hành và điều chỉnh theo phản hồi.

**Support line:** `Mỗi dự án có quy mô và lộ trình phù hợp; chúng tôi ưu tiên trao đổi rõ ràng thay vì cam kết chung chung.`

### 5.6 AI-Assisted Engineering

**Title:** `Kinh nghiệm kỹ thuật, được hỗ trợ bởi AI.`

`5Tech đang phát triển mô hình AI Software Factory nội bộ nhằm hỗ trợ phân tích yêu cầu, lập kế hoạch, viết mã, review và kiểm thử. Chúng tôi đặt việc kiểm chứng kỹ thuật, bảo mật và quyết định của con người vào những khâu quan trọng.`

**Three principles:**
- `AI hỗ trợ năng suất` — Tự động hóa những phần việc phù hợp.
- `Kỹ sư chịu trách nhiệm` — Có đánh giá và kiểm chứng trước khi phát hành.
- `Chất lượng có thể kiểm tra` — Ưu tiên test, review và minh bạch thay đổi.

**Status label:** `Đang phát triển và chuẩn hóa quy trình nội bộ`.

### 5.7 Technology

**Title:** `Công nghệ là công cụ. Giá trị nằm ở sản phẩm.`

Group technologies based on verified repository/team capability:
- `Mobile`: Flutter / Dart / Android / iOS
- `Frontend`: React / TypeScript / Vite (**verify if advertised as services**)
- `Backend`: Python / FastAPI / PostgreSQL / APIs
- `AI & Automation`: Claude Code / Codex / n8n (**as tools in workflow, not proprietary AI products**)
- `Delivery`: Git / GitHub / CI/CD / Testing

Only display logos if licenses and usage are appropriate.

### 5.8 About

**Title:** `Một đội ngũ. Một cách làm đặt sản phẩm và sự tin cậy làm trọng tâm.`

`5Tech Solutions là đội ngũ công nghệ tại Việt Nam, tập trung vào việc xây dựng sản phẩm số có ích, dễ dùng và có nền tảng kỹ thuật vững chắc. Chúng tôi coi việc hiểu đúng vấn đề và hợp tác rõ ràng là điều quan trọng không kém việc viết mã.`

**Values:** `Thực tế` · `Minh bạch` · `Chất lượng` · `Đồng hành`

**Location line:** `Việt Nam · TP. Hồ Chí Minh & Quảng Ngãi` (**validate desired public company/contact wording**).

**Legal name:** Do **not** present a planned company legal name or business-registration details as legally registered before registration is confirmed.

### 5.9 FAQ

**Q:** `5Tech có phát triển ứng dụng cho cả Android và iOS không?`  
**A:** `Có. Chúng tôi làm việc với công nghệ đa nền tảng như Flutter và lựa chọn giải pháp phù hợp với từng sản phẩm.`

**Q:** `5Tech có thể tham gia từ giai đoạn ý tưởng không?`  
**A:** `Có. Chúng tôi có thể cùng xác định vấn đề, phạm vi MVP, trải nghiệm và hướng kỹ thuật trước khi phát triển.`

**Q:** `AI có thay thế hoàn toàn lập trình viên trong quy trình của 5Tech không?`  
**A:** `Không. AI hỗ trợ một số công đoạn kỹ thuật; con người vẫn chịu trách nhiệm đánh giá, kiểm thử và các quyết định quan trọng.`

**Q:** `Làm sao để bắt đầu trao đổi dự án?`  
**A:** `Gửi email mô tả ngắn về ý tưởng, nhóm người dùng và mục tiêu mong muốn tới info@5ts.io.vn.`

### 5.10 Contact & Footer

**Title:** `Có một bài toán cần giải quyết? Hãy bắt đầu từ một cuộc trò chuyện.`  
**Description:** `Cho chúng tôi biết bạn đang xây dựng điều gì, ai sẽ sử dụng và bạn muốn đạt kết quả nào.`

**CTA:** `Gửi email cho 5Tech` → `mailto:info@5ts.io.vn`  
**Email:** `info@5ts.io.vn`  
**Phone:** `+84 935 357 567` (**verify continued correctness before deployment**)  
**Website:** https://5ts.io.vn/

**Footer:** `© {current year} 5Tech Solutions. All rights reserved.`

Use privacy/contact disclosures if introducing analytics or a data-collection form. Do not introduce a form that silently discards leads.

---

## 6. English Copy Deck

Content must be written fluently in English, not machine-word-for-word translated. Keep business claims equivalent across languages.

| Section | English proposed copy |
|---|---|
| Positioning | `AI-Powered Digital Product Studio` |
| Hero headline | `Your idea. Built into a real product.` |
| Hero description | `5Tech Solutions designs and builds iOS and Android apps, web experiences, backend systems, and practical AI integrations. We combine product thinking with dependable engineering and transparent collaboration.` |
| Primary CTA | `Discuss Your Project` |
| Secondary CTA | `Explore Our Work` |
| Services title | `From ideas to useful digital products.` |
| Mobile | `Cross-platform and native mobile experiences designed for usability, performance, and maintainability.` |
| Web & Backend | `Reliable web interfaces, APIs, integrations, and data-driven backend systems.` |
| Product Design | `User flows, prototypes, and interfaces that make complex tasks easier to use.` |
| AI | `Practical AI integration and workflow automation focused on a real business need.` |
| MVP | `Define a focused first release, validate assumptions, and improve through feedback.` |
| Projects | `Real products. Real problems.` |
| FamilyNest Pro | `A shared space to help families organize everyday routines and care.` |
| GrowthInvesting | `Tools to support individual investors in monitoring signals and planning their investment process.` |
| Process | `Understand first. Build with purpose.` |
| AI Factory | `Engineering experience, supported by AI.` |
| AI Factory description | `We are developing an internal AI-assisted engineering workflow to support requirements analysis, planning, coding, review, and testing. Human judgment and verification remain essential.` |
| About | `A technology team focused on useful products and trusted partnerships.` |
| Contact title | `Have a problem worth solving? Let's talk.` |
| Contact CTA | `Email 5Tech` |

Also translate the 5 process steps, FAQ entries, project cards, navigation labels, image alt text and metadata. Preserve an existing `/en/` URL if present; do not introduce `/en` versus `/en/` conflicts.

---

## 7. Interaction & Components

**Components** (adapt to existing tech stack):

- `SiteHeader` — sticky or non-sticky based on current UX, keyboard-accessible mobile menu, logo links to home, VI/EN switch.
- `HeroSection` — single H1, two CTAs, purposeful visual panel.
- `ServiceCard` — accessible title, summary, tags and optional link.
- `ProjectCard` — real screenshot, category, verified product description and external link.
- `ProcessTimeline` — five-step workflow with semantic ordered list.
- `AIEngineeringSection` — factual and modest depiction of emerging AI-assisted workflow.
- `TechnologyGroups` — text-first capabilities.
- `FAQSection` — native `<details>` preferred if stack supports.
- `ContactSection` — functional `mailto:` and `tel:` links; optional external form after explicit provider decision.
- `SiteFooter` — legal/contact information and back-to-top control.

**Interaction details:**
- Nav links scroll to sections without hiding headings behind sticky header.
- Mobile menu opens/closes correctly, supports Escape key and focus handling.
- VI/EN switch preserves equivalent destination when possible.
- External links include descriptive accessible names and safe rel attributes where applicable.
- Use real URL destinations, not dummy `#` CTA targets.
- No auto-playing video/audio. No intrusive animation.

**Lead capture strategy on GitHub Pages:**

- **MVP default:** email CTA with prefilled subject, robust across static hosting.
- **Optional later:** third-party form endpoint or independently hosted API (with validation, rate limiting, bot protection, privacy notice and delivery testing). Do not imply GitHub Pages can run server-side email handlers.

---

## 8. SEO & Performance Requirements

### Technical SEO

- Unique `<title>` and meta description per localized page.
- One visible H1 per page, logical H2/H3 hierarchy.
- Correct `lang="vi"` and `lang="en"` per page.
- Canonical URLs reflecting actual published URLs.
- If VI/EN pages exist, proper `hreflang="vi"`, `hreflang="en"`, optional `x-default`, using real accessible URLs.
- Open Graph + Twitter/X preview title, description and properly sized image.
- XML sitemap generated or maintained with canonical URLs only.
- robots.txt allows production content and references sitemap as appropriate.
- `Organization` and `WebSite` JSON-LD with **verified** name, URL, logo and contact points. No unsupported structured-data claims.
- Content on `family.5ts.io.vn` and `growthinvesting.vn` should be linked from project pages; do not duplicate extensive product site content.
- Preserve existing URLs or set up a feasible static redirect plan where changed.

**Draft metadata (VI):**

```html
<title>5Tech Solutions | Phát triển ứng dụng Mobile, Web & AI</title>
<meta name="description" content="5Tech Solutions thiết kế và phát triển ứng dụng Flutter, iOS, Android, web, backend và tích hợp AI. Cùng biến ý tưởng thành sản phẩm thực tế." />
<link rel="canonical" href="https://5ts.io.vn/" />
```

**Draft metadata (EN, only if `/en/` exists):**

```html
<title>5Tech Solutions | Mobile, Web & AI Development</title>
<meta name="description" content="5Tech Solutions designs and builds mobile apps, web products, backend systems and practical AI integrations. Explore our work and discuss your project." />
<link rel="canonical" href="https://5ts.io.vn/en/" />
```

### Performance objectives

- LCP ≤ 2.5 s; INP ≤ 200 ms; CLS ≤ 0.1 at the 75th percentile of relevant real-user measurements, where available.
- Aim for Lighthouse mobile Performance and Accessibility ≥ 90 **as targets, not claims of current performance**.
- Compress images using WebP/AVIF with suitable fallback, responsive `srcset`, explicit width/height, and lazy loading below fold.
- Avoid oversized fonts/libraries and unnecessary JS for static content.
- Defer non-critical scripts; use responsive CSS and code splitting if applicable.
- Add caching strategies appropriate to GitHub Pages; do not assume custom server headers are configurable.

---

## 9. GitHub Pages Deployment — Preserve, Don't Replace

### 9.1 First inspect configuration

Agent must identify:

- GitHub Pages source: `Deploy from a branch` **or** `GitHub Actions`.
- Repository type (root user/org page or project page).
- Build system and output path (`/`, `docs/`, `dist/`, etc.).
- Custom domain configuration in **Settings → Pages**.
- Whether a `CNAME` file is required by the current deployment approach.
- Existing Actions workflows and environment permissions.
- Correct base path, assets and client-side routing behavior.

**Do not overwrite a working workflow blindly.** Update only if necessary and only after a successful local build.

### 9.2 If site is plain HTML/CSS/JS

- Prefer the existing branch-based publishing arrangement.
- Keep published files in the configured folder.
- Preserve current `CNAME` if required.
- Confirm GitHub Pages and custom domain settings after merge.

### 9.3 If site uses a bundler (Vite/Astro/etc.)

- Prefer existing publishing configuration if valid.
- If a GitHub Actions deployment is already used, keep and improve it rather than replacing it.
- If changing from branch publishing to Actions is truly needed, document why and explicitly require owner approval.
- Publish static build output only (e.g., `dist/` for Vite).
- Use GitHub Pages deployment actions and repository permissions per official GitHub documentation.
- For a **custom root domain**, configure bundler base path accordingly. Do not assume the project-repo path is part of the public URL.
- `CNAME` handling differs by source type: for branch publishing a `CNAME` in the published source may be relevant; for custom Actions publishing GitHub Pages domain settings control the domain and a `CNAME` inside the artifact is not required. Verify actual method.

### 9.4 Operations that are forbidden without a separate request

- Changing DNS at P.A Việt Nam.
- Changing nameservers or apex/subdomain routing.
- Disabling GitHub Pages.
- Adding Vercel/Cloudflare/Netlify deployment configs.
- Converting the site to SSR with a required always-on server.
- Replacing `family.5ts.io.vn` hosting or application setup.
- Removing existing production analytics, current legal notices or domain configuration without a review.

---

## 10. Suggested Agent Implementation Sequence

### Stage A — Repository audit (mandatory)

1. `git status`, inspect recent commits and existing Pages workflows.
2. Identify framework, build steps, routes and localization strategy.
3. Inventory existing components, assets, branding and content sources.
4. Capture pre-change screenshots if browser automation is available.
5. Produce a small implementation plan listing modified files and risks.

### Stage B — Structure & Content

1. Normalize content into VI/EN dictionaries/data modules where reasonable.
2. Improve hero, service descriptions, projects and CTAs.
3. Add process, AI-assisted engineering, FAQ and clearer contact section.
4. Preserve existing image attribution and honest labeling of concept illustrations.

### Stage C — UI/UX

1. Refine design tokens and typography using existing logo palette.
2. Implement mobile-first responsive layout and menu.
3. Improve spacing, card hierarchy and case study visuals.
4. Implement reduced-motion support and keyboard accessibility.

### Stage D — SEO & Quality

1. Add localized metadata, canonical, OG and structured data as appropriate.
2. Improve image loading and static asset optimization.
3. Validate semantic markup and accessibility.
4. Test direct links and deep links to all localized routes.

### Stage E — CI/CD & Release

1. Run existing lint/test/build scripts; add focused tests if absent.
2. Verify expected static deployment output and GitHub Pages compatibility.
3. Capture screenshot comparison / QA notes.
4. Open PR with a clear checklist and no DNS/hosting changes.
5. Merge after approval; monitor live page and preserve rollback commit.

---

## 11. Acceptance Criteria

- [ ] Existing public domain `https://5ts.io.vn/` unchanged.
- [ ] GitHub Pages remains the production hosting platform.
- [ ] P.A Việt Nam DNS and all subdomains unchanged.
- [ ] Current repository, source and build pipeline preserved or only safely improved.
- [ ] Vietnamese and English content both complete and consistent.
- [ ] All nav/CTAs/projects/contact links functional.
- [ ] FamilyNest Pro and GrowthInvesting links correct.
- [ ] No unsupported numerical, legal, security or marketing claims.
- [ ] AI Software Factory presented as an internal initiative under development.
- [ ] No horizontal scroll on small phones; site usable at 320 px.
- [ ] Keyboard navigation, focus states and basic screen-reader semantics validated.
- [ ] No broken assets, uncaught runtime errors or accidental secret exposure.
- [ ] Static build succeeds using the existing deployment mechanism.
- [ ] SEO metadata and localized URLs validated.
- [ ] Direct route refresh works for every published URL.
- [ ] No unreviewed production change; PR and rollback instructions provided.

---

## 12. Proposed Priorities

| Priority | Task | Expected impact | Relative effort |
|---|---|---|---|
| P0 | Verify deployment/CNAME and protect GitHub Pages | Prevent downtime | Low–Medium |
| P0 | Update hero, CTA, services and clear company positioning | Better clarity/conversion | Medium |
| P0 | Mobile nav, responsive and accessibility | Better usability | Medium |
| P1 | Richer real-product showcase/case studies | Higher credibility | Medium |
| P1 | VI/EN copy and metadata alignment | Better professionalism/SEO | Medium |
| P1 | Process + AI-assisted engineering section | Explain differentiation | Low–Medium |
| P1 | Performance, image and accessibility audit | Better site quality | Medium |
| P2 | Dedicated SEO landing pages | Search discoverability | Medium–High |
| P2 | Optional external lead form integration | Lead operations | Medium |

---

## 13. Copy-Paste Execution Prompt for Claude Code / Codex

```text
Read docs/5Tech-Website-v2-GitHub-Pages-Upgrade.md completely.

Upgrade the existing 5Tech Solutions site at https://5ts.io.vn/
according to the specification. First inspect this repository and report
its framework, GitHub Pages publishing source, build instructions, and
custom-domain handling. Preserve the current hosting on GitHub Pages,
DNS at P.A Việt Nam, and all existing subdomains. Do not migrate hosting
or require a paid platform.

Create a feature branch. Implement the revised responsive UI, Vietnamese
and English content, stronger product showcase, collaboration process,
accurate AI-assisted engineering copy, contact CTA, technical SEO and
accessibility improvements. Reuse the current framework; avoid a rewrite
unless the existing code makes it absolutely necessary and obtain approval
before such a change. Do not invent performance statistics or company facts.

Run all existing lint/test/build checks and verify static GitHub Pages
compatibility. Provide screenshots if browser automation is available.
Summarize modified files, risks, validation results, and rollback procedure.
Create a PR for human review. Do not merge or change production DNS.
```

**Suggested repository location for this file:** `docs/5Tech-Website-v2-GitHub-Pages-Upgrade.md`.

---

## 14. Reference Documentation

- Live public baseline: https://5ts.io.vn/
- GitHub — Custom domain management: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- GitHub — Publishing source: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- GitHub — GitHub Pages Actions: https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages
- Web Core Vitals: https://web.dev/articles/vitals

**End of specification.**
