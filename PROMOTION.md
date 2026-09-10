# Manual promotion

Changes move from `blog-staging` to `blog` only after an explicit review. No workflow, webhook or scheduled task promotes automatically.

## Review gate

1. Identify the exact `blog-staging` commit being considered.
2. Confirm its GitHub Actions build and Pages deployment succeeded.
3. Inspect the published home page and every affected page.
4. Check images, links, navigation, responsive overflow and the browser console when relevant.
5. Summarize the result and decide deliberately whether to promote it.

## Promotion

After the review gate passes, copy the reviewed staging snapshot into `blog` as one coherent commit. Include the source staging commit in the production commit message:

```text
Promote blog-staging <full commit SHA>
```

Production runs the same build, link checks and editorial trials. Publishing remains disabled until the production Pages site is intentionally launched.

If an urgent change is ever made directly in production, review it and copy it back to staging before beginning the next experiment. This keeps staging as the place where future changes start.
