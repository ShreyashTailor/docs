+++
title = "Frequently Asked Questions"
description = "Find answers to frequently asked questions"
authors = ["tr1x_em","randomboi404"]
date = 2025-12-20
+++

#### Q. Which DNS Records are supported?

**Ans :**
We currenly support the following records:

- A
- AAAA
- CNAME
- MX
- TXT
- NS (not available for everyone)
- DS (can only be used alongside NS)
- URL (custom record made by us for redirecting)

#### Q. Why does my domain do not show the changes even though my PR is successfully merged?

**Ans :**
It takes time for DNS propagation. After clearing your browser cache, if your changes did not reflect within 48-72 hours, consider contacting us.

#### Q. How can I become a maintainer / reviewer of the project?

**Ans :**
We don't currently accept any applications.

#### Q. Which services can I use?

**Ans :**
All the services are supported if you configure it properly. You can find examples of important services in (link to 3rd section).

#### Q. Why is my subdomain deleted without my permission?

**Ans :**
Because you broke one of our [rules](https://github.com).

#### Q. Why are there so many restrictions on NS records?

**Ans :**
NS records effectively delegate full DNS control of a subdomain to external nameservers. This can be easily abused for phishing, malware, spam, or other malicious activities, and can also impact the reputation and security of the parent domain.
Because of this, NS records are restricted and only granted on a case-by-case basis to trusted users with a valid reason.
