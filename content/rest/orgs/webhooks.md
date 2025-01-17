---
title: Organization webhooks
allowTitleToDifferFromFilename: true
shortTitle: Webhooks
intro: 'Use the REST API to interact with webhooks in an organization.'
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - API
miniTocMaxHeadingLevel: 3
---

## About organization webhooks

Organization webhooks allow you to receive HTTP `POST` payloads whenever certain events happen in an organization. For more information, see "[About webhooks](/developers/webhooks-and-events/webhooks/about-webhooks)."

### Scopes and restrictions

All actions against organization webhooks require the authenticated user to be an admin of the organization being managed. Additionally, OAuth tokens require the `admin:org_hook` scope. For more information, see "[Scopes for OAuth Apps](/developers/apps/scopes-for-oauth-apps)."

In order to protect sensitive data which may be present in webhook configurations, we also enforce the following access control rules:

- OAuth applications cannot list, view, or edit webhooks which they did not create.
- Users cannot list, view, or edit webhooks which were created by OAuth applications.

### Receiving Webhooks

In order for {% data variables.product.product_name %} to send webhook payloads, your server needs to be accessible from the Internet. We also highly suggest using SSL so that we can send encrypted payloads over HTTPS.

For more best practices, [see our guide](/guides/best-practices-for-integrators/).

#### Webhook headers

{% data variables.product.product_name %} will send along several HTTP headers to differentiate between event types and payload identifiers. See [webhook headers](/webhooks/event-payloads/#delivery-headers) for details.
