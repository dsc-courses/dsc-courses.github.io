# Updating the Course List

This document describes how to find and add new course offerings to the dsc-courses.github.io website.

## Where course data lives

- `_modules/01-ug-courses.md` -- Undergraduate DSC courses
- `_modules/02-ug-cogsci.md` -- Undergraduate COGS courses
- `_modules/03-grad-courses.md` -- Graduate DSC courses

Each course has an `offerings` list in YAML front matter. Entries are ordered newest-first with the format:

```yaml
- quarter: Spring 2026 (Instructor)
  url: https://dsc-courses.github.io/dsc10-2026-sp
```

## Step 1: Find new course repos on GitHub

Most course websites are hosted under the `dsc-courses` GitHub org:

```bash
gh repo list dsc-courses --limit 200 --json name --jq '.[].name' | sort
```

Filter for the target year (e.g. `| grep 2026`) to find new repos. The naming convention is typically `{course}-{year}-{quarter}`, e.g. `dsc10-2026-wi`, `dsc80-2026-sp`.

Some exceptions to watch for:
- **DSC 20** uses a single repo (`dsc20-website`, redirects to dsc20.org) for all quarters
- **DSC 100** is hosted at `bsalimi.github.io/dsc100-{quarter}` (e.g. `dsc100-wi26`, `dsc100-sp26`)
- **DSC 148** is hosted at `shangjingbo1226.github.io/teaching/...`
- **DSC 180AB (Capstone)** is at `dsc-capstone.org/{year}/`
- Some repos use non-standard names (e.g. `DSC40B_SP26`, `DSC95-2025-Fall`)
- Some courses redirect to custom domains (e.g. dsc10.com, dsc80.com, dsc106.com, dsc140a.com)

## Step 2: Verify each site is live

For each new repo found, check that its GitHub Pages site is actually live:

```
https://dsc-courses.github.io/{repo-name}
```

Fetch the page and confirm:
1. The site loads (not 404)
2. The course name, quarter, and instructor(s)

Some sites redirect to custom domains -- follow the redirect and check that page instead.

For courses hosted outside `dsc-courses` (DSC 100, DSC 148, etc.), check the instructor's known URL pattern with the new quarter suffix.

## Step 3: Add entries to the YAML

For each confirmed offering, add a new entry at the **top** of that course's `offerings` list (newest first). Include the instructor name in parentheses if found on the site.

If a course doesn't exist yet in the file (e.g. a brand new course number), add a new course block in numeric order with `course`, `title`, and `offerings` fields. Check the course website for the official title.

## Step 4: Verify

Build the site locally or just review the YAML to make sure formatting is correct. Each entry needs `quarter` and `url` fields with consistent indentation (6 spaces for the dash, 8 spaces for `url`).

## Quarters to check each update cycle

| When updating     | Add these quarters                          |
|-------------------|---------------------------------------------|
| Start of Fall     | Summer, Fall of current academic year       |
| Start of Winter   | Winter                                      |
| Start of Spring   | Spring                                      |
| Catch-up (like now) | All quarters since last update             |
