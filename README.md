# Axon (AppLovin) Server API — PowerClick

Server-side Google Tag Manager tag that sends your conversions to AppLovin (Axon), plus [PowerClick](https://powerclick.io) reporting:
after each send it posts AppLovin (Axon)'s response to PowerClick with the click ID and PowerClick's spore ID, so PowerClick
can show delivery health and tie each conversion back to the ad click.

## Based on Stape's template

A modified version of [stape-io/axon-tag](https://github.com/stape-io/axon-tag) by [Stape](https://stape.io), licensed under the
Apache License 2.0, at commit `27ad87e` (2026-09-03). Stape's settings and behaviour are unchanged; see Stape's
documentation for the AppLovin (Axon) setup. Changes:

- A **PowerClick** field group: **PowerClick Tenant ID**, **PowerClick Event Name (optional)**.
- After the AppLovin (Axon) request, one POST of the response to `https://ingest.powerclick.io` for your account.
- Permissions: *Sends HTTP requests* adds `https://ingest.powerclick.io/*`; *Reads cookies* adds `__spore_id`.
- Name and brand: PowerClick. Stape's tests are not included (they assert Stape's exact requests).

## Setup

1. Server container: add the template from the Community Template Gallery.
2. Configure the AppLovin (Axon) fields exactly as with Stape's template.
3. In the **PowerClick** group, enter your **PowerClick Tenant ID**.

Problems with AppLovin (Axon) delivery itself: compare with Stape's template. Problems with PowerClick reporting: open an
issue here.
