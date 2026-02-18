# @owlstronaut/circleci-trust-publish-test

Test package for validating CircleCI OIDC trusted publishing against the **real npm registry**.

## Purpose

Used for bug-bashing the CircleCI trusted publisher UI flows on wubwub. This package is connected to CircleCI and publishes via OIDC token exchange — no long-lived npm tokens.

## Setup

### 1. CircleCI

| Field | Value |
|-------|-------|
| Org ID | `83358abe-db19-405f-8f81-b6cdde80fcb6` |
| Org Slug | `circleci/HCjRLCEAXeekHAXiqAJaCV` |
| Project ID | `020e7c31-adeb-4b15-afb5-3a63541f483c` |
| Project Slug | `circleci/HCjRLCEAXeekHAXiqAJaCV/FjJnKQnYK6UzgQ6YLgFbh` |
| Pipeline Definition ID | `c807691a-0a0f-4020-9a50-10bd88198b14` |

### 2. npm Trusted Publishing

Configure the trusted publisher on [npmjs.com](https://www.npmjs.com/package/@owlstronaut/circleci-trust-publish-test/access) with:

```
org_id: 83358abe-db19-405f-8f81-b6cdde80fcb6
project_id: 020e7c31-adeb-4b15-afb5-3a63541f483c
```

## Workflows

### `publish-workflow`
Publishes to the real npm registry. Only runs on `main`.

### `debug-workflow`
Decodes and prints OIDC token claims — use to get the values needed for trusted publisher configuration.

## Related

- [trust-publish-test](../trust-publish-test) — original test package (sandbox)
- Bug bash tasks: #14717, #14718, #14719, #14720, #14721
