# Personal Website — Jaehong Kim

## Project

Academic personal website for Jaehong Kim, Ph.D. candidate at KAIST.
Hosted on GitHub Pages: jaehong-k.github.io

---

## Design

Linear-style: clean, minimal, professional. Inspired by linear.app.

- Font: -apple-system / Apple SD Gothic Neo (system font, no external dependency)
- Background: #F5F3F0 (Cloud Dancer — Pantone Color of the Year 2026, warm soft white), Text: #0A0A0A, Border: #E2DDD8, Accent: #3B82F6
- Layout: single-column, centered, max-width 720px
- Generous whitespace; no visual clutter
- Hover transitions only (no scroll animations, no page transitions)
- Fully responsive, mobile-first
- No heavy JS frameworks — pure HTML/CSS/JS

Writing style in all copy: plain, direct English. No LLM-style words (notably, furthermore, crucially, etc.). No excessive em dashes.

---

## Tech Stack

- Pure HTML/CSS/JS
- No build tools, no framework, no CDN except Google Fonts
- Static files only — compatible with GitHub Pages as-is

---

## Page Structure

Single-page layout with sections in this order:

1. Profile
2. Research Interests
3. Publications
4. News
5. Education

---

## Content

### Profile

- Name: Jaehong Kim
- Role: Ph.D. Candidate, KAIST (Korea Advanced Institute of Science and Technology)
- Advisor: Won-jae Lee — https://sociology.kaist.ac.kr/
- Internship: Max Planck Institute for Security and Privacy (MPI-SP), Bochum, Germany — Sep 2025 to Feb 2026, supervised by Meeyoung Cha — https://www.mpi-sp.org/cha
- Funding: Hyundai Motor Chung Mong-Koo Foundation
- Profile photo: `Jaehong profile crop.jpeg`

TODO: Confirm official English full name (middle name, etc.)

### Links / Social

- Email: luke.4.18@kaist.kr — render via JS obfuscation only (see Email Anti-Spam section)
- Google Scholar: https://scholar.google.com/citations?user=aMHLQmEAAAAJ&hl=en
- LinkedIn: https://www.linkedin.com/in/jaehong-kim-1b3601202/
- CV: TODO — add PDF link when ready
- GitHub: TODO — add personal GitHub link if applicable

### Research Interests

Research sits at the intersection of moral psychology and AI, focusing on the attention economy.

Two main threads:

**Measurement.** A computational framework for measuring moral emotions using transformer-based models, multimodal architectures, and explainable AI. (Ongoing)

**Effects.** Among moral emotions, moral outrage — expressions that blame and condemn others — most strongly drives committed user participation. Current work examines: (i) whether this effect extends to offline political behavior, (ii) whether it persists when driven by malicious users, and (iii) whether LLMs leveraging these dynamics gain political persuasion power.

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
EMNLP 2025 (Findings)
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
Apr 2024    Paper accepted to ACL 2024
```

Note: the original draft had a conflicting "Nov 2025 — Finish interned" entry. Removed — internship ran Sep 2025–Feb 2026.

---

## Email Anti-Spam

Do not write the email as plain text anywhere in the HTML source. Construct it entirely in JavaScript at runtime so naive crawlers cannot harvest it.

Implementation pattern:

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

The `<a>` tag must have no `href` or text content in HTML — JS fills both in after load.

---

## Flag Emoji Usage

In the News section, use flag emojis to mark country transitions:
- 🇩🇪 when starting the MPI-SP internship in Germany
- 🇰🇷 when returning to Korea/KAIST

Only use flags at transition points, not on every entry.

---

### Education

List in reverse chronological order.

- Ph.D. Candidate, KAIST — Culture Technology (Expected Aug 2027)
  Advisor: Won-jae Lee

- M.S., KAIST — Culture Technology (Engineering), 2023

- B.A., Handong Global University — Communication, Psychology; minor in ICT Convergence, 2021

---

## TODOs Before Build

- [ ] Confirm full official English name
- [ ] Add ACL 2026 paper link (camera-ready pending)
- [ ] Add graduation years to Education (optional)
- [ ] Add CV PDF link
- [ ] Add personal GitHub link (if public)
