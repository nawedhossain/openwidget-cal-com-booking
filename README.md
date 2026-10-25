# Cal.com Booking for OpenWidget

Cal.com Booking integrates Cal.com's scheduling experience directly into an OpenWidget app. Visitors can view availability and book appointments in an inline calendar without being redirected to a separate booking page.

## Features

- **Inline scheduling:** Renders a Cal.com booking calendar within the app experience.
- **Configurable booking destination:** Supports personal, team, and event-type booking paths.
- **Theme selection:** Supports light and dark themes.
- **Brand customization:** Supports an optional custom brand color in six-digit hexadecimal format.
- **Calendar layouts:** Supports month and week views.
- **Responsive experience:** Enables Cal.com's slot-oriented view on smaller screens.
- **Lightweight architecture:** Uses a static HTML page and Cal.com's official embed script; no application backend or database is required.

## Configuration

The app exposes the following properties through OpenWidget:

| Property | Description | Supported values |
| --- | --- | --- |
| `calPath` | Cal.com booking path, without the protocol or domain | For example, `username/30min` or `team/event` |
| `theme` | Calendar appearance | `light` or `dark` |
| `brandColor` | Optional custom brand color | Six-digit hexadecimal color, with or without a leading `#`; for example, `6750A4` |
| `layout` | Calendar layout | `month_view` or `week_view` |

If no valid brand color is provided, Cal.com's default branding color is used. Unsupported theme values fall back to dark mode, and unsupported layout values fall back to month view. A valid booking path is required for the calendar to load.

## Implementation

The app is delivered as a static page and initializes Cal.com's official inline embed using the selected configuration. Configuration values are passed as URL query parameters from the OpenWidget app definition to the hosted page.

Project files:

- `app.json` — OpenWidget app metadata, action, and configurable properties.
- `index.html` — inline booking interface and Cal.com embed initialization.
- `logo.svg` — SVG app icon asset.

## Privacy and data handling

This app does not provide its own backend, database, or application-level collection of booking information. Scheduling, availability, and appointment submission are handled by Cal.com through its embedded booking experience. Data submitted during booking is subject to Cal.com's applicable privacy policy and terms.

## Third-party service

The booking calendar loads the official Cal.com embed script from `https://app.cal.com/embed/embed.js` and uses Cal.com to provide scheduling functionality. Availability and successful booking depend on the configured Cal.com booking page and the availability of Cal.com's service.

## License

See the repository's `LICENSE` file for the applicable license terms.
