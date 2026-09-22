# IRIS Admin Navigator

IRIS Admin Navigator is a small, open-source administration portal for the InterSystems IRIS management APIs. It focuses on server overview, security inspection, operations, system inventory, and a safe read-only API explorer.

The frontend is dependency-free vanilla HTML, CSS, and JavaScript. It authenticates through `/api/admin/login`, stores the short-lived access token only in `sessionStorage`, and sends read requests with the standard `Authorization: Bearer` header. No credentials are bundled in the repository.

## Run with IRIS

The application is designed for IRIS Community Edition / IRIS for Health Community Edition with the management API enabled. Import the `web` directory as a CSP application at `/csp/irismi`, or package the repository with ZPM. Open:

```text
http://localhost:52773/csp/irismi/index.html
```

The API is expected at `/api/admin` on the same IRIS server. Connect with an IRIS user holding the privileges required by each view. The API specification used for the endpoint catalog is maintained by the InterSystems community in [`sysadmin-api-specification`](https://github.com/intersystems-community/sysadmin-api-specification).

## Design goals

- A clear overview of the current product, mode, namespaces, and effective admin scopes.
- Focused read-only shortcuts for security, operations, and system inventory.
- A generic API explorer aligned with the management API paths.
- No external analytics, no embedded secrets, and no paid service dependency.
- Responsive layout suitable for desktop and smaller screens.

## Development

Edit files under `web/` and serve them from an IRIS CSP application. The browser UI can also be opened from a static server for layout work, but API calls require an IRIS host exposing `/api/admin`.
