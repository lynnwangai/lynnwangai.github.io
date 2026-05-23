# Personal Website Setup Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Configure the al-folio Jekyll template into Lynn Wang's live personal website at https://lynnwangai.github.io

**Architecture:** Content-only setup — no custom code. All changes are YAML config, Markdown page content, and static assets. The al-folio template handles all rendering, routing, dark mode, SEO, and deployment via GitHub Actions.

**Tech Stack:** Jekyll, al-folio template, GitHub Pages, Docker (for local builds)

---

## File Map

| File | Action | Purpose |
|---|---|---|
| `_config.yml` | Modify | Site identity, URL, scholar name config |
| `_data/socials.yml` | Modify | Social links (email, LinkedIn, GitHub, Scholar) |
| `_pages/about.md` | Rewrite | Full about page: bio, interests, recognition, visual thinking |
| `_pages/publications.md` | Rewrite | Google Scholar link page (no BibTeX for v1) |
| `_pages/projects.md` | Modify | Coming-soon placeholder, nav_order 2 |
| `_pages/cv.md` | Modify | Update cv_pdf path, nav_order 4 |
| `_data/cv.yml` | Rewrite | Full CV content from resume |
| `_pages/blog.md` | Modify | Set nav: false |
| `_pages/teaching.md` | Modify | Set nav: false |
| `_pages/repositories.md` | Modify | Set nav: false |
| `_pages/profiles.md` | Modify | Set nav: false |
| `_pages/dropdown.md` | Modify | Set nav: false |
| `_projects/1_project.md` … `9_project.md` | Delete | Remove sample project cards |
| `assets/img/prof_pic.jpg` | Add (user provides) | Profile photo |
| `assets/img/art_1.jpg` | Add (user provides) | Art/photography image 1 |
| `assets/img/art_2.jpg` | Add (user provides) | Art/photography image 2 (optional) |
| `assets/pdf/cv.pdf` | Add (user provides) | CV PDF |

---

## Task 1: Configure site identity in `_config.yml`

**Files:**
- Modify: `_config.yml` (lines 5–22, 94–95, 281–284)

- [ ] **Step 1: Open `_config.yml` and replace the site settings block (lines 5–22)**

Replace:
```yaml
title: blank # the website title (if blank, full name will be used instead)
first_name: You
middle_name: R.
last_name: Name
contact_note: >
  You can even add a little note about which of these is the best way to reach you.
description: > # the ">" symbol means to ignore newlines until "footer_text:"
  A simple, whitespace theme for academics. Based on [*folio](https://github.com/bogoli/-folio) design.
footer_text: >
  Powered by <a href="https://jekyllrb.com/" target="_blank">Jekyll</a> with <a href="https://github.com/alshedivat/al-folio">al-folio</a> theme.
  Hosted by <a href="https://pages.github.com/" target="_blank">GitHub Pages</a>.
  Photos from <a href="https://unsplash.com" target="_blank">Unsplash</a>.
keywords: jekyll, jekyll-theme, academic-website, portfolio-website # add your own keywords or leave empty
lang: en # the language of your site (for example: en, fr, cn, ru, etc.)
icon: ⚛️ # the emoji used as the favicon (alternatively, provide image name in /assets/img/)

url: https://alshedivat.github.io # the base hostname & protocol for your site
baseurl: /al-folio # the subpath of your site, e.g. /blog/. Leave blank for root
```

With:
```yaml
title: blank # the website title (if blank, full name will be used instead)
first_name: Linghui (Lynn)
middle_name:
last_name: Wang
contact_note:
description: >
  Applied Scientist · Deep Learning · Time-Series · Caltech Ph.D.
footer_text: >
  Powered by <a href="https://jekyllrb.com/" target="_blank">Jekyll</a> with <a href="https://github.com/alshedivat/al-folio">al-folio</a> theme.
  Hosted by <a href="https://pages.github.com/" target="_blank">GitHub Pages</a>.
keywords: machine learning, deep learning, time-series, applied science, Caltech
lang: en
icon: 🧠

url: https://lynnwangai.github.io # the base hostname & protocol for your site
baseurl: # leave blank — this is a user GitHub Pages site (username.github.io)
```

- [ ] **Step 2: Update blog name (around line 94)**

Replace:
```yaml
blog_name: al-folio # blog_name will be displayed in your blog page
blog_description: a simple whitespace theme for academics
```

With:
```yaml
blog_name: Lynn Wang
blog_description: Notes on ML, research, and ideas
```

- [ ] **Step 3: Update Jekyll Scholar name config (around line 281)**

Replace:
```yaml
scholar:
  last_name: [Einstein]
  first_name: [Albert, A.]
```

With:
```yaml
scholar:
  last_name: [Wang]
  first_name: [Linghui, Lynn, L.]
```

- [ ] **Step 4: Commit**

```bash
git add _config.yml
git commit -m "feat: configure site identity for Lynn Wang"
```

---

## Task 2: Update social links in `_data/socials.yml`

**Files:**
- Modify: `_data/socials.yml`

- [ ] **Step 1: Replace the entire file with Lynn's social links**

```yaml
# _data/socials.yml
cv_pdf: /assets/pdf/cv.pdf
email: lynnwang102@gmail.com
github_username: lynnwangai
linkedin_username: linghui-lynn-wang-006bb9a9
scholar_userid: rplqPFEAAAAJ
```

- [ ] **Step 2: Commit**

```bash
git add _data/socials.yml
git commit -m "feat: add Lynn's social links"
```

---

## Task 3: Rewrite `_pages/about.md`

**Files:**
- Modify: `_pages/about.md`

- [ ] **Step 1: Replace the entire file with the following content**

```markdown
---
layout: about
title: about
permalink: /
subtitle: Applied Scientist · Deep Learning · Time-Series · Caltech Ph.D.

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false
  more_info: >
    <p>St. Louis, MO · Open to relocation</p>

selected_papers: false
social: true

announcements:
  enabled: false

latest_posts:
  enabled: false
---

Hi, I'm Linghui (Lynn) Wang, an applied machine learning scientist working at the intersection of deep learning, physical systems, and real-world decision-making.

I'm currently a Senior Machine Learning Researcher at Bayer R&D, where I lead the development of ML systems for complex, noisy, high-dimensional data. My work focuses on domain-informed deep learning, multivariate time series, multimodal learning, transfer learning, and scalable model deployment. I've built production-ready models that improved predictive performance by over 10%, accelerated training by 80%, and strengthened generalization in challenging data regimes.

Before industry, I earned my Ph.D. in Applied Physics from Caltech, where I studied ion transport, soft matter, and biomimetic sensing materials. That training shaped how I approach machine learning: I aim to build deep learning models that generalize by combining data-driven methods with domain knowledge and scientific intuition. I'm also interested in using models not only for prediction, but as tools to understand structure, interactions, and dynamics in complex systems.

More broadly, I'm interested in AI systems that do more than fit data — systems that help us predict, uncover useful structure, and support better decisions in complex environments.

---

## Current Interests

- **Mechanistic interpretability** — understanding the internal representations and circuits that drive behavior in large neural networks
- **AI alignment and safety** — building systems whose goals remain robustly aligned with human intent at scale
- **AI's societal implications** — how large-scale AI deployment reshapes scientific practice, decision-making, and institutional trust
- **Domain-informed deep learning** — grounding data-driven methods in physical and scientific structure to improve robustness and generalization

---

## Recognition

- Bayer R&D Eclipse Award — Top Innovation Award, Global R&D (2025)
- Asia Breeding Year End Award (2025)
- R&D Top Performer Award (2024)

---

## Visual Thinking

Outside of research, I make things — mostly photography and visual art.

<div class="row mt-3">
  <div class="col-sm-6 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/art_1.jpg" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-6 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/art_2.jpg" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

- [ ] **Step 2: Commit**

```bash
git add _pages/about.md
git commit -m "feat: write about page with bio, interests, recognition, and visual thinking"
```

---

## Task 4: Rewrite `_pages/publications.md`

**Files:**
- Modify: `_pages/publications.md`

- [ ] **Step 1: Replace the entire file**

```markdown
---
layout: page
permalink: /publications/
title: Publications & Patents
nav: true
nav_order: 3
---

My published work spans deep learning for physical systems, multivariate time-series prediction, and multimodal learning.

**[View full list on Google Scholar →](https://scholar.google.com.hk/citations?user=rplqPFEAAAAJ)**

5+ peer-reviewed publications &nbsp;·&nbsp; 2 U.S. patents
```

- [ ] **Step 2: Commit**

```bash
git add _pages/publications.md
git commit -m "feat: set up Publications & Patents page with Google Scholar link"
```

---

## Task 5: Update `_pages/projects.md`

**Files:**
- Modify: `_pages/projects.md`

- [ ] **Step 1: Update front matter and add placeholder content**

Replace the front matter and content with:
```markdown
---
layout: page
title: Projects
permalink: /projects/
description:
nav: true
nav_order: 2
display_categories: [work]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}
{% else %}
{% assign sorted_projects = site.projects | sort: "importance" %}
{% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>

{% if site.projects.size == 0 %}
<p class="text-muted mt-4">Interpretability project in progress — check back soon.</p>
{% endif %}
```

- [ ] **Step 2: Commit**

```bash
git add _pages/projects.md
git commit -m "feat: set up Projects page with placeholder"
```

---

## Task 6: Update `_pages/cv.md`

**Files:**
- Modify: `_pages/cv.md`

- [ ] **Step 1: Replace the entire file**

```markdown
---
layout: cv
permalink: /cv/
title: CV
nav: true
nav_order: 4
cv_pdf: /assets/pdf/cv.pdf
cv_format: rendercv
description: Curriculum Vitae — Linghui (Lynn) Wang
toc:
  sidebar: left
---
```

- [ ] **Step 2: Commit**

```bash
git add _pages/cv.md
git commit -m "feat: update CV page config"
```

---

## Task 7: Rewrite `_data/cv.yml` with Lynn's CV

**Files:**
- Modify: `_data/cv.yml`

- [ ] **Step 1: Replace the entire file**

```yaml
cv:
  name: Linghui (Lynn) Wang
  label: Applied Scientist
  email: lynnwang102@gmail.com
  location: St. Louis, MO
  image: ""
  summary: >
    Applied Scientist with a Ph.D. in Applied Physics from Caltech and 3+ years of industry experience
    designing, evaluating, and deploying deep learning systems for high-dimensional, noisy prediction problems.
    5+ peer-reviewed publications; 2 U.S. patents.

  social_networks:
    - network: LinkedIn
      username: linghui-lynn-wang-006bb9a9
    - network: GitHub
      username: lynnwangai

  sections:
    Experience:
      - company: Bayer
        position: Senior Machine Learning Researcher
        location: Chesterfield, MO, USA
        start_date: 2025-05
        highlights:
          - "Initiated and led research into domain-integrated model architectures for multivariate time-series prediction; developed transformer-based models that improved MAE by 23% versus prior baselines with strong generalization to previously unseen geographic regions."
          - "Strategic and technical lead for a cross-functional predictive-modeling initiative, partnering with 12 stakeholders across science, data, and product to define use cases, align requirements, and drive delivery of production ML solutions."
          - "Led end-to-end development of a regional multimodal ML system with 10+ collaborators, enabling model-driven decision-making for a new market and informing downstream ranking and recommendation workflows."
          - "Mentored junior scientists on modeling strategy, experiment design, and implementation quality across active project workstreams."

      - company: Bayer
        position: Data Scientist
        location: Chesterfield, MO, USA
        start_date: 2023-05
        end_date: 2025-05
        highlights:
          - "Designed and deployed a multimodal, multitask deep learning system integrating heterogeneous sequence data (weather + genetic signals), improving MAE by 10% and accelerating training by 80% versus prior baselines."
          - "Applied transfer learning and fine-tuning to noisy, high-dimensional forecasting tasks, improving generalization by 48% on held-out conditions through systematic ablation and evaluation."
          - "Scaled training to 2M data points x 50K features using multi-GPU distributed training on AWS SageMaker; optimized to <20 GPU-hours per weekly retraining cycle."
          - "Productionized an end-to-end ML system on AWS (data ingestion, training, evaluation, deployment, monitoring, retraining) using S3/SageMaker/EC2 with Airflow and Docker, delivering ~10M inferences per production cycle."

      - company: Toyota Research Institute
        position: Research Intern
        location: Los Altos, CA, USA
        start_date: 2022-05
        end_date: 2022-08
        highlights:
          - "Designed and implemented physics-informed Graph Neural Networks (GNNs) for structured property prediction; improved accuracy by 40% and integrated models into an active learning loop to accelerate scientific discovery workflows."

      - company: Caltech
        position: Graduate Researcher
        location: Pasadena, CA, USA
        start_date: 2016
        end_date: 2023
        highlights:
          - "Built end-to-end signal processing pipeline for high-noise time-series sensor data; developed physics-informed and simulation-based models (Monte Carlo, Molecular Dynamics) on HPC infrastructure."
          - "5+ peer-reviewed publications, 2 U.S. patents."
          - "Ranked 4th/80 in Caltech ML competition using ensemble methods (Random Forest, AdaBoost, Neural Networks); built LSTM and HMM-based sequence generators for structured text generation."

    Education:
      - institution: California Institute of Technology (Caltech)
        location: Pasadena, CA
        url: https://www.caltech.edu/
        area: Applied Physics
        studyType: "Ph.D., M.S."
        start_date: 2016
        end_date: 2023

      - institution: University of Illinois Urbana-Champaign (UIUC)
        location: Urbana-Champaign, IL
        url: https://illinois.edu/
        area: "Physics; Minor in Mathematics"
        studyType: B.S.
        start_date: 2013
        end_date: 2016

    Skills:
      - name: "Modeling & Research"
        level: Expert
        icon: fa-solid fa-brain
        keywords: "deep learning, transformer architectures, time-series modeling, multimodal learning, multitask learning, transfer learning, ensemble methods, statistical modeling, experiment design, model selection, error analysis"

      - name: "Tools & Frameworks"
        level: Expert
        icon: fa-solid fa-code
        keywords: "Python, PyTorch, TensorFlow, NumPy, Pandas, Scikit-learn, SQL, AWS (SageMaker, S3, EC2), distributed multi-GPU training"

      - name: "GenAI / NLP"
        level: Proficient
        icon: fa-solid fa-robot
        keywords: "LLM fine-tuning, prompt engineering, RAG, sequence-to-sequence modeling"

      - name: "Production ML"
        level: Proficient
        icon: fa-solid fa-server
        keywords: "Docker, batch inference pipelines, model monitoring, evaluation frameworks"

    Certificates:
      - name: Generative AI with Large Language Models
        date: 2024-01-01
        issuer: "DeepLearning.AI & AWS (Coursera)"
        icon: fa-solid fa-certificate
        summary: "LLM fine-tuning, RLHF, prompt engineering"

    Awards:
      - title: Bayer R&D Eclipse Award
        date: 2025-01-01
        awarder: Bayer
        summary: "Top Innovation Award in global R&D"

      - title: Asia Breeding Year End Award
        date: 2025-01-01
        awarder: Bayer

      - title: R&D Top Performer Award
        date: 2024-01-01
        awarder: Bayer
```

- [ ] **Step 2: Commit**

```bash
git add _data/cv.yml
git commit -m "feat: populate CV with Lynn's experience, education, and skills"
```

---

## Task 8: Hide unused pages from nav

**Files:**
- Modify: `_pages/blog.md` — set `nav: false`
- Modify: `_pages/teaching.md` — add `nav: false`
- Modify: `_pages/repositories.md` — set `nav: false`
- Modify: `_pages/profiles.md` — set `nav: false`
- Modify: `_pages/dropdown.md` — set `nav: false`

- [ ] **Step 1: Set `nav: false` in `_pages/blog.md`**

The file starts with:
```yaml
---
layout: default
permalink: /blog/
title: blog
nav: true
---
```

Change `nav: true` to `nav: false`.

- [ ] **Step 2: Add `nav: false` to `_pages/teaching.md`**

The file front matter currently has no `nav:` line. Add `nav: false` after the `title:` line:
```yaml
---
layout: page
permalink: /teaching/
title: teaching
description: Course materials, schedules, and resources for classes taught.
nav: false
---
```

- [ ] **Step 3: Set `nav: false` in `_pages/repositories.md`**

Change `nav: true` to `nav: false`.

- [ ] **Step 4: Set `nav: false` in `_pages/profiles.md`**

Change `nav: true` to `nav: false`.

- [ ] **Step 5: Set `nav: false` in `_pages/dropdown.md`**

Change `nav: true` to `nav: false`.

- [ ] **Step 6: Commit**

```bash
git add _pages/blog.md _pages/teaching.md _pages/repositories.md _pages/profiles.md _pages/dropdown.md
git commit -m "feat: hide unused nav pages (blog, teaching, repositories, profiles, dropdown)"
```

---

## Task 9: Remove sample project files

**Files:**
- Delete: `_projects/1_project.md` through `_projects/9_project.md`

- [ ] **Step 1: Delete all sample project files**

```bash
rm _projects/1_project.md _projects/2_project.md _projects/3_project.md \
   _projects/4_project.md _projects/5_project.md _projects/6_project.md \
   _projects/7_project.md _projects/8_project.md _projects/9_project.md
```

- [ ] **Step 2: Commit**

```bash
git add -A _projects/
git commit -m "feat: remove sample project files"
```

---

## Task 10: Add placeholder asset files

**This task requires Lynn to provide files. Claude Code cannot create image or PDF content.**

- [ ] **Step 1: Add profile photo**

Save your profile photo as `assets/img/prof_pic.jpg` (recommended: ~800×800px, square crop or portrait).

- [ ] **Step 2: Add art/photography images**

Save your two art images as:
- `assets/img/art_1.jpg`
- `assets/img/art_2.jpg`

Recommended size: ~1200px wide. If you only have one image, that's fine — update `_pages/about.md` to remove the second `<div class="col-sm-6 ...">` block.

- [ ] **Step 3: Add CV PDF**

Save your CV as `assets/pdf/cv.pdf`.

- [ ] **Step 4: Commit assets**

```bash
git add assets/img/prof_pic.jpg assets/img/art_1.jpg assets/img/art_2.jpg assets/pdf/cv.pdf
git commit -m "feat: add profile photo, art images, and CV PDF"
```

> **Note:** If you don't have the assets ready yet, you can skip this task and come back. The site will build with a broken image placeholder. Just don't skip the commit before Task 11.

---

## Task 11: Build locally and verify

**Prerequisites:** Docker installed and running. Run `docker compose pull` once if you haven't already.

- [ ] **Step 1: Start the local dev server**

```bash
docker compose up
```

Wait for output like:
```
Server address: http://0.0.0.0:4000/
Server running...
```

Then open http://localhost:8080 in your browser.

- [ ] **Step 2: Check About page (http://localhost:8080)**

Verify:
- Name "Linghui (Lynn) Wang" appears as heading
- Subtitle "Applied Scientist · Deep Learning · Time-Series · Caltech Ph.D." shows below name
- Profile photo shows (or a placeholder box if photo not yet added)
- Bio paragraphs are correct
- "Current Interests" section shows with 4 bullet points
- "Recognition" section shows 3 awards
- "Visual Thinking" section shows (images or broken-image placeholder if not yet added)
- Social icons (email, LinkedIn, GitHub, Scholar) appear
- No announcements feed
- No "Latest Posts" section

- [ ] **Step 3: Check Projects page (http://localhost:8080/projects/)**

Verify:
- Page loads with title "Projects"
- "Interpretability project in progress — check back soon." placeholder text appears

- [ ] **Step 4: Check Publications page (http://localhost:8080/publications/)**

Verify:
- Title shows "Publications & Patents"
- Google Scholar link is clickable
- "5+ peer-reviewed publications · 2 U.S. patents" line shows

- [ ] **Step 5: Check CV page (http://localhost:8080/cv/)**

Verify:
- CV renders with Lynn's experience, education, skills
- Download CV link appears (may show 404 until cv.pdf is added)

- [ ] **Step 6: Check navbar**

Verify navbar shows exactly: **About · Projects · Publications & Patents · CV**
No Blog, Teaching, Repositories, or Profiles links.

- [ ] **Step 7: Check dark mode**

Click the dark mode toggle (sun/moon icon in navbar). Site should switch themes cleanly.

- [ ] **Step 8: Stop the server**

Press `Ctrl+C` to stop Docker, then:
```bash
docker compose down
```

---

## Task 12: Create GitHub repo and deploy

- [ ] **Step 1: Create the GitHub repository**

Go to https://github.com/new and create a repository named exactly:
```
lynnwangai.github.io
```
Set it to **Public**. Do NOT initialize with README, .gitignore, or license (the repo already has content).

- [ ] **Step 2: Connect local repo to GitHub**

```bash
git remote add origin https://github.com/lynnwangai/lynnwangai.github.io.git
git branch -M main
git push -u origin main
```

- [ ] **Step 3: Enable GitHub Pages**

In the repo on GitHub:
1. Go to **Settings → Pages**
2. Under "Build and deployment", set Source to **GitHub Actions**
3. The al-folio workflow file (`.github/workflows/deploy.yml`) is already in the repo and will trigger automatically

- [ ] **Step 4: Monitor the deployment**

Go to the **Actions** tab in your GitHub repo. You should see a workflow run in progress. Wait for it to complete (typically 3–5 minutes).

If the workflow fails, the error will be shown in the Actions tab. Common issue: `baseurl` must be empty (not `/`) for a `username.github.io` repo — already handled in Task 1.

- [ ] **Step 5: Verify live site**

Open https://lynnwangai.github.io in your browser.

Repeat the same checks from Task 11, Steps 2–7.

- [ ] **Step 6: Done**

The site is live. Future updates: edit any file, commit, push to `main` — GitHub Actions auto-deploys within ~3 minutes.
