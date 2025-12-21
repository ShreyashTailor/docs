+++
title = "Github Setup"
description = "Learn how to setup up your domain on Github Pages"
authors = ["tr1x_em"]
date = 2025-12-20
[extra]
banner = "banner.jpg"
+++

## Github Pages Setup

- Create a github repository and enable github pages via Settings tab using the [docs](https://docs.github.com/en/pages)
- Ensure your site is building correctly at the default URL. (e.g. `username.github.io/repo`)
- Add a CNAME record in your subdomain json file:
```json
{
    "type": "CNAME",
    "name": "example",
    "value": "username.github.io",
    "proxied": false
}
```
- Submit the PR and wait for the approval.
- Once merged, go to your GitHub Repo Settings → Pages → Custom Domain and enter: `example.is-an-ai.dev`

{% alert(note=true) %}
The record must be proxied.{% end %}

- Tick the Enforce HTTPS checkbox below the custom domain input.

{% alert(note=true) %}
You may need to wait some time (usually around 15-30 mins) for DNS propagation else it'll show an error.{% end %}

## Verifying your subdomain with Github Pages

- Follow the instructions in the [docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages) to get verification string and hostname.
- Add a TXT record in your subdomain json file:
```json
{
    "type": "TXT",
    "name": "hostname.example",
    "value": "github-verification-string"
}
```
- Submit the PR and wait for the approval.
- Once merged, repeat the steps to get the verification string and click on "Verify".

{% alert(note=true) %}
You may need to wait some time (upto 72 hours in some cases) for DNS propagation else it'll show an error.{% end %}
