# DSCI 521 Milestone 3

This repository contains my Quarto website for DSCI 521. The site includes computational blog posts written in both Python and R.

The website is built with Quarto and rendered to the `docs/` directory for GitHub Pages.

## Software requirements

The following software versions were used for this project:

- Quarto 1.10.18
- uv 0.12.9
- Python 3.14
- R 4.6.1

## Clone the repository

Clone the repository and enter the project directory:

```bash
git clone git@github.com:xyunpeng/xyunpeng.github.io.git
cd xyunpeng.github.io
```

## Restore the Python environment

The Python environment is managed using `uv`.

Run:

```bash
uv sync
```

This will recreate the local `.venv` environment using the dependencies recorded in `pyproject.toml` and `uv.lock`.

## Restore the R environment

The R environment is managed using `renv`.

Start R from the project directory:

```bash
R
```

Then run:

```r
renv::restore()
```

After the packages have been restored, exit R with:

```r
q()
```

When asked whether to save the workspace image, choose:

```text
n
```

## Render the website

To render the website using the project Python environment, run:

```bash
uv run quarto render
```

The rendered website files will be created in:

```text
docs/
```

## Preview the website locally

To preview the website locally, run:

```bash
uv run quarto preview
```

Quarto will display a local URL in the terminal that can be opened in a web browser.

Press `Ctrl + C` to stop the preview server.

## Computational posts

The website contains two computational posts:

- `posts/python-penguins/index.qmd` — analysis using Python
- `posts/r-penguins/index.qmd` — analysis using R

Both posts explore the Palmer Penguins dataset.

## Data source

The Palmer Penguins dataset is used in both computational posts.

Dataset information:

https://allisonhorst.github.io/palmerpenguins/

The dataset contains measurements for penguins from three species observed in the Palmer Archipelago, Antarctica.

## Internet access

Internet access is required when restoring the Python and R environments for the first time because the required packages must be downloaded.

After the environments are installed, the computational posts use package-provided Palmer Penguins data and do not require downloading an external data file during rendering.