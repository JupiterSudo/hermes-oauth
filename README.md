# hermes-oauth

Public home page, privacy policy and terms of service for **Hermes**, a personal single-user automation assistant, used for Google OAuth brand verification.

Live at <https://jupitersudo.github.io/hermes-oauth/>. Plain static HTML plus `style.css`, published by GitHub Pages from `main`, folder `/`. There is no build step; push to `main` to deploy.

The app name on the OAuth consent screen must match the name on the home page ("Hermes"). The consent screen's home page, privacy policy and terms URLs should be:

- https://jupitersudo.github.io/hermes-oauth/
- https://jupitersudo.github.io/hermes-oauth/privacy.html
- https://jupitersudo.github.io/hermes-oauth/terms.html

## Verify domain ownership in Google Search Console

Google only verifies the brand if the authorised domain `jupitersudo.github.io` is verified in [Search Console](https://search.google.com/search-console) **by the same Google account that owns the Cloud project**. You have to do this yourself:

1. Sign in to Search Console with the Cloud project owner account and choose **Add property → URL prefix**. A "Domain" property needs a DNS record, and you can't add one on github.io.
2. Enter the URL and choose the **HTML tag** method. Copy the `<meta name="google-site-verification" ...>` tag.
3. Put the tag where the placeholder comment is in the `<head>` of `index.html`, then commit, push, wait for Pages to deploy, and click **Verify**. Leave the tag in place afterwards, because Google re-checks it.
4. In Google Cloud Console → Google Auth Platform → Branding, add `jupitersudo.github.io` under **Authorised domains** and submit for verification.

Which URL to use: the tag in this repo can only verify `https://jupitersudo.github.io/hermes-oauth/`. If the branding check then says the home page or domain isn't registered to you, verify the root property `https://jupitersudo.github.io/` as well. To do that, create a `jupitersudo/jupitersudo.github.io` repository (it doesn't exist yet) and put an `index.html` containing the same kind of tag in it. If Google won't accept a github.io URL-prefix property at all, move the site to a custom domain you can verify through DNS.
