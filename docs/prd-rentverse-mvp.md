# RentVerse MVP — Product Requirements Document

**Version:** 0.1  
**Status:** Draft  
**Scope:** Frontend MVP (concept derived from README; not a full implementation spec.)

---

## Product Summary

RentVerse is a **real estate investment platform** that combines traditional property investing with **cryptocurrency payments**. The product is inspired by Arrived.com and adds blockchain-based transaction capabilities. The MVP focuses on a **responsive, frontend-led experience** with property discovery, 3D visualization, and wallet-ready flows—with backend/blockchain integration scoped for later phases.

**Ambiguity:** The README does not specify whether MVP includes live payments, real smart contracts, or only UI/UX for “crypto-enabled” flows. This PRD assumes **UI-first MVP** with wallet connect and placeholder/mock transaction flows unless otherwise decided.

---

## Goals

1. **Validate demand:** Ship a usable frontend that demonstrates property browsing, 3D viewing, and a path to crypto payment.
2. **Establish product feel:** Match the README’s “next-generation real-estate experience” with clear information architecture and modern UI.
3. **Enable iteration:** Lay a frontend foundation (routing, components, 3D, theming) that can later connect to real APIs and chains.
4. **Stay lean:** Prioritize a small set of pages and flows; defer advanced features (e.g. real-time market data, full smart-contract flows) to post-MVP.

---

## Problem Statement

- **Investors** lack a single place to discover fractional real estate and understand offerings in a clear, trustworthy way.
- **Crypto-native users** want to use wallets and crypto for property investment but lack simple, property-first experiences (vs. DeFi-first).
- **Trust and clarity** are missing: property details, returns, and process are often scattered; 3D and clear copy can help.

The MVP addresses these by providing a **focused property discovery and 3D experience** with a visible path to wallet connection and (mock or real) crypto-based investment.

---

## Target Users

| Segment | Description | MVP Relevance |
|--------|-------------|----------------|
| **Retail investors** | Individuals looking for fractional real estate, possibly with crypto. | Primary: browse, compare, view 3D, understand ROI. |
| **Crypto-native users** | Holders comfortable with wallets (e.g. MetaMask, Phantom, Trust). | Primary: connect wallet, see “crypto-enabled” flows. |
| **Curious visitors** | People exploring the concept without committing. | Secondary: content (About, FAQ, Blog), no login required. |

**Ambiguity:** README mentions “VeChain wallet” in FAQ and “Metamask, Phantom, OKX, Trust” elsewhere. MVP should support at least one wallet (e.g. MetaMask) for connect; multi-chain strategy is an open question.

---

## User Jobs

1. **Discover:** Find and compare properties (list, filters, search).
2. **Understand:** See property details, ROI, and location; build confidence.
3. **Experience:** View properties in 3D to assess layout and feel.
4. **Prepare to invest:** See how to invest (steps, wallet connect, minimums); in MVP this may be UI-only.
5. **Learn and trust:** Read About, FAQ, Blog, Privacy to understand the platform.

---

## MVP Scope

### In scope (frontend MVP)

- **Pages:** Home, Properties (list + detail), Property 3D viewer, About, FAQ, Privacy, Blog (list + post), 404.
- **Property experience:** Search/filter on list; property cards; detail page with key metrics; 3D viewer (Three.js / R3F).
- **Wallet:** “Connect” entry point (navbar/CTA); connect flow (one wallet for MVP); display connection state (connected address / disconnect). No real payments required for MVP.
- **Content:** Static or CMS-ready structure for About, FAQ, Blog, Privacy; no backend content API required for MVP.
- **UI/UX:** Responsive layout, consistent design tokens, accessible navigation and CTAs.
- **Tech:** TypeScript, Tailwind, React Router, Three.js + React Three Fiber for 3D.

### Out of scope (post-MVP or explicit follow-up)

- Real payments and on-chain transactions.
- Smart contract integration (beyond UI placeholders).
- Real-time market data feeds.
- User accounts, auth, and portfolios (beyond wallet connect).
- Admin or partner dashboards.
- Native mobile apps (responsive web only for MVP).

---

## Feature Breakdown by Page

### Home

| Feature | Description | Priority |
|--------|-------------|----------|
| Hero | Value proposition, primary CTA (e.g. “Browse properties” or “Connect wallet”). | P0 |
| Featured properties | Grid/cards of 3–6 properties with image, title, price/ROI, CTA. | P0 |
| Why choose us | Benefits (e.g. crypto payments, transparency, 3D viewing). | P1 |
| How it works | 3–4 step guide (e.g. Connect wallet → Choose property → Invest). | P0 |
| Blog preview | Latest 2–3 posts with links to Blog. | P1 |
| Community / social | Optional; link to Discord/social if available. | P2 |

### Properties

| Feature | Description | Priority |
|--------|-------------|----------|
| Property grid | Cards with image, title, location, price/ROI, status. | P0 |
| Search | Text search (e.g. by name/location). | P0 |
| Filters | Basic filters (e.g. price range, ROI range, status). | P1 |
| Sort | Sort by price, ROI, newest. | P1 |
| 3D entry | Per-card or list-level “View in 3D” linking to Property 3D page. | P0 |
| Pagination or load more | If list is long. | P1 |

### Property Detail

| Feature | Description | Priority |
|--------|-------------|----------|
| Gallery / hero image | Main image or small gallery. | P0 |
| Key metrics | Price, ROI, minimum investment, funding status. | P0 |
| Description | Copy about the property. | P0 |
| CTA | “Invest” or “View in 3D” (and optionally “Connect wallet” if not connected). | P0 |
| Location / map | Optional for MVP. | P2 |

### Property 3D

| Feature | Description | Priority |
|--------|-------------|----------|
| 3D viewer | Three.js / R3F scene; load property model (e.g. GLB). | P0 |
| Controls | Orbit/pan/zoom (or equivalent). | P0 |
| Property context | Overlay or panel with name, key metric, CTA. | P0 |
| Navigation back | Return to list or detail. | P0 |

### About

| Feature | Description | Priority |
|--------|-------------|----------|
| Mission / vision | Short narrative. | P0 |
| Team | Names, roles, optional photos. | P1 |
| Stats / milestones | Optional (e.g. “X properties”, “Y investors”). | P2 |

### FAQ

| Feature | Description | Priority |
|--------|-------------|----------|
| Accordion or list | Questions and answers (crypto, process, wallets). | P0 |

### Privacy

| Feature | Description | Priority |
|--------|-------------|----------|
| Policy content | Sections (data collected, wallet usage, cookies, etc.). | P0 |

### Blog

| Feature | Description | Priority |
|--------|-------------|----------|
| Post list | Titles, excerpts, dates, optional featured image. | P0 |
| Category filter | Optional. | P1 |
| Search | Optional. | P2 |
| Post page | Full content, optional author and social share. | P0 |

### Global

| Feature | Description | Priority |
|--------|-------------|----------|
| Navbar | Logo, main links (Home, Properties, About, FAQ, Blog), Connect button. | P0 |
| Footer | Links, contact, optional social. | P0 |
| Wallet connect | Modal or inline flow; show address when connected; disconnect. | P0 |
| 404 | Clear message and link back home. | P0 |

---

## Functional Requirements

- **FR-1** User can open Home, Properties, Property Detail, Property 3D, About, FAQ, Privacy, Blog (list + post) and 404 via navigation or direct URL.
- **FR-2** User can search and filter the property list (at least search; filters/sort as P1).
- **FR-3** User can open a property’s 3D view from the list or detail page and interact with the 3D scene (orbit/zoom).
- **FR-4** User can trigger “Connect wallet” and see connection state (connected/disconnected, optional address truncation).
- **FR-5** Property cards and detail show: title, location, price/ROI, and a clear CTA (e.g. “View in 3D”, “Invest”).
- **FR-6** Blog list and post pages render content; post URLs are stable (e.g. by slug or id).
- **FR-7** All primary flows work on viewports from mobile to desktop (responsive).
- **FR-8** No hard dependency on backend for core navigation and 3D; property data can be mock/static for MVP.

---

## Non-Functional Requirements

- **NFR-1 Performance:** Initial load and route changes feel responsive; 3D scene loads within a few seconds on mid-range devices.
- **NFR-2 Accessibility:** Semantic HTML, focus order, and sufficient contrast; aim for WCAG 2.1 AA where feasible.
- **NFR-3 SEO:** Title and meta per page; server-side or client-side rendering as chosen (e.g. CRA + meta tags).
- **NFR-4 Browser support:** Modern evergreen (Chrome, Firefox, Safari, Edge); no IE.
- **NFR-5 Maintainability:** TypeScript for type safety; shared design tokens (e.g. Tailwind theme); component structure that can grow into a design system.

---

## Assumptions

- README describes desired product direction, not final implementation; MVP may use mock data and placeholder wallet behavior.
- One wallet provider (e.g. MetaMask) is enough for MVP; multi-chain can follow.
- Property and blog content can be static or from a simple API; no complex CMS required for MVP.
- 3D models (e.g. GLB) are provided or chosen per property; no auto-generation in MVP.
- Team has design inputs (brand, layout) or will use existing RentVerse styling (e.g. primary/secondary tokens) for consistency.
- Backend and smart contracts are out of scope for this frontend MVP; integration points can be stubbed.

---

## Open Questions

1. **Wallet:** Which wallet(s) and chain(s) are in scope for MVP (e.g. MetaMask + Ethereum only)?
2. **Data:** Will property (and blog) data come from an API, static JSON, or hardcoded content?
3. **Auth:** Is “Connect wallet” the only identity for MVP, or will there be email/account later?
4. **Invest flow:** Should “Invest” open a modal with steps and mock success, or only navigate to a dedicated page?
5. **3D assets:** Who provides GLB (or other) models, and how are they mapped to properties (e.g. by property id)?
6. **Real-time data:** Is “real-time market data” (README) a future phase only, or should MVP show any live data (e.g. price ticker)?

---

## Success Criteria

- **Launch readiness:** All P0 features for Home, Properties, Property Detail, Property 3D, About, FAQ, Privacy, Blog, and global nav/footer are implemented and usable.
- **3D:** At least one property has a working 3D view with orbit/zoom and a clear way back to list/detail.
- **Wallet:** User can connect and disconnect a wallet and see state in the UI.
- **Quality:** No critical bugs on primary flows; responsive on mobile and desktop.
- **Foundation:** Codebase is in TypeScript, uses Tailwind for styling, and uses Three.js + R3F for 3D; structure supports adding real API and wallet logic later.

---

*This PRD is a living document. Update as scope and open questions are resolved.*
