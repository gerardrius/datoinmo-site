# DatoInmo Website — Build Prompt (v2)

Build me a single-page website as a single `index.html` file (inline CSS, no frameworks, no build step) for my solo data & operations consultancy targeting real estate agencies in Barcelona.

---

## BUSINESS CONTEXT

- **Business:** DatoInmo — data & operations consulting for real estate agencies
- **Founder:** Gerard Rius, ex-data analyst at Engel & Völkers España
- **Target audience:** Directors, owners, and commercial managers of real estate agencies in Barcelona and surrounding areas (Maresme, Vallès, Baix Llobregat, Garraf)
- **Competitive angle:** Not a software vendor. Not a generic consultant. An insider who's seen the data problems from inside a top-tier agency and now helps independent agencies fix the same issues — without buying enterprise software they don't need.
- **Core thesis:** Most real estate agencies in Barcelona are hemorrhaging money on portals, losing leads through slow response times, and making decisions based on gut feeling instead of data. The fix isn't more technology — it's measuring the right things and acting on them.

---

## LANGUAGES — TRILINGUAL WITH SWITCHER

The site must support **three languages**: Catalan (default), Spanish, and English.

### Language switcher behavior:
- Small, minimal switcher in the top-right corner of the nav: `CA | ES | EN`
- Active language highlighted with accent color
- Switching is instant (no page reload) — use vanilla JS to toggle `lang` attribute on `<html>` and show/hide content blocks per language using CSS classes (`.lang-ca`, `.lang-es`, `.lang-en`)
- Default language: **Catalan** (the audience is local Barcelona agencies; Catalan signals "local insider, one of us")
- Browser `lang` attribute should update on switch for accessibility
- `<html lang="ca">` by default
- Each language block uses the same semantic structure — only the text content changes

### Meta tags per language:
- Default meta description and OG tags in Catalan
- Use `hreflang` link tags for all three languages

---

## TONE & VOICE

**Direct, insider, anti-corporate.** Like a colleague who's been inside the machine telling you what's broken. Not a consultant brochure. Not a tech startup landing page.

Rules:
- Catalan: natural, colloquial, tuteja. Like talking to someone at a Collegi d'APIs event.
- Spanish: tuteo natural, professional but never stiff. Like talking over coffee, not presenting slides.
- English: confident, conversational, no buzzwords. Think: senior colleague explaining something clearly over a beer.
- No jargon without immediate payoff. If you say "lead scoring," you explain what it means in the same sentence.
- No vague promises. Every claim is specific: numbers, timeframes, outcomes.
- The founder has seen the mess from inside. The tone is: "I know exactly what's broken because I used to look at the same dashboards you're ignoring."

---

## DESIGN DIRECTION

- **No stock photos, no hero images.** Typography-driven, clean, high-contrast.
- **Aesthetic reference:** The confidence of a Stripe or Linear page, but minimal and warmer. Think: a well-designed pitch deck for one person, not a SaaS company.
- **Color palette:**
  - Background: `#0a0a0a` (near-black)
  - Primary text: `#f0f0f0` (off-white)
  - Secondary text: `#888888` (muted gray for supporting copy)
  - Accent: a single warm accent color for CTAs and highlights — suggest `#e8643a` (burnt orange) or `#d4a853` (muted gold). Something that says "real estate warmth" without being generic blue.
  - Accent hover state: slightly lighter variant
- **Google Fonts:** Use Inter for body and a slightly more characterful sans-serif for headlines (e.g., Instrument Sans, General Sans via CDN, or just Inter at different weights). If using only Inter, use weight contrast: headlines at 700, body at 400, accent text at 500.
- **Spacing:** Generous vertical rhythm. Sections should breathe. At least 120px between major sections on desktop.
- **Cards/blocks:** If using cards for services or problems, use subtle borders (`1px solid rgba(255,255,255,0.08)`) rather than background fills. No drop shadows.

---

## CTA STRATEGY

- **Single CTA throughout:** email link to `gerard@datoinmo.com`
- **All CTA buttons** → `mailto:gerard@datoinmo.com?subject=Conversa%20DatoInmo`
- **CTA button style:** Accent background, dark text, slightly rounded (4-6px radius), no uppercase transform. Should feel clickable and human, not corporate.
- **CTA appears 3 times:** hero, after services, and final section. The hero and final CTAs should be prominent buttons. The mid-page CTA can be a subtler text link.

---

## SECTIONS (top to bottom)

### 0. NAV (sticky, minimal)

- Logo: just the text "DatoInmo" in the headline font, weight 600
- Language switcher: `CA | ES | EN` — right-aligned
- No hamburger menu. No other nav links. The page is short enough to scroll.
- Background: transparent, becomes slightly opaque on scroll (subtle backdrop-blur if desired)

---

### 1. HERO

Full viewport height. Centered content. The headline is the star.

**Catalan:**
- Headline: `La teva agència genera leads. Saps quants es perden abans que algú despengi el telèfon?`
- Subheadline: `Consultoria de dades i operacions per a agències immobiliàries a Barcelona. Fundada per un ex-data analyst d'Engel & Völkers España.`
- CTA button: `Parlem 15 minuts`

**Spanish:**
- Headline: `Tu agencia genera leads. ¿Pero sabes cuántos se pierden antes de que alguien conteste?`
- Subheadline: `Consultoría de datos y operaciones para agencias inmobiliarias en Barcelona. Fundada por un ex-data analyst de Engel & Völkers España.`
- CTA button: `Hablemos 15 minutos`

**English:**
- Headline: `Your agency generates leads. Do you know how many die before anyone picks up the phone?`
- Subheadline: `Data & operations consulting for real estate agencies in Barcelona. Founded by an ex-data analyst from Engel & Völkers Spain.`
- CTA button: `Let's talk — 15 minutes`

**Design notes:**
- Headline should be large (clamp between 2.5rem and 4rem) but not shouting. It's a question — it should land like a gut punch, not a billboard.
- Subheadline in muted gray, smaller.
- CTA button centered below with comfortable spacing.
- Optional: a single subtle stat below the CTA in small text, like "La media de respuesta en agencias de Barcelona: 6 horas. La ventana de conversión: 15 minutos." / "Tiempo medio de respuesta en agencias de Barcelona: 6 horas. La ventana de conversión: 15 minutos." / "Average lead response time in Barcelona agencies: 6 hours. The conversion window: 15 minutes."

---

### 2. PROBLEMA (THE PROBLEM)

Three blocks, each with a bold statement and a short explanation. These should feel like punches — short, specific, data-informed.

**Catalan heading:** `El que veig al 90% de les agències`

**Block 1 — Velocitat de resposta:**
- CA: `Leads que triguen més de 4 hores a rebre resposta — quan la finestra real és de 15 minuts.`
- ES: `Leads que tardan más de 4 horas en recibir respuesta — cuando la ventana real es de 15 minutos.`
- EN: `Leads that wait 4+ hours for a reply — when the real window is 15 minutes.`

**Block 2 — Cost opac dels portals:**
- CA: `Milers d'euros al mes en portals sense saber quin porta compradors reals i quin porta turistes immobiliaris.`
- ES: `Miles de euros al mes en portales sin saber cuál trae compradores reales y cuál trae turistas inmobiliarios.`
- EN: `Thousands per month on listing portals with no idea which ones bring real buyers and which bring property tourists.`

**Block 3 — CRM cementiri:**
- CA: `Un CRM ple de contactes duplicats, sense etiquetes, sense seguiment — un cementiri d'oportunitats.`
- ES: `Un CRM lleno de contactos duplicados, sin etiquetas, sin seguimiento — un cementerio de oportunidades.`
- EN: `A CRM full of duplicate contacts, no tags, no follow-up — a graveyard of missed opportunities.`

**Design notes:**
- These three blocks should be visually distinct — either stacked vertically with generous spacing, or in a 3-column grid on desktop that collapses to stacked on mobile.
- Each block could have a subtle left border in the accent color, or a small icon/number. But no decorative icons — if you number them, use the numbers meaningfully (they represent common failure points, not a process).
- Optional addition — a small line after all three blocks: "Cap d'aquests problemes requereix més tecnologia. Requereix mesurar el que importa." / "Ninguno de estos problemas necesita más tecnología. Necesita medir lo que importa." / "None of these problems need more technology. They need measuring what matters."

---

### 3. SERVEIS (WHAT I DO)

Three service offerings. Each with a name, a one-liner description, and 2-3 bullet points of what's concretely included.

**Catalan heading:** `Tres serveis concrets`
**Spanish heading:** `Tres servicios concretos`
**English heading:** `Three concrete services`

**Service 1 — Auditoria de CRM:**

- CA:
  - Title: `Auditoria de CRM`
  - Description: `Netejo, estructuro i poso regles perquè la teva base de dades funcioni com a eina de venda, no com a magatzem de noms.`
  - Details: `Deduplicació de contactes · Taxonomia d'etiquetes per fase i canal · Regles d'assignació i seguiment automàtic · Resultat: un CRM que et diu exactament on estan els teus leads i qui se n'ha d'ocupar.`

- ES:
  - Title: `Auditoría de CRM`
  - Description: `Limpio, estructuro y pongo reglas para que tu base de datos funcione como herramienta de venta, no como almacén de nombres.`
  - Details: `Deduplicación de contactos · Taxonomía de etiquetas por fase y canal · Reglas de asignación y seguimiento automático · Resultado: un CRM que te dice exactamente dónde están tus leads y quién debe ocuparse.`

- EN:
  - Title: `CRM Audit`
  - Description: `I clean, structure, and set rules so your database works as a sales tool, not a warehouse of names.`
  - Details: `Contact deduplication · Tag taxonomy by stage and channel · Auto-assignment and follow-up rules · Result: a CRM that tells you exactly where your leads are and who should be handling them.`

**Service 2 — Anàlisi de rendiment de portals:**

- CA:
  - Title: `Anàlisi de rendiment de portals`
  - Description: `Mesuro cost per lead real, taxa de conversió i ROI de cada portal perquè deixis de pagar a cegues.`
  - Details: `Connexió de dades portal → CRM → venda · Cost per lead qualificat (no per clic) · Comparativa entre portals amb dades reals · Resultat: saps exactament on invertir i on tallar.`

- ES:
  - Title: `Análisis de rendimiento de portales`
  - Description: `Mido coste por lead real, tasa de conversión y ROI de cada portal para que dejes de pagar a ciegas.`
  - Details: `Conexión de datos portal → CRM → venta · Coste por lead cualificado (no por clic) · Comparativa entre portales con datos reales · Resultado: sabes exactamente dónde invertir y dónde cortar.`

- EN:
  - Title: `Portal performance analysis`
  - Description: `I measure real cost per lead, conversion rate, and ROI per portal so you stop paying blind.`
  - Details: `Data pipeline: portal → CRM → closed deal · Cost per qualified lead (not per click) · Portal comparison with real numbers · Result: you know exactly where to invest and where to cut.`

**Service 3 — Dashboard d'operacions:**

- CA:
  - Title: `Dashboard d'operacions`
  - Description: `Un panell clar amb els 5-6 números que un director d'agència necessita veure cada dilluns al matí.`
  - Details: `Leads nous vs contactats · Temps de resposta per agent · Pipeline per fase · Conversió per canal · Resultat: en 2 minuts saps com va l'agència sense preguntar a ningú.`

- ES:
  - Title: `Dashboard de operaciones`
  - Description: `Un panel claro con los 5-6 números que un director de agencia necesita ver cada lunes por la mañana.`
  - Details: `Leads nuevos vs contactados · Tiempo de respuesta por agente · Pipeline por fase · Conversión por canal · Resultado: en 2 minutos sabes cómo va la agencia sin preguntar a nadie.`

- EN:
  - Title: `Operations dashboard`
  - Description: `A clean panel with the 5-6 numbers an agency director needs to see every Monday morning.`
  - Details: `New leads vs contacted · Response time per agent · Pipeline by stage · Conversion by channel · Result: in 2 minutes you know how the agency is doing without asking anyone.`

**Design notes:**
- Each service is a card or block with clear visual separation.
- Service title in accent color or bold white, description in body text, details in slightly smaller/muted text.
- A subtle CTA line after the three services: "Cada projecte comença amb una conversa de 15 minuts." / "Cada proyecto empieza con una conversación de 15 minutos." / "Every project starts with a 15-minute conversation." — linked to mailto.

---

### 4. COM TREBALLO (HOW I WORK) — Optional but recommended

A short section showing the process. 3 steps, not dressed up — just honest.

**Catalan heading:** `Com funciona`
**Spanish heading:** `Cómo funciona`
**English heading:** `How it works`

**Step 1:**
- CA: `Conversa inicial (15 min, gratuïta)` — `Em parles de la teva agència, els teus canals i el teu CRM. Jo et dic on veig problemes i si puc ajudar.`
- ES: `Conversación inicial (15 min, gratis)` — `Me cuentas sobre tu agencia, tus canales y tu CRM. Yo te digo dónde veo problemas y si puedo ayudar.`
- EN: `Initial call (15 min, free)` — `You tell me about your agency, your channels, and your CRM. I tell you where I see problems and whether I can help.`

**Step 2:**
- CA: `Diagnòstic i proposta (1 setmana)` — `Analitzo les teves dades, et presento els troballes i et faig una proposta concreta amb cost i terminis.`
- ES: `Diagnóstico y propuesta (1 semana)` — `Analizo tus datos, te presento los hallazgos y te hago una propuesta concreta con coste y plazos.`
- EN: `Diagnosis and proposal (1 week)` — `I analyze your data, present findings, and give you a concrete proposal with cost and timeline.`

**Step 3:**
- CA: `Execució i transferència` — `Munto el sistema, te l'ensenyo a usar i et deixo documentació. Res de dependència: l'objectiu és que no em necessitis.`
- ES: `Ejecución y transferencia` — `Monto el sistema, te enseño a usarlo y te dejo documentación. Nada de dependencia: el objetivo es que no me necesites.`
- EN: `Execution and handoff` — `I build the system, teach you to use it, and leave documentation. No lock-in: the goal is that you don't need me.`

---

### 5. QUI SÓC (WHO I AM)

Personal, credible, brief. No photo needed (but allow space for one if added later).

**Catalan:**
- Heading: `Qui sóc`
- Text: `Sóc en Gerard Rius. Vaig treballar com a data analyst a Engel & Völkers España, on vaig analitzar el rendiment comercial d'agències a Barcelona. Ara ajudo directors d'agències independents a prendre decisions amb dades en lloc d'intuïció.`
- Text 2: `No venc software. No venc fum. Munto els sistemes de mesurament que la teva agència necessita i t'ensenyo a fer-los servir.`

**Spanish:**
- Heading: `Quién soy`
- Text: `Soy Gerard Rius. Trabajé como data analyst en Engel & Völkers España, donde analicé el rendimiento comercial de agencias en Barcelona. Ahora ayudo a directores de agencia independientes a tomar decisiones con datos en lugar de con intuición.`
- Text 2: `No vendo software. No vendo humo. Monto los sistemas de medición que tu agencia necesita y te enseño a usarlos.`

**English:**
- Heading: `Who I am`
- Text: `I'm Gerard Rius. I worked as a data analyst at Engel & Völkers Spain, where I analyzed commercial performance for agencies in Barcelona. Now I help independent agency directors make decisions with data instead of gut feeling.`
- Text 2: `I don't sell software. I don't sell smoke. I build the measurement systems your agency needs and I teach you how to use them.`

**Design notes:**
- This can be a simple text block, slightly indented or with a subtle left accent border.
- The "No venc software" / "No vendo software" paragraph should have slightly more visual weight — it's the differentiator.

---

### 6. CTA FINAL

Full-width section, generous padding. This is the closing — make it warm and inviting.

**Catalan:**
- Headline: `Vols saber què diuen les teves dades?`
- Subtext: `Escriu-me i fem una primera conversa de 15 minuts sense compromís.`
- Button: `gerard@datoinmo.com`

**Spanish:**
- Headline: `¿Quieres saber qué dicen tus datos?`
- Subtext: `Escríbeme y hacemos una primera conversación de 15 minutos sin compromiso.`
- Button: `gerard@datoinmo.com`

**English:**
- Headline: `Want to know what your data is telling you?`
- Subtext: `Write me and we'll have a first 15-minute conversation, no strings attached.`
- Button: `gerard@datoinmo.com`

---

### 7. FOOTER

Minimal, one line.

- `© 2025 DatoInmo — Gerard Rius — Barcelona`
- Language does not change in footer (it's just a name and location).

---

## TECHNICAL REQUIREMENTS

### Must-haves:
- Single `index.html` file, everything inline (CSS in `<style>`, JS in `<script>`)
- Responsive (mobile-first approach, breakpoint at ~768px)
- Smooth scroll between sections (`scroll-behavior: smooth`)
- Subtle entrance animations (CSS only using `@keyframes` and `IntersectionObserver` in vanilla JS — no libraries)
- Semantic HTML5 (`<header>`, `<main>`, `<section>`, `<footer>`)
- Fast: no external dependencies except Google Fonts (loaded with `display=swap`)
- Language switching via vanilla JS (no page reload, toggle visibility of `.lang-ca`, `.lang-es`, `.lang-en` elements)
- Active language stored in `localStorage` so returning visitors see their last choice
- `<html lang="ca">` updates dynamically on switch

### Meta tags:
- `<meta name="description">` in Catalan (default)
- Open Graph tags: `og:title`, `og:description`, `og:type` (website), `og:url`, `og:locale` (ca_ES)
- `<link rel="alternate" hreflang="ca" href="...">` (and es, en)
- `<meta name="viewport" content="width=device-width, initial-scale=1">`
- Favicon: use a simple inline SVG favicon via `<link rel="icon" type="image/svg+xml" href="data:image/svg+xml,...">` — just the letter "D" in the accent color

### Accessibility:
- All interactive elements keyboard-accessible
- Sufficient color contrast (check accent color against dark background)
- `aria-label` on language switcher buttons
- `prefers-reduced-motion` media query to disable animations

### Performance:
- No images to load
- CSS animations only (no JS animation libraries)
- Google Fonts loaded asynchronously
- Total page weight target: under 50KB (excluding fonts)

---

## WHAT TO AVOID

- No testimonials section (I don't have clients yet to quote — I'd rather have nothing than fake social proof)
- No pricing section (pricing is custom per project, discussed in the initial call)
- No blog link (doesn't exist yet)
- No social media links (LinkedIn only if added, but not required)
- No cookie banner (no tracking, no cookies except localStorage for language preference)
- No animations that feel "techy" or startup-y (no gradient text, no floating particles, no parallax)
- No "trusted by" logos section
- No generic stock illustrations or abstract shapes
- No hamburger menu
- Don't number the problem blocks as "01 / 02 / 03" — they're not a sequence, they're independent failure points

---

## OPTIONAL ENHANCEMENTS (implement if they improve the page, skip if they add bloat)

- A subtle horizontal rule or visual separator between sections (e.g., a thin line at 10% opacity)
- A small "↑" back-to-top button that appears after scrolling past the hero
- Hover effect on CTA buttons: slight scale + lighter accent color
- The hero headline could have the key phrase ("quants es perden" / "cuántos se pierden" / "how many die") in the accent color for emphasis — but only if it doesn't feel gimmicky
- A very subtle grid or dot pattern on the background at extremely low opacity (2-3%) for texture — but only if it doesn't slow anything down
