# resume

LaTeX resume templates, tailored per role, plus one master CV that holds
everything. Each role-specific version reuses the same base layout (Charter
font, ATS-friendly, single page) but with content and skills sections
trimmed and adapted to the target job.

## Structure

```
.
├── master-cv/
│   └── resume.tex          # Full history, everything, not for submission
├── software-developer/
│   └── resume.tex          # Full-stack / backend-focused resume (1 page)
├── robotics-engineer/
│   └── resume.tex          # Robotics / embedded-focused resume (1 page)
└── .gitignore
```

## Versions

### `master-cv/resume.tex`
The internal reference copy. Contains every job, every project, and the full
skills list (web dev + robotics + everything else), with no 1-page limit.
**Not meant to be sent to anyone as-is** — it's the source you trim from
when building a role-specific resume, or when you need to remember exactly
what you did on a given project. Update this file first whenever you gain
new experience, then cherry-pick the relevant parts into the versions below.

### `software-developer/resume.tex`
Emphasizes full-stack web development: REST APIs, React, PostgreSQL, Docker,
CI/CD. Skills grouped by Languages / Backend & APIs / Frontend / DevOps.

### `robotics-engineer/resume.tex`
Emphasizes robotics and embedded systems: ROS/ROS2, PID control, sensor
fusion, Gazebo simulation, and hardware (Raspberry Pi, Arduino). Experience
and projects are reordered/reframed to highlight hardware-software
integration work.

## Workflow

1. Add new experience/projects to `master-cv/resume.tex` as they happen —
   don't worry about length or relevance here, just capture everything.
2. When applying to a job, open the closest matching role-specific file
   (or copy `master-cv/resume.tex` into a new folder for a new role) and
   trim it down to the 2-3 most relevant bullets per section, keeping it
   to one page.
3. Recompile and send only the role-specific PDF, never the master CV.

## Building

Requires a LaTeX distribution (TeX Live recommended).

```bash
cd software-developer
pdflatex resume.tex
pdflatex resume.tex   # run twice to resolve references
```

Same steps apply inside `robotics-engineer/` and `master-cv/`.

## Customizing

1. Update the header block (name, phone, email, LinkedIn, GitHub, portfolio
   link) in the `\begin{center}...\end{center}` section.
2. Edit `Professional Summary`, `Experience`, `Projects`, `Technical Skills`,
   and `Education` sections with your own details.
3. Recompile with `pdflatex`.

