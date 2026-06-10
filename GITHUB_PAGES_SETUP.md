# Avenue website: GitHub Pages setup

This guide publishes the website in this folder:

`/Users/mymac/Documents/avenue_web`

Recommended GitHub repository:

`https://github.com/mike-avenue-dev/avenue-website`

The website will use:

`https://avenuecy.com`

## Important before starting

- Do not upload the Avenue Flutter app to this repository.
- Do not add `.env`, passwords, API keys, or secret tokens.
- This folder is already a separate Git repository using the `main` branch.
- The website already contains `CNAME` with `avenuecy.com`.
- The website already contains `.nojekyll`, which tells GitHub Pages to serve the static files directly.
- Keep all email-related DNS records. Do not remove MX or email TXT records.

## Part 1: Create the GitHub repository

1. Sign in to [GitHub](https://github.com).
2. Click the `+` button in the top-right corner.
3. Select **New repository**.
4. Set **Owner** to `mike-avenue-dev`.
5. Set **Repository name** to `avenue-website`.
6. Add an optional description:

   `Landing website for Avenue — discover events and venues in Limassol.`

7. Select **Public**.

   GitHub Pages works with public repositories on GitHub Free.

8. Do **not** select:

   - Add a README file
   - Add `.gitignore`
   - Choose a license

   The local project already contains its own files and Git repository.

9. Click **Create repository**.
10. Leave the new repository page open. You will need its URL.

## Part 2: Open the website in VS Code

1. Open VS Code.
2. Select **File → Open Folder**.
3. Open:

   `/Users/mymac/Documents/avenue_web`

4. Select **View → Source Control**.
5. Confirm that the website files appear under **Changes**.

## Part 3: Connect the local folder to GitHub

The most reliable method is through the VS Code terminal.

1. In VS Code, select **Terminal → New Terminal**.
2. Confirm that the terminal path ends with:

   `avenue_web`

3. Add the GitHub repository as the remote:

```bash
git remote add origin https://github.com/mike-avenue-dev/avenue-website.git
```

4. Confirm the remote:

```bash
git remote -v
```

You should see `origin` pointing to the new `avenue-website` repository.

If Git reports `remote origin already exists`, inspect it:

```bash
git remote -v
```

Only if it points to the wrong repository, replace it:

```bash
git remote set-url origin https://github.com/mike-avenue-dev/avenue-website.git
```

## Part 4: Make the first commit and push

You can use the VS Code Source Control panel:

1. Click **Stage All Changes** (`+`) in Source Control.
2. Enter this commit message:

   `Create Avenue landing website`

3. Click **Commit**.
4. Click **Publish Branch**, **Sync Changes**, or **Push**.
5. Sign in to GitHub if VS Code asks.
6. Confirm that the destination branch is `main`.

Alternatively, use the VS Code terminal:

```bash
git add .
git commit -m "Create Avenue landing website"
git push -u origin main
```

Refresh the repository page on GitHub. You should see `index.html`, `styles.css`, `CNAME`, and the other website files.

## Part 5: Verify ownership of avenuecy.com

GitHub recommends verifying the domain before connecting it to a repository.

1. On GitHub, click your profile picture.
2. Open **Settings** for your personal GitHub account.
3. In the left sidebar, open **Pages**.
4. Under verified domains, click **Add a domain**.
5. Enter:

   `avenuecy.com`

6. GitHub will provide a DNS `TXT` record. It will look similar to:

   - Type: `TXT`
   - Name: `_github-pages-challenge-mike-avenue-dev`
   - Value: a unique verification code supplied by GitHub

7. Open the DNS management page at the company where `avenuecy.com` is managed.
8. Add the exact TXT record GitHub provides.
9. Do not change or remove the existing MX, SPF, DKIM, or other email records.
10. Return to GitHub and click **Verify** after the TXT record is detected.
11. Keep the verification TXT record permanently.

DNS updates can be quick, but may take up to 24 hours.

## Part 6: Enable GitHub Pages

1. Open the `avenue-website` repository on GitHub.
2. Click **Settings**.
3. In the left sidebar, under **Code and automation**, click **Pages**.
4. Under **Build and deployment**, set:

   - Source: **Deploy from a branch**
   - Branch: `main`
   - Folder: `/(root)`

5. Click **Save**.

GitHub will start a Pages deployment. It may take several minutes.

The temporary address should look like:

`https://mike-avenue-dev.github.io/avenue-website/`

You can inspect deployment progress under the repository’s **Actions** tab.

## Part 7: Add avenuecy.com in GitHub Pages

Do this in GitHub before changing the website DNS records.

1. Return to the repository’s **Settings → Pages**.
2. Find **Custom domain**.
3. Enter:

   `avenuecy.com`

4. Click **Save**.

The repository already has a `CNAME` file containing `avenuecy.com`. If GitHub creates or updates this file itself, pull that GitHub commit before making more local changes:

```bash
git pull
```

## Part 8: Configure the domain DNS

Open the DNS settings for `avenuecy.com`.

### Apex domain records

Add these four `A` records:

| Type | Name/Host | Value |
|---|---|---|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

Use the default TTL or `3600`.

### WWW record

Add this record:

| Type | Name/Host | Value |
|---|---|---|
| CNAME | `www` | `mike-avenue-dev.github.io` |

Do not include `/avenue-website` in the CNAME value.

This lets both addresses work:

- `avenuecy.com`
- `www.avenuecy.com`

GitHub should redirect `www.avenuecy.com` to `avenuecy.com`.

### Records to preserve

Do not remove or change records used by email, including:

- MX records
- SPF TXT records
- DKIM records
- DMARC records
- Records required by your email provider

Only remove an existing `A`, `AAAA`, `ALIAS`, `ANAME`, or `CNAME` record when it conflicts with the new website record for the same host (`@` or `www`).

Do not create a wildcard record such as `*.avenuecy.com`.

## Part 9: Check the DNS from your Mac

Open Terminal and run:

```bash
dig avenuecy.com +noall +answer -t A
```

The result should eventually contain all four GitHub Pages IP addresses.

Check `www`:

```bash
dig www.avenuecy.com +noall +answer
```

The result should show a CNAME pointing to:

`mike-avenue-dev.github.io`

DNS changes may take up to 24 hours to propagate.

## Part 10: Enable HTTPS

1. Return to the repository’s **Settings → Pages**.
2. Wait until GitHub reports that the DNS check is successful.
3. Select **Enforce HTTPS**.

The checkbox may remain unavailable while GitHub creates the TLS certificate. This can take up to 24 hours after the DNS records are correct.

After HTTPS is active, test:

- `https://avenuecy.com`
- `https://www.avenuecy.com`
- `https://avenuecy.com/privacy.html`
- `https://avenuecy.com/terms.html`
- `https://avenuecy.com/support.html`
- `https://avenuecy.com/delete-account.html`

## Part 11: Publish future website changes

After editing files in VS Code:

1. Open **Source Control**.
2. Review the changed files.
3. Stage the files.
4. Enter a clear commit message.
5. Click **Commit**.
6. Click **Push** or **Sync Changes**.

Terminal equivalent:

```bash
git add .
git commit -m "Describe the website change"
git push
```

GitHub Pages automatically republishes the website after a push to `main`. Updates normally appear within several minutes.

## Troubleshooting

### The website shows a 404

- Confirm `index.html` is in the repository root.
- Confirm Pages uses `main` and `/(root)`.
- Check the repository’s **Actions** tab for a failed Pages deployment.
- Wait up to 10 minutes after the initial deployment.

### The custom domain does not work

- Confirm the custom domain in **Settings → Pages** is exactly `avenuecy.com`.
- Confirm `CNAME` contains only `avenuecy.com`.
- Confirm all four apex `A` records are present.
- Confirm `www` points to `mike-avenue-dev.github.io`, not to the repository URL.
- Remove conflicting records for `@` or `www`.
- Allow up to 24 hours for DNS propagation.

### HTTPS is unavailable

- Wait until GitHub’s DNS check succeeds.
- Confirm both the apex and `www` DNS records are configured.
- Do not point `www` directly to `avenuecy.com`.
- Wait up to 24 hours for certificate generation.

### Email stops working

Website `A` and `CNAME` records do not normally affect email. If email stops working, confirm that the domain’s MX, SPF, DKIM, and DMARC records were not deleted or replaced.

## Official GitHub documentation

- [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [Configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Managing a custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [Verifying a custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages)
