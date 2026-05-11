# Personal Website Design Spec
**Date:** 2026-05-11
**Owner:** Linghui (Lynn) Wang
**Template:** al-folio (Jekyll)
**Live URL:** https://lynnwangai.github.io
**Repo:** https://github.com/lynnwangai/lynnwangai.github.io

---

## 1. Site Identity

| Field | Value |
|---|---|
| Name | Linghui (Lynn) Wang |
| Tagline | Applied Scientist · Deep Learning · Time-Series · Caltech Ph.D. |
| Email | lynnwang102@gmail.com |
| LinkedIn | linkedin.com/in/linghui-lynn-wang-006bb9a9 |
| GitHub | github.com/lynnwangai |
| Google Scholar | https://scholar.google.com.hk/citations?user=rplqPFEAAAAJ |

---

## 2. Navigation

**Navbar order:** About · Projects · Publications & Patents · CV

| Page | Route | Status for v1 |
|---|---|---|
| About | `/` | Full content |
| Projects | `/projects/` | Placeholder card ("coming soon") |
| Publications & Patents | `/publications/` | Google Scholar link + summary |
| CV | `/cv/` | PDF link + rendered content |
| Blog | `/blog/` | Exists in codebase, hidden from nav |

**Hidden entirely (not in nav, no stray links):** Teaching, Repositories, News/Announcements feed.

---

## 3. About Page

Sections in order:

### 3.1 Header
- Profile photo (floated right, not circular — `image_circular: false`)
- Name: "Linghui (Lynn) Wang" as page heading
- Subtitle: "Applied Scientist · Deep Learning · Time-Series · Caltech Ph.D."
- Social icons: Email, LinkedIn, GitHub, Google Scholar

### 3.2 Professional Bio
Verbatim text provided by Lynn:

> Hi, I'm Linghui (Lynn) Wang, an applied machine learning scientist working at the intersection of deep learning, physical systems, and real-world decision-making.
>
> I'm currently a Senior Machine Learning Researcher at Bayer R&D, where I lead the development of ML systems for complex, noisy, high-dimensional data. My work focuses on domain-informed deep learning, multivariate time series, multimodal learning, transfer learning, and scalable model deployment. I've built production-ready models that improved predictive performance by over 10%, accelerated training by 80%, and strengthened generalization in challenging data regimes.
>
> Before industry, I earned my Ph.D. in Applied Physics from Caltech, where I studied ion transport, soft matter, and biomimetic sensing materials. That training shaped how I approach machine learning: I aim to build deep learning models that generalize by combining data-driven methods with domain knowledge and scientific intuition. I'm also interested in using models not only for prediction, but as tools to understand structure, interactions, and dynamics in complex systems.
>
> More broadly, I'm interested in AI systems that do more than fit data — systems that help us predict, uncover useful structure, and support better decisions in complex environments.

### 3.3 Current Interests
Short section (paragraph or 3–4 bullets) covering:
- Mechanistic interpretability of large models
- Model alignment and AI safety
- AI's broader societal implications
- Domain-informed deep learning and time-series systems

*Exact wording to be drafted during implementation.*

### 3.4 Selected Recognition
Understated list under a minimal header (e.g., "Recognition"):
- Bayer R&D Eclipse Award — Top Innovation Award, Global R&D (2025)
- Asia Breeding Year End Award (2025)
- R&D Top Performer Award (2024)

### 3.5 Visual Thinking
- Section title: "Visual Thinking"
- 1–2 art/photography images in a simple grid
- Minimal caption per image
- Kept low-key — signals range, not a portfolio
- Images to be provided by Lynn as JPGs (~1200px), placed in `assets/img/`

---

## 4. Publications & Patents Page

- Short intro sentence (1–2 lines)
- Prominent link to Google Scholar profile
- Summary line: "5+ peer-reviewed publications · 2 U.S. patents"
- Note that full list is maintained on Google Scholar
- No manual BibTeX entries for v1

---

## 5. Projects Page (v1 Placeholder)

- Single placeholder card or note: interpretability project in progress
- Will be fleshed out when Lynn's interpretability project is ready to share

---

## 6. CV Page

- Link to download/view `assets/pdf/cv.pdf`
- CV content rendered from `_data/cv.yml`
- Sections from resume: Technical Skills, Work Experience, Education, Certifications & Honors
- PDF to be provided by Lynn, placed at `assets/pdf/cv.pdf`

---

## 7. Design & Aesthetic

- al-folio default theme — clean, minimal, academic
- Dark mode toggle enabled (al-folio built-in)
- Mobile-responsive (al-folio built-in)
- No animations, no video backgrounds, no analytics for v1
- Fast page loads

---

## 8. Hosting & Deployment

- GitHub Pages (free)
- Auto-deploy on push to `main` via GitHub Actions (al-folio built-in)
- Custom domain: skip for v1, add later if desired
- SEO: meta tags, sitemap, robots.txt handled by al-folio

---

## 9. Assets to Provide (Lynn's responsibility)

| Asset | Path | Notes |
|---|---|---|
| Profile photo | `assets/img/prof_pic.jpg` | ~1200px JPG |
| Art/photo image 1 | `assets/img/art_1.jpg` | ~1200px JPG |
| Art/photo image 2 | `assets/img/art_2.jpg` | ~1200px JPG (optional) |
| CV PDF | `assets/pdf/cv.pdf` | Final version |

---

## 10. Out of Scope for v1

- Blog posts (page hidden, content added later)
- Full interpretability project page (placeholder only)
- Custom domain
- Analytics
- Contact form
- Teaching page
- Repositories listing
