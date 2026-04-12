# Personal Website — Jaehong Kim

## Project

Academic personal website for Jaehong Kim, Ph.D. candidate at KAIST.
Hosted on GitHub Pages: jaehong-k.github.io

---

## Design

Linear-style: clean, minimal, professional. Inspired by linear.app.
Full design token reference → see DESIGN.md.

- Font: -apple-system / Apple SD Gothic Neo (system font, no external dependency)
- Background: #F5F3F0 (Cloud Dancer — Pantone Color of the Year 2026, warm soft white)
- Text: #0A0A0A — Secondary: #6b6860 (warm gray, not cool) — Body: #374151 — Border: #E2DDD8
- Accent: #4f46e5 (indigo) — Accent bg: #eef2ff
- Layout: single-column, centered, max-width 720px
- Hover transitions only (no scroll animations, no page transitions)
- Fully responsive, mobile-first (breakpoint: 580px)
- No heavy JS frameworks — pure HTML/CSS/JS

Writing style in all copy: plain, direct English. No LLM-style words (notably, furthermore, crucially, etc.). No excessive em dashes.

---

## Tech Stack

- Pure HTML/CSS/JS
- No build tools, no framework, no CDN
- Static files only — compatible with GitHub Pages as-is

---

## Page Structure

Single-page layout with sections in this order:

1. Profile
2. News
3. Research
4. Publications
5. Ongoing Work
6. Education

Note: News is second (right after Profile) so recent activity is visible immediately.

---

## Content

### Profile

- Name: Jaehong Kim
- Role: Ph.D. Candidate, KAIST (Korea Advanced Institute of Science and Technology)
- Advisor: Wonjae Lee (sociologist) — https://sociology.kaist.ac.kr/
- Internships: Two stints at Max Planck Institute for Security and Privacy (MPI-SP)
  - Sep 2024 – Nov 2024
  - Sep 2025 – Feb 2026
  - Supervised by computational social scientist Meeyoung Cha — https://www.mpi-sp.org/cha
  - Ongoing collaboration with Cha after internships
- Funding: Hyundai Motor Chung Mong-Koo Foundation
- Profile photo: `Jaehong profile.jpeg` (full-body shot)

Bio wording: "I completed two research internships at the Max Planck Institute for Security and Privacy, supervised by computational social scientist Meeyoung Cha, with whom I continue to collaborate."

TODO: Confirm official English full name (middle name, etc.)

### Links / Social

- Email: luke.4.18@kaist.kr — render via JS obfuscation only (see Email Anti-Spam section)
- Google Scholar: https://scholar.google.com/citations?user=aMHLQmEAAAAJ&hl=en
- LinkedIn: https://www.linkedin.com/in/jaehong-kim-1b3601202/
- CV: TODO — add PDF link when ready
- GitHub: TODO — add personal GitHub link if applicable

### Research

Research sits at the intersection of moral psychology and AI, focusing on the attention economy.

Two main threads:

**Measurement.** Computational framework for detecting moral emotions from text and video, using transformer-based models and multimodal architectures. Moral outrage most strongly predicts committed user participation. Also developing explainable AI techniques.

**Effects.** Does the outrage effect extend to offline political behavior? Does it hold when manufactured by malicious actors? Do LLMs that deploy moral outrage become more politically persuasive?

### Publications

List in reverse chronological order. Show venue badge, paper link, and classifier link where available.
Venue badge format: `CONFERENCE YEAR (Findings)` for findings, `CONFERENCE YEAR` for main track.
Classifier link label: "Korean & English Moral Emotion Classifier + Tutorial"

---

**Exploring LLM Behavior in Relational Moral Dilemmas: Moral Rightness, Predicted Human Behavior, and Model Decisions**
ACL 2026 (Findings)
Paper: TODO — link pending camera-ready

---

**Moral Outrage Shapes Commitments Beyond Attention: Multimodal Moral Emotions on YouTube in Korea and the US**
WWW 2026
Paper: https://dl.acm.org/doi/10.1145/3774904.3792728
Classifier: https://github.com/Paul-scpark/Multimodal-Moral-Emotion

---

**Parallel Communities Across the Surface Web and the Dark Web**
EMNLP 2025 (Findings) — Best Resource Paper Nominated
Paper: https://aclanthology.org/2025.findings-emnlp.987/

---

**How Do Moral Emotions Shape Political Participation? A Cross-Cultural Analysis of Online Petitions Using Language Models**
ACL 2024 (Findings)
Paper: https://aclanthology.org/2024.findings-acl.963/
Classifier: https://github.com/Paul-scpark/Moral-Emotion

### News

Date format: `Mon YYYY` — no brackets, no dashes. Use flag emoji for country transitions.
Show most recent first.

```
Apr 2026    Paper accepted to ACL 2026
Feb 2026    🇰🇷 Returned to KAIST after internship at MPI-SP
Jan 2026    Paper accepted to WWW 2026
Sep 2025    Paper accepted to EMNLP 2025
Sep 2025    🇩🇪 Started internship at MPI-SP
Nov 2024    🇰🇷 Returned to KAIST after internship at MPI-SP
Sep 2024    🇩🇪 Started internship at MPI-SP
Apr 2024    Paper accepted to ACL 2024
```

### Education

List in reverse chronological order.

- Ph.D. Candidate, Culture Technology — KAIST (Expected Aug 2027)

- M.S., Culture Technology — KAIST · Social Computing Lab (2023)
  Note: "Bridging social psychology theory and AI methodology"

- B.A., Communication & Psychology · Minor in ICT Convergence · Cum Laude — Handong Global University · Data Analysis Lab (2021)
  Note: "Learning is meant to be shared"

---

## Active Nav Behavior

**Implementation:** Click-lock + fixed 68px threshold scroll detection.

- On nav link click: immediately set that link active, lock scroll detection for 900ms (covers smooth scroll duration)
- On scroll: last section whose `getBoundingClientRect().top <= 68px` becomes active
- Near-bottom fallback (within 80px of page end): last linked section visible in viewport becomes active
- `scroll-padding-top: 64px` ensures any clicked section lands at ~64px from top → within 68px threshold

**Why this approach:** Viewport-ratio thresholds (e.g., 65% of innerHeight) caused adjacent sections to activate on large screens. Fixed 68px is viewport-independent and aligns with scroll-padding-top.

**Known limitation:** Manually scrolling into short sections (Ongoing, Education) without clicking nav may not trigger active state — only clicking does. Acceptable for academic site usage patterns.

---

## Email Anti-Spam

Do not write the email as plain text anywhere in the HTML source. Construct it entirely in JavaScript at runtime so naive crawlers cannot harvest it.

```html
<a id="email-link"></a>

<script>
  const u = 'luke.4.18';
  const d = 'kaist.kr';
  const el = document.getElementById('email-link');
  el.href = 'mailto:' + u + '@' + d;
  el.textContent = u + '@' + d;
</script>
```

---

## Flag Emoji Usage

In the News section, use flag emojis to mark country transitions:
- 🇩🇪 on Germany arrival (MPI-SP internship start)
- 🇰🇷 on Korea return (MPI-SP internship end)

Only at transition points, not on every entry.

---

## Badge System

| Type | Color | Usage |
|---|---|---|
| Venue | Indigo (#4f46e5 on #eef2ff) | Conference name |
| Under Review | Amber (#b45309 on #fffbeb) | Ongoing Work |
| Ongoing | Gray (--text-secondary on #f3f4f6) | Ongoing Work |
| Award | Amber with border (#fde68a) | Best Paper nomination |
| Cum Laude | Amber italic, inline | Degree line |

---

## TODOs

- [ ] Add ACL 2026 paper link (camera-ready pending)
- [ ] Add CV PDF link
- [ ] Add personal GitHub link (if public)
- [ ] Confirm official English full name
