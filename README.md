# mobifreaks/.github

Shared setup for the [Mobifreaks](https://munawarahmed.com/mobifreaks) template repos.

- `profile/README.md`: the org's profile page on GitHub.
- `.github/workflows/deploy-demo.yml`: reusable workflow that publishes a template's live demo to GitHub Pages.
- `workflow-templates/demo.yml`: the caller each repo adds (Actions, New workflow, "Mobifreaks demo").
- `templates/README.md`: the README every template repo follows.

## Adding a demo to a repo

1. Add `.github/workflows/demo.yml` from `workflow-templates/demo.yml`.
2. Settings, Pages, Source: **GitHub Actions**.
3. The footer must link to `https://munawarahmed.com/mobifreaks`, or the deploy fails.
4. Add the `portfolio-demo` topic so munawarahmed.com lists it.

What the workflow does on every push to the default branch: copies the files, adds `noindex` to the demo's
pages (never to the source, so downloads stay clean), checks the credit link and every local link and asset,
then deploys to Pages and, if the org secret `SITE_DEPLOY_HOOK` is set, rebuilds munawarahmed.com.

Callers pin `@v1`. Move the tag only for compatible changes.
