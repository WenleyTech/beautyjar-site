# BeautyJar production site

Static HTML/CSS/JavaScript site prepared for GitHub and Netlify.

## Deploy

1. Create or open the production GitHub repository.
2. Commit the contents of this folder to the repository root.
3. In Netlify, select **Add new site → Import an existing project → GitHub**.
4. Leave the build command empty and set the publish directory to `.`.
5. Deploy, then attach `beautyjar.com` under **Domain management** and follow Netlify's DNS instructions.
6. In **Forms**, confirm that `provider-application` is detected and submit one live test application.

## Stripe

The application currently collects no payment and says payment follows approval. Stripe Products alone do not create checkout links. Create a recurring Price and Payment Link for each approved membership (Profile and Spotlight), then send the appropriate link after an application is approved. Never put a Stripe secret key in this repository.

## Launch checks

- Replace prototype provider listings with real, authorized listings before promoting the directory.
- Confirm the production email address and legal entity details.
- Test the application form, spam protection, confirmation page, mobile layout, and every Stripe Payment Link.
- After the custom domain is live, confirm that `sitemap.xml` and every internal page and asset resolve on the production server, including case-sensitive paths.
- Add Netlify's production URL and the custom domain to Stripe's allowed/return URLs if Checkout is added later.
