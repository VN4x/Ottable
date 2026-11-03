# Website Audit & Modernization Plan: estplast.ee

## Executive Summary
`https://estplast.ee/` is the corporate and product website for **Estplast Tootmine OÜ** (part of the Finnfoam OY group), an Estonian manufacturer of EPS (expanded polystyrene) insulation boards. While the site holds strong technical documentation (CAD/DWG drawings, Declarations of Performance, EPDs) and deep educational content on EPS manufacturing and testing, its technical execution, information architecture, design, SEO, and GEO (Generative Engine Optimization) suffer from severe legacy debt (c. 2019 Elementor 2.5 build).

---

## 1. Design & UX Analysis

### Strengths
- **Brand Consistency:** Uses a recognizable green (`#007548`) and neutral gray (`#54595f`) palette aligned with Estplast's physical packaging.
- **Direct Product Grid:** All 13 core EPS products and 5 construction application areas are immediately visible on the homepage without deep click-paths.
- **Group Cross-Promotion:** Clear visual links to parent/sister brands (Finnfoam and Warmotech).

### Weaknesses
- **Severe Navigation Duplication:** Every page renders **three separate navigation menus** simultaneously on desktop:
  1. A full horizontal top bar (`FIRMAST`, `TOOTED`, `KONTAKT`, etc.).
  2. An identical vertical left sidebar menu repeating the exact same items.
  3. A secondary application menu below the sidebar (`Karkasskonstruktsioonid`, `Fassaadid`, `Katused`, `Põrandad`) that is incongruously set to collapse into a hamburger toggle.
- **Outdated Visual Assets & Layout Hacks:**
  - The main brand logo is a low-resolution `204x71` `.gif` file from 2019 (`logo.gif`).
  - The left sidebar uses a decorative background image (`couple.png`) with a hardcoded `250px` bottom padding hack.
  - Empty 20%-width spacer columns are used on desktop to center a 3-item product row inside a 5-column grid.
  - Negative letter-spacing (`-0.9px`) and cramped padding (`3px`) are used to force long product names onto buttons.
- **Broken & Misconfigured Interactive Elements:**
  - On the homepage, the **"Vundamendid" (Foundations)** application card has `href="#"`—clicking it does nothing, even though `/est/plaatvundament/` and `/est/tehnovorgud/` exist in the sitemap.
  - Header logos (`estplast.ee`, `warmotech.com`, `finnfoam.ee`) have `data-elementor-open-lightbox=""` enabled on their anchor tags.
  - The Warmotech logo in the header links to `https://www.warmotech.com/.` (with a trailing dot) on the homepage and `https://www.warmotech.lt/ee` on subpages.
- **Poor Mobile & Document UX:**
  - Product specifications and Declarations of Performance (DoP) are embedded inside `<object type="application/pdf">` tags within Elementor tabs. Mobile browsers largely fail to render inline PDF `<object>` embeds, showing fallback text in English: *"It appears you don't have a PDF plugin for this browser. No biggie… you can click here to download the PDF file."*
  - Contact page (`https://estplast.ee/est/kontakt/`) embeds a fixed `width="640" height="480"` Google MyMaps `<iframe>` that overflows narrow mobile viewports, and has no contact/inquiry form or clickable `tel:` / `mailto:` links.

---

## 2. Structure & Information Architecture

### Strengths
- **Logical Dual Taxonomy:** Categorizes offerings both by **Product Type** (`EPS 60` through `EPS 250`) and by **Construction Application** (Facades, Roofs, Floors, Frame structures, Foundations).
- **Bilingual Coverage:** Full Estonian (`/est/`) and Russian (`/rus/`) trees covering products, guides, and reseller directories.

### Weaknesses
- **Inconsistent URL Hierarchy & Routing:**
  - Homepage is at `/`, Estonian subpages are under `/est/...`, but homepage CTA banners link to root-level slugs (`/karkasskonstruktsioonid/`, `/fassaadid/`, `/ff-floor-eps-100s/`) which rely on WordPress slug guessing or serve duplicate content at non-canonical paths.
  - Submenu anchor links under "MIS ON EPS?" point to `/mis-on-eps/#omadused` instead of `/est/mis-on-eps/#omadused`.
- **Context-Losing Language Switcher:** The `EST | РУС` switcher is hardcoded to `/` and `/rus`. Switching language on a specific product page (e.g., `/est/eps-60/`) dumps the user back to the Russian homepage (`/rus`) instead of `/rus/eps-60/`.
- **Orphaned & Semi-Orphaned Pages:**
  - `/est/sertifikaadid/` (containing all DoP certificates, including `EPS 50` and `EPS 70 Fassaad`), `/est/plaatvundament/`, and `/est/tehnovorgud/` exist in the sitemap but are missing from the main navigation or unlinked on the homepage.
  - The Russian menu omits the Environmental Product Declaration (`KESKKONNADEKLARATSIOON`) page entirely.
  - Typo in Russian URL slug: `https://estplast.ee/rus/поff-floor-eps-100s/` (`%d0%bf%d0%beff-floor-eps-100s`).
- **Unhygienic File Paths:** PDFs and DWG files are hosted at `/pdf/...` with spaces, parentheses, and umlauts in filenames (e.g., `/pdf/04 Keldri seina (vundamendi) soojustus.pdf?rand=9255`) and a hardcoded `?rand=9255` query string instead of proper cache-Control versioning.

---

## 3. SEO (Search Engine Optimization) Analysis

### Strengths
- **Clean Core Product Slugs:** Estonian product URLs (`/est/eps-60/`, `/est/eps-100-silver/`) match exact high-intent search queries in the local construction market.
- **High-Value Educational Content:** `/est/mis-on-eps/` and `/est/kasulikku/` contain rich, original Estonian technical text explaining EPS manufacturing, thermal conductivity, and window installation with thermal profiles.

### Weaknesses
- **Critical `<html lang="en-US">` Mismatch:** Every page—both Estonian and Russian—declares `<html lang="en-US">`. Search engines, browsers, and screen readers are told the site is in US English, triggering inappropriate browser auto-translate prompts and hurting regional language indexing.
- **Zero SEO Plugin / Meta Tag Infrastructure:**
  - **No `<meta name="description">`** on any page.
  - **No OpenGraph (`og:*`) or Twitter Card tags** for social/messaging link previews.
  - **Weak `<title>` tags:** The Russian homepage title is literally `<title>RUS – ESTPLAST</title>`. Product pages have bare titles like `<title>EPS 60 – ESTPLAST</title>` without keywords like *soojustusplaadid*, *vahtpolüstüreen*, or *fassaadiplaat*.
- **Zero `hreflang` Implementation:** There are no `<link rel="alternate" hreflang="et" ...>` or `hreflang="ru"` tags linking the Estonian and Russian equivalents.
- **Broken Heading Hierarchy (No `<h1>` Tags):**
  - The homepage has **zero `<h1>`–`<h6>` headings**—only buttons and images.
  - Product pages (`EPS 60`, etc.) have **zero `<h1>` headings**; product titles only exist inside Elementor tab navigation links (`<div class="elementor-tab-title">`).
  - Content pages (`MIS ON EPS?`, `KONTAKT`) jump straight to `<h4>` and `<h5>` tags without `<h1>`, `<h2>`, or `<h3>`.
- **Trapped Technical Content (PDF Silos):** Crucial product specs (lambda values $\lambda_D$, compressive strength kPa, sheet dimensions, package $m^2$/$m^3$ tables) are locked inside PDF files (`<object data="/pdf/EPS 60.pdf">`) rather than HTML tables. On `/est/eps-60/`, the main tab contains only a single product image and zero HTML text.
- **Empty Image `alt` Attributes:** Virtually every `<img>` tag across the site (including all logos and all 13 product images) has `alt=""`.
- **Sitemap Pollution & Bloat:**
  - `wp-sitemap.xml` exposes **`wp-sitemap-posts-elementor_library-1.xml`**, indexing 31 internal Elementor layout fragments (`?elementor_library=logo`, `?elementor_library=nav-left-lat`, including abandoned Latvian/Lithuanian templates) as public crawlable pages.
  - `wp-sitemap-users-1.xml` exposes the admin author archive (`/author/andreisurflink-ee/`).

---

## 4. GEO (Generative Engine Optimization / AI Search) & Local SEO

### Strengths
- **Authoritative First-Party Facts:** Specific facts on `/est/mis-on-eps/` (e.g., testing every 2 hours with a Tinius Olsen H5K-T UTM machine to EVS-EN 13163 standards; 5-stage expansion and stabilization process) are strong citeable facts for LLMs.
- **Comprehensive Reseller Directory:** `/est/edasimuujad/` maps retail availability across 11 Estonian counties.

### Weaknesses
- **Zero Structured Data (Schema.org JSON-LD):** There is no `Organization`, `LocalBusiness`, `ManufacturingBusiness`, `Product`, `BreadcrumbList`, or `FAQPage` JSON-LD anywhere on the site. AI engines and Google Rich Results have no machine-readable entity graph for Estplast or its products.
- **Machine-Unfriendly Product Specs:** Because technical specifications on product pages are inside embedded PDFs rather than semantic HTML `<table>` elements, AI search crawlers (ChatGPT Search, Perplexity, Google AI Overviews) that fetch page HTML see zero technical parameters on `/est/eps-60/`.
- **No `llms.txt`:** `/llms.txt` returns `404`, missing an opportunity to provide a concise markdown index of products, technical specs, DoP certificates, and CAD drawings for AI agents.
- **Inconsistent Reseller & Contact Formatting:** Phone numbers on `/est/kontakt/` and `/est/edasimuujad/` mix formats (`6 088 751`, `+372 510 0494`, `32 781 85`) without `tel:` links or structured `LocalBusiness` / `Store` markup.

---

## 5. Technology, Performance & Security

### Strengths
- **Lightweight Server Response:** Static HTML pages are relatively small and served quickly.
- **XML-RPC Blocked:** `/xmlrpc.php` returns `403 Forbidden`, mitigating brute-force amplification attacks.

### Weaknesses
- **Severely Outdated Plugin & Theme Stack:**
  - **Elementor `v2.5.4` & Elementor Pro `v2.4.7`** (released in **2019**, over 7 years outdated) running on WordPress `6.6.11` with default theme `Twenty Nineteen v1.3`. Running 2019 Elementor versions poses high security and PHP compatibility risks.
  - **Font Awesome `4.7.0`** (legacy icon font).
- **DOM & Script Bloat:**
  - Duplicating the 25-item navigation menu 6 times in the DOM (3 menus $\times$ 2 desktop/mobile containers per widget) inflates the HTML node count on every page.
  - Loads Gutenberg block library CSS (`wp-block-library`) and `global-styles-inline-css` alongside Elementor CSS even though pages use `elementor_canvas`.
  - Loads Google Fonts (`Roboto` and `Roboto Slab`) with **all 18 font weights/styles** (`100` through `900italic`), causing unnecessary render-blocking font downloads.
- **Security & Privacy Gaps:**
  - **User Enumeration Exposed:** `/wp-json/wp/v2/users` is publicly accessible and leaks the administrator's email address as the username/display name (`andrei@surflink.ee`).
  - **Mixed Content Outbound Links:** Reseller links on `/est/edasimuujad/` use insecure `http://` URLs (`http://www.bauhof.ee/`, `http://www.optimera.ee`, etc.).
  - **Missing Legal/Privacy Compliance:** No Privacy Policy, Cookie Policy, or terms link in the footer despite loading third-party analytics (`siteimproveanalytics.com`) and Google Maps iframes.

---

## 6. Prioritized Action Plan (Roadmap)

### Phase 1: Critical SEO, Security & Broken UX Fixes (Immediate)
1. **Fix Language Declarations & Hreflang:** Install a proper multilingual/SEO plugin (e.g., Polylang/WPML + Yoast/RankMath) so Estonian pages output `<html lang="et">`, Russian pages output `<html lang="ru">`, and bidirectional `hreflang` tags connect corresponding pages.
2. **Clean Up Sitemaps & User Enumeration:**
   - Exclude `elementor_library` custom post types and `users` archives from `wp-sitemap.xml`.
   - Restrict `/wp-json/wp/v2/users` to authenticated requests and change the admin display name from an email address.
3. **Fix Broken Links & Lightbox Bugs:**
   - Point the homepage "Vundamendid" card (`href="#"`) to `/est/plaatvundament/`.
   - Remove `data-elementor-open-lightbox` from header logo links and fix `https://www.warmotech.com/.` trailing dot.
   - Standardize all internal links to canonical `/est/...` paths and fix the Russian slug typo (`/rus/ff-floor-eps-100s/`).

### Phase 2: Content Un-Siloing, Semantic HTML & GEO Optimization
1. **Convert PDF Product Specs into Semantic HTML:** On all 13 product pages (`/est/eps-60/`, etc.), render technical parameters ($\lambda_D$, compressive strength, dimensions, fire class, application uses) directly as HTML `<table>` and text on the primary view, keeping PDFs as downloadable buttons (`Tooteleht PDF`, `Toimivusdeklaratsioon PDF`).
2. **Restore Semantic Heading Hierarchy & Alt Text:**
   - Add a clear `<h1>` to the homepage and every product/content page.
   - Populate descriptive Estonian and Russian `alt` attributes for all product and diagram images.
3. **Implement Schema.org JSON-LD & `/llms.txt`:**
   - Add `ManufacturingBusiness` schema on the homepage/contact page and `Product` schema on all EPS product pages.
   - Publish `/llms.txt` summarizing Estplast's product line, technical ratings, and documentation URLs for AI engines.

### Phase 3: Design, Navigation & Tech Stack Modernization
1. **Consolidate Navigation:** Remove the redundant left vertical menu and secondary hamburger menu; unify into a single responsive header navigation with a page-aware `ET | RU | EN` language switcher.
2. **Modernize Stack & Assets:**
   - Upgrade WordPress, PHP, theme, and Elementor (or migrate to native WordPress Block Editor / GeneratePress for a zero-bloat footprint) in a staging environment.
   - Replace `logo.gif` with an SVG logo, convert product photos to WebP, and restrict Google Fonts to weights `400`, `500`, and `700`.
3. **Upgrade Contact & Conversion UX:** Add clickable `tel:` and `mailto:` links, a responsive Google Map embed, a B2B quote/technical inquiry form, and a GDPR-compliant privacy notice.
