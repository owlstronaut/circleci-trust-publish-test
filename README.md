# @owlstronaut/circleci-trust-publish-test

Test package for validating CircleCI OIDC trusted publishing against the **real npm registry**.

## Purpose

Used for bug-bashing the CircleCI trusted publisher UI flows on wubwub. This package is connected to CircleCI and publishes via OIDC token exchange — no long-lived npm tokens.

## Setup

### 1. CircleCI

- Create a project on CircleCI connected to the `owlstronaut/circleci-trust-publish-test` GitHub repo
- Enable OIDC in project settings
- Run the `debug-workflow` first to get claim values (org-id, project-id)

### 2. npm Trusted Publishing

Configure the trusted publisher on [npmjs.com](https://www.npmjs.com/package/@owlstronaut/circleci-trust-publish-test/access) with the org-id and project-id from the debug workflow.

## Workflows

### `publish-workflow`
Publishes to the real npm registry. Only runs on `main`.

### `debug-workflow`
Decodes and prints OIDC token claims — use to get the values needed for trusted publisher configuration.

## Related

- [trust-publish-test](../trust-publish-test) — original test package (sandbox)
- Bug bash tasks: #14717, #14718, #14719, #14720, #14721
