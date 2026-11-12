# VK Client iOS 13 — GitHub Pages host

This is the **user site repo** for `https://giga-mox.github.io/`.

After enabling Pages from `main` branch root, a VK ID callback landing page is expected at `https://giga-mox.github.io/vk_id_redirect/` (trailing slash). **It is not yet a verified Universal Link.** Do not register this as an active callback until signing and Apple association are fully configured and validated.

The **apple-app-site-association** file has NOT been deployed because the actual signing Team ID is unknown. A fake placeholder would fail verification. To configure, create `.well-known/apple-app-site-association` with an appID of `ACTUAL_TEAM_ID.com.gigamox.vkclient13`, paths `/vk_id_redirect` and `/vk_id_redirect/*`. The app must be signed with matching associated-domains entitlement (`applinks:giga-mox.github.io`). GitHub Pages may serve the extensionless AASA with an unsuitable Content-Type; verify actual headers and Apple validation before relying on it.

The callback HTML deliberately does not read or transmit codes. The script clears a code from the address bar after the page loads, but **this does not prevent URL logging by browsers or intermediaries**.
