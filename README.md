# 502 Garage Door Connect

Lead-capture landing page for 502GarageDoorConnect.com — a local referral service
that matches Louisville-area homeowners with independent garage door companies.

## Deploying on GitHub Pages

1. Push `index.html` and `CNAME` to the root of your repo (or to a `/docs` folder —
   just make sure GitHub Pages is pointed at whichever one you use).
2. In your repo: **Settings → Pages → Source** → select the branch/folder
   containing `index.html`.
3. GitHub will give you a default URL like `yourusername.github.io/repo-name`.
   Confirm the site loads there first before touching DNS.

## Pointing 502GarageDoorConnect.com at GitHub Pages

The `CNAME` file in this repo tells GitHub which custom domain to serve — but you
also have to configure DNS at your domain registrar (wherever you bought
502GarageDoorConnect.com) so the domain actually points to GitHub's servers.

At your registrar's DNS settings, add these records:

**For the root domain (502garagedoorconnect.com):**
Add four `A` records, all with host `@`, pointing to GitHub Pages' IP addresses:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**For the www subdomain (optional but recommended):**
Add a `CNAME` record:
```
Host: www
Value: yourusername.github.io
```

Then in your repo's **Settings → Pages**, enter `502garagedoorconnect.com` in the
custom domain field and check **Enforce HTTPS** once it becomes available
(can take up to 24 hours after DNS propagates).

## Before this goes live for real

This is a static front-end only — the form currently just shows a success
message and does not send data anywhere. Before running paid traffic to it:

- [ ] Connect the form to a real backend (Formspree, a Zapier webhook, or a
      custom endpoint) so leads actually reach you
- [ ] Set up instant notification (email/SMS) so you can forward leads to a
      buyer company within minutes, not hours
- [ ] Add a real phone number and email in place of the placeholders
- [ ] Write a proper Privacy Policy page — you're collecting and reselling
      personal contact info, which has real disclosure obligations
- [ ] Set up Google Search Console + submit the site once DNS is live
