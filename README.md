# DockerLecture

Beginner-friendly lecture slides introducing Docker, why it is useful, and how
containers differ from virtual machines.

The main artifact is the compiled Beamer deck:

- [docker.pdf](docker.pdf) - ready-to-read lecture slides
- [docker.tex](docker.tex) - LaTeX source for rebuilding or editing the deck

## Lecture Outline

The slide deck currently covers:

1. Why Docker is useful when server environments change
2. How virtual machines work and where their overhead comes from
3. How Docker avoids a guest OS and shares host OS system calls
4. The difference between Docker images and Docker containers
5. Docker options, currently present as a section placeholder for future slides

## Repository Contents

| Path | Description |
| --- | --- |
| `docker.pdf` | Compiled PDF version of the lecture. |
| `docker.tex` | Beamer source file for the lecture slides. |
| `figures/architecture.jpg` | Docker image/container architecture diagram used in the deck. |
| `figures/docker.png` | Docker architecture comparison figure. |
| `figures/itworks.png` | Environment mismatch illustration used in the motivation section. |
| `figures/vm.png` | Virtual machine architecture comparison figure. |

## Requirements

To read the lecture, open `docker.pdf`.

To rebuild the PDF from source, install a LaTeX distribution that includes
Beamer and common packages used by the deck:

- `graphicx`
- `apacite`
- `datetime2`
- `ulem`

No Docker installation is required to read or build these lecture slides.

## Build

From the repository root, run:

```sh
latexmk -pdf docker.tex
```

If `latexmk` is unavailable, run `pdflatex` twice so the table of contents and
cross-references settle:

```sh
pdflatex docker.tex
pdflatex docker.tex
```

The generated output is `docker.pdf`.

To remove LaTeX auxiliary files after building:

```sh
latexmk -c docker.tex
```

## Editing Notes

- Keep figures under `figures/` and reference them from `docker.tex` with
  relative paths.
- The repository intentionally tracks `docker.pdf` so readers can view the deck
  without compiling LaTeX.
- The `.gitignore` file excludes common LaTeX auxiliary files generated during
  compilation.
