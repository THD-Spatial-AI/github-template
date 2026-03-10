
# THD-Spatial Repository Template

[![MkDocs](https://github.com/THD-Spatial/github-template/actions/workflows/docs.yml/badge.svg)](https://thd-spatial.github.io/github-template)

This repository is a template for projects under the `THD-Spatial` GitHub group. It provides a basic structure, documentation, and guidance to help you prepare repositories for internal collaboration and open-source release.

## What this template includes

- `README.md` (project overview and usage guidance)
- `CONTRIBUTING.md` (contribution workflow and expectations)
- `LICENSE` (required before making a repository public)
- `docs/` (documentation pages for naming conventions and open-source readiness)
- `mkdocs.yml` (MkDocs configuration for documentation site generation)

## Before making a repository public

Use the open-source readiness checklist before publishing a repository under `THD-Spatial`.

- **Checklist:** [Open Source Checklist](docs/getting-started/open-source-checklist.md)

The checklist covers:

- essential repository files (license, README, contributing, code of conduct)
- Git LFS setup for large files
- optional but recommended files
- final review steps before publication

## Repository naming

All repositories under `THD-Spatial` should follow a consistent naming convention.

- **Guidelines:** [Repository Naming Guidelines](docs/getting-started/repository-naming.md)

## Required files for public repositories

### 1. README (required)

> [!IMPORTANT]
> Every repository must include a `README.md` file that explains the project purpose, setup, and usage.

At minimum, the README should include:

- project title and description
- purpose / scope
- installation and usage instructions
- contribution guidance (or link to `CONTRIBUTING.md`)
- license information (or link to `LICENSE`)

### 2. License (required)

A public repository must include a license. Without a license, others do not have clear legal permission to use, modify, or distribute the code.
> [!IMPORTANT]
> Repositories under `THD-Spatial` must include a `LICENSE` file before being made public.

Useful resource:

- [Choose a License](https://choosealicense.com/)

### 3. CONTRIBUTING & Code of Conduct (recommended, required for community-facing repos)

1. Add a `CONTRIBUTING.md` file to explain how contributors should report issues, propose changes, and submit pull requests.

2. Add a `CODE_OF_CONDUCT.md` file to help set expectations for respectful collaboration and create a welcoming project environment.

A common choice:

- [Contributor Covenant](https://www.contributor-covenant.org/)

### 4. Git LFS for large files

> [!IMPORTANT]
> Use Git LFS for large files (especially datasets, binaries, media, and generated assets) to keep the Git repository manageable. For more information, official platform documentation can be found at [Git LFS](https://git-lfs.com/).

Basic setup:

```bash
git lfs install
git lfs track "*.psd"
git lfs track "*.zip"
...
```

Then commit `.gitattributes` and your files as usual.

> [!NOTE]
> If you publish releases and want Git LFS files included in release archives, enable:
>
> **Settings → Archives → Include Git LFS objects in archives**
> ![GitHub release archives setting](docs/assets/getting-started/archives_setting_screenshot.png)

### 5. Documentation (MkDocs)

This template uses [MkDocs](https://www.mkdocs.org/) with the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme for project documentation.

Documentation source files are located in the `docs/` directory.

### Run documentation locally

1. Install dependencies:

    ```bash
    pip install -r docs/requirements.txt
    ```

2. Start the local docs server:

    ```bash
    mkdocs serve
    ```

3. Then open:

    ```bash
    http://localhost:8000/
    ```

    > [!NOTE]
    > port may vary based on configuration*

### Hosting documentation with GitHub Pages

This repository deploys documentation to **GitHub Pages** using a GitHub Actions workflow:

- Workflow: `.github/workflows/docs.yml`

The workflow builds the MkDocs site and publishes it automatically when changes are pushed to the configured branch (for example, `main`).

> [!TIP]
> If your repository is private, then the workflow will fail without GitHub Pro or Enterprise. In that case you disable the workflow temporarily until you are ready to make the repository public. To disable the workflow, go to the **Actions** tab, select the workflow, and click "Disable workflow" in the right sidebar.
> ![disable workflow screenshot](docs/assets/getting-started/disable-workflow.png)

#### Typical deployment flow

1. Update documentation files in `docs/` (and/or `mkdocs.yml`)
2. Commit and push changes to the default branch
3. GitHub Actions runs the docs workflow
4. The site is deployed to GitHub Pages automatically

#### Notes

- Make sure **GitHub Pages** is enabled in repository settings
- The Pages source should be set to **GitHub Actions**
- If using a project repository site, the published URL is typically:

```bash
https://<org-name>.github.io/<repo-name>/
```

(e.g., documentation for this repo can be accessed at <https://thd-spatial.github.io/github-template/>)

---

### 6. Optional but useful files

Depending on the project, consider adding:

- `CHANGELOG.md` — track notable changes
- `CODEOWNERS` — define review ownership
- `.github/ISSUE_TEMPLATE/` — issue templates
- `.github/pull_request_template.md` — PR template
- `SECURITY.md` — vulnerability reporting policy
- `SUPPORT.md` — support and contact guidance

> [!CAUTION]
> **TO ALL MAINTAINERS:** Please review the open-source readiness checklist and ensure all required files are included before making a repository public. This helps set clear expectations for users and contributors, and ensures legal clarity around usage and contributions.
>
> This template is intended to be practical and easy to adapt. Keep it lightweight, take some time to remove sections you do not need **(Including this one)**, and update links/paths if you rename files in `docs/`.
