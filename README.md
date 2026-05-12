# VCM-704LAB-UET Lab Website

Official research website for **VCM-704LAB-UET** — Video Coding for Machine Vision Research Group, University of Engineering and Technology, Vietnam National University, Hanoi.

This website is built with **MkDocs Material** and deployed using GitHub Pages.

## Local Development

```bash
pip install -r requirements.txt
mkdocs serve
```

Then open:

```text
http://127.0.0.1:8000
```

## Build

```bash
mkdocs build
```

## Deploy

The repository includes a GitHub Actions workflow at:

```text
.github/workflows/deploy.yml
```

After GitHub Pages is enabled for the repository, every push to `main` will build and deploy the website.

## Website Structure

```text
docs/
├── index.md
├── about.md
├── people.md
├── research.md
├── projects.md
├── publications.md
├── resources.md
├── join-us.md
└── contact.md
```

## Main Research Theme

**Efficient Video Coding for Machine Vision Applications**

The lab focuses on task-aware, standard-compatible, and edge-oriented video coding frameworks for intelligent visual analytics.
