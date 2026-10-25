# Cal.com Booking — OpenWidget App

An OpenWidget app that embeds a Cal.com booking calendar inline, so visitors can choose a date and time without being sent to a separate Cal.com page.

## Files

- `app.json` — OpenWidget app metadata and installer properties.
- `index.html` — static booking page; loads Cal.com's inline embed.
- `logo.svg` — the provided Cal.com logo, renamed as requested. Use it as the app icon asset when submitting the app.

No backend, API key, or database is needed. The calendar and booking flow are provided by Cal.com. This project does not include a `LICENSE` file.

## Publish the page with GitHub Pages

1. Create a GitHub repository. If you want to add a license when creating it, OpenWidget's current submission guide specifically asks for Apache License 2.0.
2. Extract this ZIP and upload `app.json`, `index.html`, `logo.svg`, and `README.md` to the **root** of the repository.
3. In GitHub, open **Settings → Pages** and configure deployment from the `main` branch and `/ (root)`.
4. Wait for GitHub Pages to publish the site. Its URL should look like `https://nawedhossain.github.io/openwidget-cal-com-booking/`.
5. Open `app.json` and the `action.value` URL is already set to your GitHub Pages URL. If you fork or rename the repository later, update it and preserve the query string. Example:

   ```json
   "value": "https://nawedhossain.github.io/openwidget-cal-com-booking/?calPath=%calPath%&theme=%theme%&brandColor=%brandColor%&layout=%layout%"
   ```

6. Commit the edit. The `index.html` page is now hosted and can be used as the OpenWidget app's full-screen URL.

## Configure the OpenWidget app

The values in `app.json` become setup fields in OpenWidget:

- **Cal.com booking path (`calPath`):** `yourname/30min` or another path copied from your Cal.com booking link. Enter the path, not the complete URL.
- **Theme (`theme`):** type `light` or `dark`. Any value other than `light` is treated as `dark`.
- **Brand color (`brandColor`):** optional six-character hex color **without** the `#`, such as `6750A4`. Leave blank to use Cal.com's default embed color.
- **Calendar layout (`layout`):** type `month_view` or `week_view`. Other values fall back to `month_view`.

The app validates the booking path and color before using them. It does not collect or store visitor data itself; Cal.com handles the booking form and appointment flow.

## Test before submitting

After enabling Pages, test a URL like this in your browser:

`https://nawedhossain.github.io/openwidget-cal-com-booking/?calPath=YOURNAME/30min&theme=dark&brandColor=6750A4&layout=month_view`

Confirm that the calendar loads, the theme and color look right, the booking flow works on mobile, and the final confirmation step behaves correctly inside OpenWidget's full-screen iframe.

## Submit to OpenWidget

Follow OpenWidget's current instructions at <https://openwidget.com/developers/openwidget-apps>. The docs currently ask app authors to email the app details and repository to `info@openwidget.com`, include an SVG/PNG/JPEG icon under 50 KB, and include an Apache 2.0 license. The provided `logo.svg` is included as the icon asset; no license file is bundled in this ZIP.
