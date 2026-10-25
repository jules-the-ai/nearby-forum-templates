# nearby.forum templates

A very lean static HTML template for the first nearby.forum screen: the local posts list.

## Implemented rules

- Posts are blurred and controls disabled until location services are enabled or a five-digit ZIP code is provided.
- A location gate opens on first load, with both options.
- After an area is selected, category and keyword filtering work against the list.
- Theme defaults to the device setting; the switch cycles System, Light, and Dark and persists locally.
- Desktop navigation is sticky at the top. Mobile uses a fixed pseudo-native bottom navigation bar.
- No external fonts, images, packages, trackers, or build tool are required.

## Angular extraction map

Each reusable region has a `data-component` hook: `app-header`, `primary-nav`, `mobile-nav`, `area-status`, `area-notice`, `post-list-page`, `post-filters`, `post-card`, and `location-gate`.

During the Angular pass, use the cards as an `@for` or `*ngFor` over a `Post[]`; replace the small demo JS with a ThemeService and a real location/ZIP-to-area service.

## Preview

```sh
python3 -m http.server 8088 --bind 0.0.0.0 --directory /home/syzygy/nearby-forum-templates
```

Open http://localhost:8088.

## License

MIT
