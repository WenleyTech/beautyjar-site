# BeautyJar production site

Static HTML/CSS/JavaScript site prepared for GitHub and Netlify.

## Deployment

1. Create or open the production GitHub repository.
2. Commit the contents of this folder to the repository root.
3. Connect the repository to the BeautyJar Netlify project.
4. Leave the build command empty and set the publish directory to `.`.
5. Test the Netlify preview before changing the production domain.
6. In **Forms**, confirm that `provider-onboarding` and `invited-provider` are detected.
7. Add a form-submission email notification for `hello@beautyjar.com`.

## Paid provider flow

The public provider page links to Stripe Payment Links for Profile and Spotlight. Checkout must remain payment-first. Configure the Stripe success destinations as:

- Profile: `https://beautyjar.com/provider-onboarding?plan=profile`
- Spotlight: `https://beautyjar.com/provider-onboarding?plan=spotlight`

The provider completes onboarding after payment. BeautyJar verifies the submission before publication. If BeautyJar cannot approve the listing, cancel the membership and refund the initial payment. Never put a Stripe secret key in this repository.

## Invited provider flow

Invited providers do not use Stripe. Send one of these private routes with the provider's unique invitation code:

- Profile: `/provider-invitation?type=profile`
- Spotlight: `/provider-invitation?type=spotlight`

Invitations are assigned to one named provider and are nontransferable. Match the submitted email and invitation code against the private invitation register before verification and publication. The invitation pages and terms are `noindex` and are not linked from the public site.

## Launch checks

- Replace prototype provider listings with real, authorized listings before promoting the directory.
- Confirm the production email address and legal entity details.
- Test both forms, spam protection, uploads, confirmation pages, mobile layout, and every Stripe Payment Link.
- After the custom domain is live, confirm that `sitemap.xml` and every internal page and asset resolve on the production server, including case-sensitive paths.
- Add Netlify's production URL and the custom domain to Stripe's allowed/return URLs if Checkout is added later.
