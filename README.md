# Geni API — Postman Collection

A Postman (v2.1) collection for the **Geni API** (geni.com, part of MyHeritage), the collaborative "World Family Tree" with strong Jewish genealogy coverage. It includes all 89 endpoints from the official reference, OAuth 2.0 helper requests and worked research examples.

**Import link:** `https://raw.githubusercontent.com/mikeyeves/Geni-API-Postman/main/Geni_API.postman_collection.json` (Postman → Import → Link)

No environment file is needed. All settings are collection variables (collection → Variables tab).

## Getting access
1. Sign in to Geni and register an app at https://www.geni.com/platform/developer/apps.
2. Note the **App Key** (`client_id`) and **App Secret** (`client_secret`). Set a **Site Domain**; your `redirect_uri` must be on that domain.
3. Fill in `client_id`, `client_secret` and `redirect_uri` in the collection Variables.

## Authenticating (folder `00 · Authentication`)
1. **Build login URL**: open the link, sign in, click **Allow**, then copy the `code` from the redirect into `auth_code`.
2. **Exchange code for access token**: saves `access_token` (and `refresh_token`).
3. **Refresh access token**: gets a new token when the old one expires.

Every request sends `?access_token={{access_token}}`. The API does **not** accept browser cookies.

## Folders
| Folder | Requests |
|---|---|
| 00 · Authentication (OAuth 2.0) | 4 |
| ★ Research · Barna / Krupl / Bukovsky | 7 |
| Profile | 24 |
| Union | 4 |
| User | 15 |
| Surname | 3 |
| Project | 8 |
| Document | 10 |
| Photo | 9 |
| Photo album | 4 |
| Video | 9 |
| Revision | 1 |
| Stats | 2 |

Each request description links to its official reference page.

## Tips
- **IDs:** Geni IDs look like `profile-g6000000012345678901`. The collection adds the `profile-` / `union-` / … prefix, so put only the part after it in `profile_id`.
- **Useful reads:** `profile/search?names=…`, `profile-{id}/ancestors?generations=…` (up to 20), `profile-{id}/immediate-family`, `profile-{id}/path-to/profile-{other}`.
- **Search results:** profile search shows a Postman Visualizer table with links to each profile.
- **Writes:** write calls (add, update, delete, merge, tag …) are POST, sent as form data or JSON.
- **Rate limits:** watch the `X-API-Rate-Limit`, `X-API-Rate-Remaining` and `X-API-Rate-Window` headers. The collection logs them to the console.

## Related collections
- [FamilySearch API](https://github.com/mikeyeves/FamilySearch-API-Postman)
- [NYC Historical Vital Records](https://github.com/mikeyeves/NYC-Historical-Vital-Records-Postman)
- [NYC Open Data](https://github.com/mikeyeves/NYC-Open-Data-Postman)
- [Unified Census ED Finder](https://github.com/mikeyeves/Unified-Census-ED-Finder-Postman)
- [Federal Register + National Archives Catalog](https://github.com/mikeyeves/US-Federal-Register-National-Archives-Catalog-APIs)
- [Hebcal](https://github.com/mikeyeves/Hebcal-Jewish-Calendar-APIs)

*Unofficial. Not affiliated with or endorsed by Geni or MyHeritage. Generated from the public API reference.*
