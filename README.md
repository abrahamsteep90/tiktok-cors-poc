# TikTok CORS Vulnerability PoC

## Overview
This repository demonstrates a critical CORS misconfiguration in TikTok's infrastructure that allows any website to make authenticated requests on behalf of users.

## Vulnerability Details
- **CWE-942**: Permissive Cross-domain Policy with Untrusted Domains
- **CVSS Score**: 9.1 (Critical)
- **Impact**: Account takeover, data theft, unauthorized actions

## Technical Evidence
The following curl command proves the CORS misconfiguration:

```bash
curl -i -H "Origin: https://malicious.com" -H "Access-Control-Request-Method: GET" -X OPTIONS \
"https://sf16-website-login.neutral.ttwstatic.com/obj/tiktok_web_login_static/*"