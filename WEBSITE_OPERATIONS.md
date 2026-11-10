# The Sacred Pathways — website operations

## CRITICAL: incomplete fork, do not deploy to the live domain

As of 10 November 2026, this fork has only `index.html` and `yulia.png`, while the actual public website includes `/pathways/books.html` (interactive route map), `/pathways/pilgrimages.html`, and `/pages/media.html`, among other pages. Earlier Cursor/Claude work had the full website folder, and deployment may be on another GitHub account/Azure subscription. **This fork is not yet a verified copy of the production source.** Do not add an Azure deployment token or publish this fork until the complete live source has been recovered and compared.

In response, the Azure deployment workflow in this repository has been paused for normal pushes/PRs. It is now manual-only with an explicit confirmation gate. The latest attempted deployment before pausing failed for a missing token. The live website was not changed by that failure.

## Source of truth

- **Live website:** https://thesacredpathways.net/
- **GitHub repository:** https://github.com/yuliyaschreib-collab/thesacredpathways
- **Default/production branch:** `main`
- **Visibility:** public (never commit passwords, secrets, private drafts, archive records, or personal documents)
- **Website code:** `index.html`
- **Existing image:** `yulia.png`
- **Important:** the above files are insufficient to reproduce the live site. Do not treat this fork as authoritative until full source restoration.
- **Configured deployment:** GitHub Actions workflow `.github/workflows/azure-static-web-apps-salmon-river-07ebbf21e.yml` targets an Azure Static Web App, but automatic deployments are intentionally paused. The Azure target and credentials are not currently verified.

## Working in ChatGPT

The owner can request website edits in the ChatGPT conversation with a connected GitHub app. A maintainer should:

1. Inspect current `main` code before editing. Do not rely on old Cursor/local copies.
2. Make scoped changes directly via the connected GitHub repository, using a branch/PR for major redesigns or a carefully reviewed commit for small safe changes.
3. Check that GitHub Actions deployment succeeds; review logs and fix failed builds.
4. Verify mobile and desktop layouts and public navigation. Preserve SEO metadata and existing working links.
5. Explain clearly which changes were actually deployed and which still require Azure Portal or DNS-provider access.

## Publishing connection: GitHub Actions enabled, deployment verification pending

On 10 November 2026, the owner enabled Actions on this forked repository in the GitHub Actions tab. A controlled documentation-only commit was used to test the workflow. **Check the actual run result and Azure publication before declaring the deployment verified.**

Owner/admin action to inspect if it remains at zero: open `https://github.com/yuliyaschreib-collab/thesacredpathways/settings/actions` and verify that GitHub Actions are enabled for the repository. Then check `https://github.com/yuliyaschreib-collab/thesacredpathways/actions` for runs. If the settings allow Actions but no runs appear, investigate account/organisation restrictions and whether the linked Azure Static Web App deployment secret is configured. Do not paste tokens into chat or source files.

## Domain and DNS

**Authoritative DNS location supplied by owner (10 November 2026):** Azure tenant `schreibsecondary.onmicrosoft.com`, subscription `6e057eb9-5a68-43d3-a168-f7d205100f6c`, resource group `thesacredpathways.net`, Azure DNS zone `thesacredpathways.net`. [Open record sets in Azure](https://portal.azure.com/#@schreibsecondary.onmicrosoft.com/resource/subscriptions/6e057eb9-5a68-43d3-a168-f7d205100f6c/resourceGroups/thesacredpathways.net/providers/Microsoft.Network/dnszones/thesacredpathways.net/recordsets). A `guru` CNAME should point to `lively-meadow-07fcd1c0f.3.azurestaticapps.net`. **Record creation/validation not yet confirmed.** Do not change parent domain nameservers, apex records or email records.


A website's *hosting* (Azure) and the domain's *authoritative DNS provider* may be separate. Never assume the DNS is in GitHub or Azure. Confirm the authoritative provider before editing DNS. Do not replace existing A, MX, TXT, or NS records. Do not switch the parent domain's nameservers while adding a `guru` subdomain.

## Separate private archive

Gurudev's Archive is a separate private Azure Static Web App, maintained from the private `guruji-atlas-private` GitHub repository. Never copy the archive, encrypted data, unlock key, or authenticated pages into this public repository.

## Cost/security

Avoid new paid Azure resources or upgrades without the owner's explicit approval. Never put deployment tokens or credentials in source files. Existing Azure SWA deployments use GitHub-managed secrets.
