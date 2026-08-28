# Release notes

## v251.14.0

### New features

- Extension Kit:
  - New [If action](https://docs-external.u4pp.com/extensions-kit/built-in-actions/if-else/) that runs a block of actions only when a condition is met, with an optional **Else** block. This is an early version, available only in non-production environments.
  - The [Monitoring tab](https://docs-external.u4pp.com/extensions-kit/guides/portal/monitoring/) now includes an **App Studio** dashboard.
  - The **HTTP request** action now supports a `Content-Disposition` header in the **Headers** section. For information, see [Content-Disposition header](https://docs-external.u4pp.com/extensions-kit/built-in-actions/http-request#content-disposition-header).

### Improvements

- Extension Kit:
  - Newly created flows are now internally marked to be subject to new future hard limits. For more information about the current limits, see [Service limits](https://docs-external.u4pp.com/extensions-kit/architecture/service-limits/).
  - Improved accessibility across the portal to align with WCAG 2.2, covering keyboard navigation, focus visibility, screen reader announcements, ARIA attributes, labels, and text contrast.
  - Internal technical and security improvements.

- App Studio:
  - Importing an app from another tenant is no longer blocked when a credential is invalid. The API now returns a warning instead of an error.
  - Internal technical and security improvements.

### Fixes

- Extension Kit:
  - A condition cloned in the **Until** action is no longer linked to the original condition.
  - The **Monitoring** tab email is now sent when the Unit4 ID is not an email address.
  - The **Flows API** no longer returns `500 Internal Server Error` when the tenant claim is not present in the request.
  - The SFTP actions in the portal now link to the correct help page.

- App Studio:
  - The **Combobox** and **Dropdown** components now reset their fields.
  - The **Data grid** no longer collapses when it is added to a column.
  - The file exported from the **Data grid** no longer contains an empty column.
  - The **File uploader** component now updates correctly.
  - The **Chart** component no longer grows larger than intended.
  - The app no longer loads indefinitely after triggering a **Marketplace flow** resource in a system app.

---

## v251.10.1

### Hotfixes

- Extension Kit:
  - Fixed an issue where **Webhook** triggers with a remote certificate stopped working. If the issue persists after this update, [export the updated certificate](https://docs-external.u4pp.com/extensions-kit/built-in-triggers/http-webhook-v2#how-to-export-the-certificate) and add it to the service calling the webhook.

## v251.10.0

### New features

- Extension Kit:
  - The [Monitoring tab](https://docs-external.u4pp.com/extensions-kit/guides/portal/monitoring/) is now available for production environments.
  - **Dual** SFTP authentication method is now available for production environments.

- App Studio:
  - New [Chart component](https://docs-external.u4pp.com/extensions-kit/app-studio/components/charts-ripple/). It supports **Bar**, **Line**, **Pie**, **Doughnut**, and **Radar** chart types.
  - New _Background colour_ property in the following layout components: **Root**, **Container**, **Panel**, **Panel with tabs**, **Panel with stepper**, and **Stacked list**. Available options are _White_ (default) and _Gray_.
  - New _Card_ variant for the **Container** component.
  - New _Column span_ options in the **Container** component that enable setting individual column widths.
  - Complex Liquid templating (`{% %}`) is now supported in the _URL_, _Headers_, and _Parameters_ fields across **HTTP**, **ERPx API**, **ERP CR API**, and **U4 service** resources.

  > Note: You need to create a new version of your published app to get the new Ripple version. Open your app and publish it again.

### Improvements

- Extension Kit:
  - The **Webhook** trigger now has a rate limit to protect platform stability under high request volumes.
  - Internal technical and security improvements.

- App Studio:
  - The **Options** menu (three dots) on the App Studio dashboard is now fully operable via keyboard navigation and accessible to screen reader users.

### Fixes

- Extension Kit:
  - The **Until** action can no longer be nested beyond five levels deep.

- App Studio:
  - Data grid styles are now correctly applied in the canvas editor.
  - The **Advanced** tab no longer displays in the **Root** component editor panel for Ripple apps, where it was not applicable.
  - An error no longer occurs when a **Data grid** column with the _Datatype_ set to **Value list** contains a plain array in the _Options_ property.
  - An error no longer occurs when a **Stacked list** component contains multiple Liquid template expressions.
