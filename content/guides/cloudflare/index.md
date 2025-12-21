+++
title = "Cloudflare Setup"
description = "Learn how to setup up your domain on Cloudflare Services"
authors = ["randomboi404"]
date = 2025-12-20
insert_anchor_links = "left"
+++

# Cloudfare Services

## Using Cloudfare Pages

- Create your cloudfare pages using the [docs](https://developers.cloudflare.com/pages) and deploy it normally.
- In your Pages project settings, copy the default pages domain. (e.g. `your-project-pages.dev`)
- Add a CNAME record in your subdomain json file:

```json
{
    "type": "CNAME",
    "name": "example",
    "value": "your-project.pages.dev",
    "proxied": true
}
```

- Submit the PR and wait for the approval.
- Once merged, go back to Cloudflare Pages → Custom Domains and add:
  `example.is-an-ai.dev`

{% alert(note=true) %}

- The record must be proxied.
  {% end %}

## Using Cloudfare Workers

- Create and configure your cloudfare worker using the [docs](https://developers.cloudflare.com/workers).
- Deploy the worker so it is accessible at:
  `your-worker.your-account.workers.dev`
- Add a CNAME record in your subdomain json file pointing to the domain of worker:

```json
{
    "type": "CNAME",
    "name": "example",
    "value": "your-worker.your-account.workers.dev",
    "proxied": true
}
```

- Submit the PR and wait for the approval.
- Once merged, go back to Cloudflare Dashboard → Workers → Custom Domains and add:
  `example.is-an-ai.dev`

{% alert(note=true) %}

- The record must be proxied.
  {% end %}

{% alert(warning=true) %}

- Workers must serve legitimate content.
- Abuse, scraping, phishing, or tunneling will lead to removal.
  {% end %}

## Using Cloudflare Tunnel (cloudflared)

- Create a tunnel using `cloudflared`. (Visit [docs](https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel) for more info)
- Cloudflare will generate a tunnel domain like:
  `<uuid>.cfargotunnel.com`
- Add a CNAME record in your subdomain json file:

```json
{
    "type": "CNAME",
    "name": "panel",
    "value": "<uuid>.cfargotunnel.com",
    "proxied": true
}
```

{% alert(note=true) %}

- The record must be proxied.
  {% end %}

{% alert(warning=true) %}

- No private dashboards are allowed.
- No admin panels are allowed.
- No internal services are allowed.
- Service must be publicly accessible.
  {% end %}

# Restricted Services

The below cloudfare services are STRICTLY forbidden to use:

- Cloudflare Registrar
- Custom Nameservers (NS) without approval
- Cloudflare Spectrum
- Cloudflare Load Balancers
- Cloudflare SaaS delegation
- Email routing via NS delegation
