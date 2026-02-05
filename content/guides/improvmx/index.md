+++
title = "ImprovMX Setup"
description = "Learn how to setup up email forwarding on your domain"
authors = ["randomboi404"]
date = 2025-12-21
insert_anchor_links = "left"
+++

## ImprovMX Email Forwarding

- Add the below records in your subdomain json file:
```json
{
    "type": "MX",
    "name": "example",
    "target": "mx1.improvmx.com",
    "priority": 10
},
{
    "type": "MX",
    "name": "example",
    "target": "mx2.improvmx.com",
    "priority": 20
},
{
    "type": "TXT",
    "name": "example",
    "target": "v=spf1 include:spf.improvmx.com ~all"
}
```

- Submit the PR and wait for the approval.
- If you haven't already, go to [ImprovMX Dashboard](https://app.improvmx.com) and add your domain there.
