# resume

[![Build & Publish](https://github.com/agus-darmawan/resume/actions/workflows/build-and-publish.yml/badge.svg)](https://github.com/agus-darmawan/resume/actions/workflows/build-and-publish.yml)
[![Portfolio](https://img.shields.io/badge/portfolio-agus--darmawan.com-blue)](https://agus-darmawan.com)
[![Built with LaTeX](https://img.shields.io/badge/built%20with-LaTeX-008080)](https://www.latex-project.org/)

> LaTeX resumes for **I Wayan Agus Darmawan** — Full-stack Developer &
> Robotics Engineer. One master copy holds everything; role-specific
> versions are trimmed from it for actual job applications.

## Structure

```
.
├── master-cv/             # everything, no page limit — internal reference only
├── software-developer/    # trimmed to 1 page, full-stack focused
└── robotics-engineer/     # trimmed to 1 page, robotics/embedded focused
```

All three share the same base layout: Charter font, ATS-friendly
(`\pdfgentounicode=1`), no exotic packages.

## Versions

| File | Focus | Use for |
| --- | --- | --- |
| `master-cv/resume.tex` | Every job, project, and skill, unfiltered | Personal reference only — never sent out |
| `software-developer/resume.tex` | REST APIs, React, PostgreSQL, Docker, CI/CD | Full-stack / backend roles |
| `robotics-engineer/resume.tex` | ROS/ROS2, PID control, sensor fusion, embedded hardware | Robotics / embedded roles |

## Workflow

1. Add new experience to `master-cv/resume.tex` first, as soon as it happens — no filtering, just capture it.
2. When applying to a job, trim the relevant bullets into `software-developer/` or `robotics-engineer/` (or a new folder for a new role), keeping it to 1 page.
3. Only ever send the role-specific PDF — the master CV stays private.

## Building

Requires a LaTeX distribution (TeX Live recommended).

```bash
cd software-developer   # or robotics-engineer, master-cv
pdflatex resume.tex
pdflatex resume.tex     # run twice to resolve references
```

## CI/CD

`.github/workflows/build-and-publish.yml` compiles all three resumes on
every push to `main`. `software-developer` and `robotics-engineer` PDFs are
then:

- uploaded to the Cloudflare R2 bucket that `agus-darmawan.com` reads from (`NEXT_PUBLIC_CONTENT_URL`) — so a push here goes live on the site automatically
- attached to a rolling `latest-cv` GitHub Release as a direct-download backup

`master-cv` is compiled as a build artifact but never published anywhere.

**Required repo secrets** (Settings → Secrets and variables → Actions):

| Secret | Description |
| --- | --- |
| `R2_ACCESS_KEY_ID` | Cloudflare R2 API token access key |
| `R2_SECRET_ACCESS_KEY` | Cloudflare R2 API token secret |
| `R2_BUCKET` | Target R2 bucket (same one the site reads from) |
| `R2_ENDPOINT` | R2 S3-compatible endpoint |
| `R2_RESUME_PREFIX` | Path inside the bucket, e.g. `resume/` |

## Language

English only, by design — standard for tech roles internationally and at
most Indonesian tech companies, and it keeps one source of truth to
maintain. Add `resume.id.tex` later if a Bahasa Indonesia version becomes
genuinely necessary for a specific application.
