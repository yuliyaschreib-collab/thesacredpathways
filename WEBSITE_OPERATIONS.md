# The Sacred Pathways — website operations

## Source of truth

- **Live website:** https://thesacredpathways.net/
- **GitHub repository:** https://github.com/yuliyaschreib-collab/thesacredpathways
- **Default/production branch:** `main`
- **Visibility:** public (never commit passwords, secrets, private drafts, archive records, or personal documents)
- **Website code:** `index.html`
- **Existing image:** `yulia.png`
- **Configured deployment:** GitHub Actions workflow `.github/workflows/azure-static-web-apps-salmon-river-07ebbf21e.yml` targets an Azure Static Web App. Actual deployment must be verified in Actions after each change.

## Working in ChatGPT

The owner can request website edits in the ChatGPT conversation with a connected GitHub app. A maintainer should:

1. Inspect current `main` code before editing. Do not rely on old Cursor/local copies.
2. Make scoped changes directly via the connected GitHub repository, using a branch/PR for major redesigns or a carefully reviewed commit for small safe changes.
3. Check that GitHub Actions deployment succeeds; review logs and fix failed builds.
4. Verify mobile and desktop layouts and public navigation. Preserve SEO metadata and existing working links.
5. Explain clearly which changes were actually deployed and which still require Azure Portal or DNS-provider access.

## Publishing connection: needs a one-time GitHub check

As of 10 November 2026, the GitHub Actions API reports **zero workflow runs** for this repository, including after commits to `main`. The deploy workflow exists and has been updated for a plain HTML site, but a successful Azure deployment from this repository has **not yet been confirmed**. Do not tell the owner that Sacred Pathways edits are live until this is resolved.

Owner/admin action to inspect if it remains at zero: open `https://github.com/yuliyaschreib-collab/thesacredpathways/settings/actions` and verify that GitHub Actions are enabled for the repository. Then check `https://github.com/yuliyaschreib-collab/thesacredpathways/actions` for runs. If the settings allow Actions but no runs appear, investigate account/organisation restrictions and whether the linked Azure Static Web App deployment secret is configured. Do not paste tokens into chat or source files.

## Domain and DNS

A website's *hosting* (Azure) and the domain's *authoritative DNS provider* may be separate. Never assume the DNS is in GitHub or Azure. Confirm the authoritative provider before editing DNS. Do not replace existing A, MX, TXT, or NS records. Do not switch the parent domain's nameservers while adding a `guru` subdomain.

## Separate private archive

Gurudev's Archive is a separate private Azure Static Web App, maintained from the private `guruji-atlas-private` GitHub repository. Never copy the archive, encrypted data, unlock key, or authenticated pages into this public repository.

## Cost/security

Avoid new paid Azure resources or upgrades without the owner's explicit approval. Never put deployment tokens or credentials in source files. Existing Azure SWA deployments use GitHub-managed secrets.
