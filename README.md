# SSM sending-domain website

This small GitHub Pages site connects https://ssm.dedyn.io to the existing SSM website at https://eyesky93.github.io/ssm/.

The index page redirects immediately using HTML meta refresh, with accessible English/Hebrew links if automatic navigation is unavailable. It contains no scripts, tracking, email addresses or credentials. This is a browser redirect, not an HTTP 301/302 response.

## Finish setup

1. In this repository's Settings → Pages, select Deploy from a branch, master, / (root), then Save.
2. Set Custom domain to ssm.dedyn.io and save before changing DNS. The committed CNAME file declares the same domain.
3. In deSEC's ssm.dedyn.io zone, add an A record set with an empty subname, TTL 3600, and these four values:
   - 185.199.108.153
   - 185.199.109.153
   - 185.199.110.153
   - 185.199.111.153
4. Preserve all existing mail TXT/MX records. Do not add a DNS CNAME at the zone root.
5. Once GitHub provisions the certificate, enable Enforce HTTPS.
6. Verify https://ssm.dedyn.io opens the existing SSM website before submitting the newsletter sender for Google AMP approval.

This repository does not publish or reconfigure the existing SSM repository. Google sender approval remains a separate step.

References:
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- https://developers.google.com/workspace/gmail/ampemail/register
