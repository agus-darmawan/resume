# resume

LaTeX resume templates, tailored per role. Each version reuses the same base
layout (Charter font, ATS-friendly, single page) but with content and skills
sections adapted to the target job.

## Structure

```
.
├── software-developer/
│   └── resume.tex      # Full-stack / backend-focused resume
├── robotics-engineer/
│   └── resume.tex       # Robotics / embedded-focused resume
└── .gitignore
```

## Versions

### `software-developer/resume.tex`
Emphasizes full-stack web development: REST APIs, React, PostgreSQL, Docker,
CI/CD. Skills grouped by Languages / Backend & APIs / Frontend / DevOps.

### `robotics-engineer/resume.tex`
Emphasizes robotics and embedded systems: ROS/ROS2, PID control, sensor
fusion, Gazebo simulation, and hardware (Raspberry Pi, Arduino). Experience
and projects are reordered/reframed to highlight hardware-software
integration work.

## Building

Requires a LaTeX distribution (TeX Live recommended).

```bash
cd software-developer
pdflatex resume.tex
pdflatex resume.tex   # run twice to resolve references
```

Same steps apply inside `robotics-engineer/`.

## Customizing

1. Update the header block (name, phone, email, LinkedIn, GitHub, portfolio
   link) in the `\begin{center}...\end{center}` section.
2. Edit `Professional Summary`, `Experience`, `Projects`, `Technical Skills`,
   and `Education` sections with your own details.
3. Recompile with `pdflatex`.

