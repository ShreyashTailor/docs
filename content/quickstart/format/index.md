+++
title = "Request Format"
description = "Learn how to format your subdomain addition request"
authors = ["tr1x_em"]
date = 2025-12-20
+++

Your file must be located in the <mark>domains/</mark> folder and named exactly as your desired subdomain (e.g example.json).

<ul>
    <li>

**Characters**: Only lowercase alphanumeric characters (a-z, 0-9) and hyphens (-) are allowed. (NOTE: hyphens are not allowed at the start or end of the subdomain name)

</li><li>

**Length**: Must be at least 2 characters long.

</li><li>

**Wildcards**: We do NOT support wildcards as it leads to vulnerability issues.

</li><li>

Your filename must be the same as that of your subdomain name.

</li>

</ul>

# JSON Format

The file content must be valid JSON containing an `owner` object and a `records` object.
You may specify your contact info in the `owner` object. However, a key named `username` MUST be compulsory present which will have the value of your github username.

Example:

```json
{
    "user": {
        "username": "randomboi404",
        "email": "admin@is-an-ai.dev",
        "discord": "randomboi404"
    },
    "subdomain": "example",
    "records": [
        {
            "type": "URL",
            "name": "example",
            "value": "https://randomboi404.is-a.dev"
        }
    ]
}
```

# Supported Records

All the DNS records expect 3 compulsory values: `type`, `name` and `value`. Their general syntax is as follows:

(Note that you can combine multiple suitable records in a single subdomain file as long as it doesn't break the constraints)

### CNAME Record

```json
{
    "type": "CNAME",
    "name": "example",
    "value": "randomboi404.github.io",
    "proxied": false
}
```

{% alert(note=true) %}
**proxy**: It refers to the cloudfare proxy. Make sure to turn it on/off as per the need.
{% end %}

### A Record

```json
{
    "type": "A",
    "name": "my-app",
    "value": "192.0.2.1"
}
```

### AAAA Record

```json
{
    "type": "AAAA",
    "name": "ipv6-site",
    "value": "2001:db8:85a3:0000:0000:8a2e:0370:7334"
}
```

### MX Record

```json
{
    "type": "MX",
    "name": "mail",
    "value": ["10 mx1.improvmx.com", "20 mx2.improvmx.com"]
}
```

### TXT Record

```json
{
    "type": "TXT",
    "name": "verify",
    "value": ["google-site-verification=abc123xyz"]
}
```

### URL Record

```json
{
    "type": "URL",
    "name": "socials",
    "value": ["https://x.com/yourhandle"]
}
```

{% alert(tip=true) %}
**Regarding NS and DS Records**: Direct PR regarding an NS record WILL be instantly rejected. If you want to have a nameserver record, you MUST contact us personally via our Discord and specify the need. Even then, there's a high chance that you'll be rejected if your reason is invalid. This is done for security purposes as handling a nameserver is a critical risk for us.

Supported but WIP: CAA, SRV, TLSA
{% end %}

# Examples

{% alert(note=true) %}
You may visit the [domain/](https://github.com) folder of our repo as all accepted files in it are working examples!

{% end %}

Despite that, here are a few generic examples covering certain test cases:

- Example 1:

```json
{
    "user": {
        "username": "tr1xem"
    },
    "subdomain": "trix",
    "records": [
        {
            "type": "CNAME",
            "name": "trix",
            "value": "tr1xem.github.io",
            "proxied": false
        },
        {
            "type": "CNAME",
            "name": "blogs.trix",
            "value": "tr1xem.github.io",
            "proxied": false
        },
        {
            "type": "TXT",
            "name": "_discord.trix",
            "value": "dh=19e8ae4b10637d5025674833b9073d3f4b057367"
        }
    ]
}
```

Output:

<mark>trix.is-an-ai.dev</mark> can serve a github page.

<mark>blogs.trix.is-an-ai.dev</mark> can serve a github page.

<mark>\_discord.trix.is-an-ai.dev</mark> is for domain verification for personal discord account.

- Example 2:

```json
{
    "user": {
        "username": "thenil3sh",
        "email": "contact@example.com"
    },
    "subdomain": "tones",
    "records": [
        {
            "type": "URL",
            "name": "tones",
            "value": "https://tones.example.com"
        }
    ]
}
```

Output:
<mark>tones.is-an-ai.dev</mark> will redirect to `https://tones.example.com`
