# CrewFlo website

Static site: no build step. Upload this folder as-is.

## Before it goes live
1. Check that support@thecrewflo.com actually receives mail. Every "Book a demo"
   button opens an email to it.
2. Check the Google Play link opens your listing:
   https://play.google.com/store/apps/details?id=com.mittantechnology.crewflo
3. Check where your email is hosted (Namecheap > Domain List > Manage > Nameservers
   and Mail Settings). If the mailbox lives on the WordPress hosting plan, move it
   before you cancel that plan.

The privacy policy and terms (Termly exports, last updated August 26, 2026) are
already in `privacy-policy/index.html` and `terms-and-conditions/index.html`. When
you update them in Termly, re-export and replace the content inside
`<div class="legal-body">`.

Each page is a folder with an `index.html`, so the addresses match the old
WordPress site exactly: /about/, /privacy-policy/ (the link Google Play uses) and
/terms-and-conditions/.

"Get CrewFlo today" buttons open the web app at https://crewflo.vercel.app/#/home.

## Deploy on Vercel
1. Vercel dashboard > Add New > Project. Import from a Git repo containing this
   folder (or run `npx vercel` inside it). Framework preset: Other. No build command.
2. Project > Settings > Domains: add `thecrewflo.com` and `www.thecrewflo.com`.
   Vercel shows the exact DNS records to create.
3. In Namecheap, set only those website records (A for @, CNAME for www).
   Leave MX / mail records alone.
4. Once the new site loads on thecrewflo.com and email still works, cancel the
   WordPress hosting.

`vercel.json` keeps old links working: /privacy-policy/, /privacy (linked from the
terms), /terms-and-conditions/, /about/, /contact/ and /pricing/ all land on the right page.

Font: Archivo (SIL Open Font License), self-hosted in /fonts.
