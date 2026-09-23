# dbt Prefect Starter Documentation

[![Quarto Publish](https://github.com/edesz/dbt-prefect-starter-docs/actions/workflows/publish.yml/badge.svg)](https://github.com/edesz/dbt-prefect-starter-docs/actions/workflows/publish.yml) ![Static Badge](https://img.shields.io/badge/MIT-License?style=for-the-badge&label=LICENSE&color=%2326ED46) ![Python](https://img.shields.io/badge/python-%233670A0.svg?style=for-the-badge&logo=python&logoColor=ffdd54) ![Maintained](https://img.shields.io/badge/Maintained%3F-yes-green.svg) ![GitHub stars](https://img.shields.io/github/stars/edesz/dbt_prefect_starter) 

This repository creates documentation for the [dbt Prefect starter project](https://github.com/edesz/dbt_prefect_starter) using [Quarto](https://quarto.org/).

## Project Structure

This project follows the standard Quarto structure

1. `_quarto.yml`
   - this is the main configuration file for project metadata, themes, and navigation
2. `index.qmd`
   - this is the primary landing page or main document source
3. `pages`
   - this directory containing individual pages

## Prerequisites

Make sure you have [installed the Quarto CLI](https://quarto.org/docs/get-started/) on your machine.

## Usage

### Preview the project locally with live-reload

To compile the project locally and view your changes, run

```bash
make quarto-preview
```

The compiled output will be generated inside the `_site/` directory by default. 

### Render the complete project to its final output format

To generate the complete Quarto project, use

```bash
make quarto-render
```

### Deployment

This project can be published to GitHub Pages using Github Actions.

First, ensure that Github Actions can wrire to the repository

1. go to the repository Settings
2. under Actions, select Workflow permissions and select *Read and write permissions*

Next, [create a _publish.yml file required by the Github Action](https://quarto.org/docs/publishing/github-pages.html#publish-action)

```bash
make quarto-publish-gh-pages
```

Next, move the `.github/` sub-folder from the `resources/` folder into the project's root directory.

Finally, push changes to the `main` branch using

```bash
git add .
git commit -m "<your-commit-message-here>"
git push origin main
```

which will trigger the Github Action. All contents are then rendered and published to Github Pages.

## Directory Structure

### Quarto Configuration

```bash
.
├── index.qmd
└── _quarto.yml
```

### Documentation Pages (Quarto Markdown Files)

```bash
.
├── community
│   └── CODE_OF_CONDUCT.md
├── LICENSE.md
└── pages
    ├── 01-pre-requisites.qmd
    ├── 02-quickstart.qmd
    ├── 03-directory-structure.qmd
    ├── 04-authoring-dbt-models.qmd
    ├── 05-document-and-test-models.qmd
    ├── 06-motivation.qmd
    ├── 07-opinions.qmd
    ├── 08-usage.qmd
    ├── 09-customisations.qmd
    ├── 10-contributing.qmd
    ├── 11-citation.qmd
    └── images
        ├── .gitkeep
        └── template_logo.png
```

Note that the following files are identical to the corresponding files from the [dbt Prefect starter repository](https://github.com/edesz/dbt_prefect_starter)

1. [`community/CODE_OF_CONDUCT.md`](https://github.com/edesz/dbt_prefect_starter/blob/main/resources/community/CODE_OF_CONDUCT.md)
2. [`LICENSE.md`](https://github.com/edesz/dbt_prefect_starter/blob/main/LICENSE.md)

### Makefile

```bash
.
└── Makefile
```

### Continuous Integration

```bash
.
└── resources
    └── .github
        └── workflows
            └── publish.yml
```

### Version Control

```bash
.
└── .gitignore
```

### Github Repository Administration

```bash
.
└── robots.txt
```

### Github Repository Documentation

```bash
.
└── README.md
```

--------
