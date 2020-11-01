---
layout: documentation
title: Protect The Lounge with HTTPS
description: Easily configure The Lounge to be served over HTTPS for better security and privacy
---

In this guide, we will see how to easily configure The Lounge to be served over [HTTPS](https://en.wikipedia.org/wiki/HTTPS) for better security and privacy.

{: .alert.alert-warning role="alert"}
The Lounge only has basic HTTPS support, and will need to be manually restarted to reload certificates on renewal. For advanced HTTPS support, consider [using a reverse proxy](/docs/guides/reverse-proxies).

First, you need an HTTPS certificate. Use certbot for generating these: [certbot]https://certbot.eff.org/instructions
Choose `none of the above` from the first dropdown, then choose your system
Follow the instructions on screen. This should generate a private key, as well as your HTTPS certificate that will expire after 90 days.

Open your configuration file, located at `${THELOUNGE_HOME}/config.js` and look for the `https` key, and set the following values:

- Change `enable` to `true`
- Set `key` to the private key path that was generated, `privkey.pem`
- Set `certificate` to the certificate path, `cert.pem`
- Set `CA` to the chain path, `chain.pem`
You must not use `\` even if on windows, please change `\` to `/` when writing the path
The certs are located in the certbot folder (root)/certbot
