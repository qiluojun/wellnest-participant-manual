# WellNest Participant Manual: Architecture and Progress

Last updated: 2026-05-20

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
    en/
      android/
        index.md
        setup.md
        permissions.md
        surveys.md
        settings.md
        troubleshooting.md
        checklist.md
      ios/
        index.md
    ja/
      android/
        index.md
        setup.md
        permissions.md
        surveys.md
        settings.md
        troubleshooting.md
        checklist.md
      ios/
        index.md
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

- `docs/index.md`: Version selector for language and phone platform.
- `docs/en/android/`: Existing English Android participant manual.
- `docs/ja/android/`: Japanese Android participant manual translated from the English Android version.
- `docs/en/ios/` and `docs/ja/ios/`: Placeholder iPhone manual entry pages for future content.
- Each Android manual includes setup, permissions, surveys, settings/app use, troubleshooting, and checklist pages.

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
19. Debugged the published-site 404 problems reported in Quick Checklist and the landing page. The root cause was that `permalink: pretty` generates URLs such as `/setup/`, while the Markdown content still linked to `setup.md`.
20. Debugged the missing-image problem. The root cause was that image paths such as `assets/images/example.png` were resolved relative to pretty permalink page paths such as `/setup/`, producing invalid URLs.
21. Updated `README.md` to clarify that the site can be previewed locally with Jekyll before pushing changes to GitHub.
22. Performed static checks confirming:
   - No old `.md` internal links remain in the participant-facing Markdown pages.
   - No bare `assets/images/...` Markdown image references remain.
   - All image files referenced through `/assets/images/...` exist in `docs/assets/images/`.
23. Updated `docs/setup.md` after website review:
   - Added a note in Step 1 telling participants not to open **WellNest Health** immediately after installing it.
   - Revised Step 2 to explicitly ask participants to allow both app installation and Google Play Protect scanning if Android asks.
   - Simplified the Step 2 wording so the installation and scanning instructions are shorter and clearer.
24. Updated `docs/settings.md` so the **App Close Warning** notification category reminder links back to the `Notification settings` section in `docs/permissions.md`.
25. Performed a static check of the latest content edits with `rg` and `git diff`, confirming that the new permission link still uses the project-safe Jekyll `relative_url` pattern.
26. Restructured the site for language/platform versions:
   - English Android moved to `docs/en/android/`.
   - Japanese Android added at `docs/ja/android/`.
   - English iPhone and Japanese iPhone placeholder entry pages added.
   - Root `docs/index.md` changed into a manual selector.
27. Translated the Android participant manual into Japanese while temporarily reusing the English Android screenshot assets.
28. Added stable ASCII section anchors to Japanese pages where internal links target sections.
29. Updated README and `_config.yml` for the multi-version manual structure.
30. Performed static checks confirming:
   - No old root-level `/setup/`, `/permissions/`, `/surveys/`, `/settings/`, `/troubleshooting/`, or `/checklist/` links remain.
   - All `relative_url` page targets resolve to a page permalink.
   - All referenced image files exist.
31. Updated the Japanese Android manual image references to use Japanese screenshot assets under `docs/assets/image_jp/` wherever available.
    - Mapped the Japanese evening survey notification banner to `Snipaste_2026-05-20_15-32-40.png`.
    - Mapped the Japanese admin message screenshot to `Snipaste_2026-05-20_15-19-32.png`.
    - Kept English fallback assets only where no corresponding Japanese asset exists yet.
    - Re-ran a static check confirming all Japanese Android image references point to existing files.
32. Checked the English and Japanese Android quick checklist links.
    - Added explicit stable ASCII anchors to the English Android target sections used by checklist links.
    - Confirmed the Japanese Android target sections already have matching stable anchors.
    - Re-ran a static check confirming all checklist `relative_url` page targets and section anchors resolve.
    - Attempted a local Jekyll build, but Bundler reported `jekyll` was missing and suggested running `bundle install`.

## Latest debug summary

The site has been restructured into a language/platform manual selector.

Current participant-facing entry points are:

```markdown
{{ '/en/android/' | relative_url }}
{{ '/ja/android/' | relative_url }}
{{ '/en/ios/' | relative_url }}
{{ '/ja/ios/' | relative_url }}
```

Android manual pages now use version-specific `relative_url` paths:

```markdown
{{ '/en/android/setup/' | relative_url }}
{{ '/ja/android/surveys/#pre-study-survey' | relative_url }}
{{ '/assets/images/firebase-invitation-email.png' | relative_url }}
{{ '/assets/image_jp/daily-survey-card.png' | relative_url }}
```

This keeps links and images project-site-safe under:

```text
/wellnest-participant-manual/
```

Local build/testing was revisited after installing Ruby 3.4. If Bundler still appears to use `C:/Ruby40-x64`, open a fresh Ruby 3.4 terminal or adjust PATH so `ruby`, `gem`, and `bundle` resolve to the Ruby 3.4 installation before running `bundle install`.

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

1. Add or rename the remaining missing Japanese-specific assets if needed:
   - `firebase-invitation-email.png`
   - `google-play-protect-scan.png`
   - `wellnest-health-initial-screen.png`
   - `recent-apps-lock-wellnest.png`
2. Add the English iPhone and Japanese iPhone manual content under `docs/en/ios/` and `docs/ja/ios/`.
3. Commit and push the multi-version restructure, Japanese Android manual, and this progress document.
4. In GitHub repository settings, confirm:
   - Pages source is set to GitHub Actions.
   - Actions are enabled for the repository.
5. Re-run the GitHub Pages workflow.
6. Review the published site on desktop and mobile.
7. Invite the teacher or research collaborator to the repository for content review.

## Local preview support

The site can be previewed locally without committing or pushing to GitHub, as long as Ruby and Bundler are installed:

```bash
cd docs
bundle install
bundle exec jekyll serve --baseurl "/wellnest-participant-manual"
```

Then open:

```text
http://localhost:4000/wellnest-participant-manual/
```

This local URL uses the same `baseurl` as the GitHub Pages deployment, so image paths and internal links can be tested before publishing.
