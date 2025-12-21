+++
title = "Discord Setup"
description = "Connect your domain to your Discord profile"
authors = ["randomboi404"]
date = 2025-12-21
insert_anchor_links = "left"
+++

## Discord Domain Verification

- Open Discord and go to `Settings` → `Connections`.
- Click the `Domain` icon (the globe) and enter your domain name.
- Copy the verification string provided by Discord (e.g., `dh=...`).
- Add a TXT record in your subdomain json file:
```json
{
    "type": "TXT",
    "name": "_discord.example",
    "value": "discord-verification-string"
}
```

- Submit the PR and wait for the approval.
- Once merged, go back to Discord and click **Verify**. Your domain will now show on your profile.

## Alternative Method (By a plain file on server)

- Open Discord and go to `Settings` → `Connections`.
- Click the `Domain` icon (the globe) and enter your domain name.
- Click on **Verify using HTTPs** and copy the verification string.
- Create a `.well-known/` folder in your subdomain's root.
- Create a file named `discord` in it and paste the verification string.
- Follow the procedure again and when you're in the **Verify using HTTPS** tab, click **Verify**. Your domain will now show on your profile.
