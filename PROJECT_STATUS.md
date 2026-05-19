# WellNest Participant Manual: Architecture and Progress

Last updated: 2026-05-19

## Project purpose

This repository hosts the participant-facing WellNest user manual as a GitHub Pages website.

The manual is intended for study participants, especially postpartum mothers, rather than software developers. Its main purpose is to help participants install the apps, grant permissions, complete surveys, keep the app running, and contact the research team when needed.

## Repository architecture

```text
wellnest-participant-manual/
  README.md
  PROJECT_STATUS.md
  .gitignore
  .gitattributes
  .github/
    workflows/
      pages.yml
  docs/
    _config.yml
    Gemfile
    index.md
    setup.md
    permissions.md
    surveys.md
    settings.md
    troubleshooting.md
    checklist.md
    assets/
      images/
```

## Website stack

- Hosting: GitHub Pages
- Build system: GitHub Actions
- Static site generator: Jekyll
- Theme: Just the Docs
- Site source directory: `docs/`
- Deployment workflow: `.github/workflows/pages.yml`
- Expected public URL: `https://qiluojun.github.io/wellnest-participant-manual/`

## Key configuration

The Jekyll configuration is in `docs/_config.yml`.

Important settings:

- `theme: just-the-docs`
- `baseurl: "/wellnest-participant-manual"`
- Search is enabled.
- Heading anchors are enabled.
- The support email is shown in the footer and auxiliary link area.

The GitHub Actions workflow builds from the `docs/` directory and uploads `docs/_site` to GitHub Pages.

The workflow was adjusted to avoid a GitHub Pages API 404 from `actions/configure-pages@v5`. It now builds directly with:

```bash
bundle exec jekyll build --baseurl "/wellnest-participant-manual"
```

## Documentation structure

- `docs/index.md`: Friendly landing page with study summary, Start here links, Quick Checklist link, and support email.
- `docs/setup.md`: Firebase invitation flow, installing both WellNest and WellNest Health, Android install permissions, and installation failure guidance.
- `docs/permissions.md`: Permission configuration workflow, notification settings, Past Health Data, completion confirmation, and when WellNest Health can be uninstalled.
- `docs/surveys.md`: Pre-Study Survey, pilot phase, daily survey table, Morning Survey, Evening Survey, Weekly Survey, and app messages.
- `docs/settings.md`: Region/language settings, survey reminder times, Help screen, Support Resources, manual upload, background running, and end-of-study note.
- `docs/troubleshooting.md`: FAQ-style troubleshooting with links back to detailed instructions.
- `docs/checklist.md`: Practical Quick Checklist with each item linked to the relevant detailed page or section.

## Image assets

Screenshots were extracted from the original Word manual and placed in:

```text
docs/assets/images/
```

The extracted files were renamed from generic Word media names such as `image2.png` to descriptive names such as:

- `firebase-invitation-email.png`
- `permission-configuration-page.png`
- `survey-reminder-notification-categories.png`
- `daily-survey-card.png`
- `data-upload-screen.png`
- `app-closed-notification.png`

## Completed development progress

1. Read the original request and the existing `WellNest_User_Manual_revised.docx`.
2. Extracted the original manual text and identified the main participant workflows.
3. Extracted 35 screenshots from the DOCX file.
4. Renamed screenshot assets with clear, maintainable filenames.
5. Reorganized the Word manual into multiple Markdown pages suitable for mobile and web reading.
6. Added Jekyll front matter to all Markdown pages.
7. Added internal navigation links between checklist items, detailed pages, and troubleshooting sections.
8. Preserved the required research context:
   - The research team is from The Center for Spatial Information Science, The University of Tokyo.
   - The study explores Passive Mobile Sensing technology for understanding mothers' well-being during the postpartum period.
   - The study includes an approximately one-week pilot period and a 12-week formal data collection period.
9. Preserved the public support email:
   - `study-support@mcl.iis.u-tokyo.ac.jp`
10. Avoided exposing private Firebase links, APK direct links, tokens, or other internal credentials.
11. Added Just the Docs/Jekyll configuration files.
12. Added GitHub Actions deployment workflow for GitHub Pages.
13. Added `.gitignore` for Jekyll build artifacts.
14. Updated `README.md` with deployment and local preview instructions.
15. Fixed the GitHub Actions workflow after `actions/configure-pages@v5` returned a Pages API 404.
16. Checked that local Markdown links and image references resolve.
17. Fixed participant-facing image paths by using Jekyll `relative_url` with absolute site paths, so images work under the GitHub Pages project `baseurl`.
18. Fixed internal page and section links by replacing `.md` links with pretty permalink URLs such as `/setup/` and `/surveys/#pre-study-survey`, also wrapped with `relative_url`.

## Manual confirmation still recommended

Before sharing the site publicly with participants, confirm:

- The GitHub Pages workflow completes successfully on GitHub.
- The public URL is accessible:
  `https://qiluojun.github.io/wellnest-participant-manual/`
- Screenshot names and placements are correct.
- The Firebase App Distribution instructions match the actual invitation emails participants receive.
- The support email is still the correct public contact address.
- The compensation/end-of-study wording is approved for public participant-facing documentation.
- No screenshot contains information that should be hidden before public release.

## Suggested next steps

1. Commit and push the latest workflow fix and this progress document.
2. In GitHub repository settings, confirm:
   - Pages source is set to GitHub Actions.
   - Actions are enabled for the repository.
3. Re-run the GitHub Pages workflow.
4. Review the published site on desktop and mobile.
5. Invite the teacher or research collaborator to the repository for content review.

## Local preview support

The site can be previewed locally without committing or pushing to GitHub, as long as Ruby and Bundler are installed:

```bash
cd docs
bundle install
bundle exec jekyll serve
```

Then open:

```text
http://localhost:4000/wellnest-participant-manual/
```

This local URL uses the same `baseurl` as the GitHub Pages deployment, so image paths and internal links can be tested before publishing.
