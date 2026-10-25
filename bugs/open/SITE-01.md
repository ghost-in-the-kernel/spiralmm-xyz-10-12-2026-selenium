<!-- Filed by Suite Builder: a system bug. To close it yourself, move this file to bugs/closed/. -->
# SITE-01: 11 pages show real content but answer 404: the site is served through its error page

Filed from the crawl of 2026-10-25, by Suite Builder: the site's own defect (KNOWN-ISSUES.md has it in full).

**What it blocks:** the status check of each test that opens one of the pages below: they answer the error while showing a page of their own. The rest of each test runs; only the status does not count while this bug is open.

**Why it matters:** A visitor sees each page, but search engines, link checkers and monitoring trust the status: they treat these pages as missing, so they may never appear in search results, and every check calls them broken.

**Likely fix:** Serve each page with status 200: a single-page app behind a CDN usually needs its error response (the one that returns index.html) set to 200, or each route pre-rendered as its own file.

**Where:**

- https://spiralmm.com/contact/: answered 404, drew "Let's Build Something"
- https://spiralmm.com/careers/: answered 404, drew "Careers"
- https://spiralmm.com/careers/ai-engineer-computer-vision/: answered 404, drew "AI Engineer (Computer Vision)"
- https://spiralmm.com/careers/nodejs-developer/: answered 404, drew "Node.js Developer"
- https://spiralmm.com/careers/uiux-designer/: answered 404, drew "UI/UX Designer"
- https://spiralmm.com/projects/: answered 404, drew "Projects"
- https://spiralmm.com/projects/siv/: answered 404, drew "Members Only, By Design."
- https://spiralmm.com/careers/devops-engineer/: answered 404, drew "DevOps Engineer"
- https://spiralmm.com/careers/product-owner/: answered 404, drew "Product Owner"
- https://spiralmm.com/careers/nextjs-frontend-developer/: answered 404, drew "Next.js Frontend Developer"
- https://spiralmm.com/careers/react-native-developer/: answered 404, drew "React Native Developer"

**How it closes:** a rebuild from a new crawl that no longer finds it removes this file (one line goes to
bugs/FIXED.md), and its tests count again. To close it yourself (it will not be fixed, or another ticket tracks
it), move this file to bugs/closed/: its tests count again. A rebuild that still finds the defect files it again,
so it is looked at again.
