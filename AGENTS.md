# daigof Agent Guide

This repository is the source repository for Diego Fortes' public profile and CV.

## CV Source Of Truth

- `Diego-Fortes-CV.md` is the only canonical CV source in this repo.
- Do not keep generated CV HTML or PDF artifacts in this repo.
- Public CV assets are published from the sibling `nobs-apps` repository at:
  - `https://nobsapps.co/Diego-Fortes-CV.html`
  - `https://nobsapps.co/Diego-Fortes-CV.pdf`

## CV Publishing Process

When `Diego-Fortes-CV.md` changes:

1. Regenerate the HTML from `Diego-Fortes-CV.md` and write the result to `../nobs-apps/Diego-Fortes-CV.html`.
2. Preserve the existing CV presentation shell in the website copy unless the user asks for a design change.
3. Generate the PDF from the website HTML with Playwright:

   ```sh
   playwright pdf "file:///Users/diegofortes/proj/nobs-apps/Diego-Fortes-CV.html" ../nobs-apps/Diego-Fortes-CV.pdf
   ```

4. From `../nobs-apps`, run:

   ```sh
   pnpm build
   ```

5. Verify that the Cloudflare Pages build output contains:
   - `build/Diego-Fortes-CV.html`
   - `build/Diego-Fortes-CV.pdf`

The `daigof/README.md` should link to the public `nobsapps.co` HTML and PDF assets, plus the Markdown source on GitHub.
