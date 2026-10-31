# Survivor-X website

Official website for Survivor-X and Survivor-X (Free), published by **Stasis State
LLC**. Static HTML/CSS and local images; no build or dependencies.

| Purpose | Production URL / contact |
| --- | --- |
| Game website | https://survivorx.stasisstate.com/ |
| Privacy policy | https://survivorx.stasisstate.com/privacy.html |
| Terms of service | https://survivorx.stasisstate.com/terms.html |
| Data deletion | https://survivorx.stasisstate.com/data-deletion.html |
| Organization | https://stasisstate.com/ |
| App's in-game policy link | https://survivorx.stasisstate.com/privacy.html |
| Support | support@stasisstate.com |
| Privacy requests | privacy@stasisstate.com |

## Hosting

Repository: `Elevate08/survivorx-website`. Configure public visibility and GitHub
Pages from `main`, `/`, with domain `survivorx.stasisstate.com` (also in `CNAME`).
Publish a DNS CNAME for `survivorx` pointing to `elevate08.github.io`, then enforce
HTTPS once GitHub issues its certificate. `.nojekyll` disables Jekyll processing.
The CNAME target has no repository path. Before a custom domain is configured,
the project URL is https://elevate08.github.io/survivorx-website/. Once configured,
GitHub redirects that URL to the custom domain, so DNS must work.

See the organization website's
[launch checklist](https://github.com/Elevate08/stasisstatellc-website/blob/main/LAUNCH.md)
(local `../stasisstatellc-website/LAUNCH.md`) for exact DNS, existing email records,
DKIM/mailbox tests, HTTPS validation, and Google Play handoff. Publishing a site
does not verify mailbox delivery or complete Google identity verification.

## Keeping disclosures accurate

Reviewed October 31, 2026 against the game repo's
`app/data-safety.json`, `docs/play/data-safety.md`, Gradle dependencies, manifests,
backup rules, Play Games initialization, analytics, and distribution settings.

- Survivor-X (Free) `com.stasisstate.survivorx.free`; Survivor-X (paid) `com.stasisstate.survivorx.paid`.
- No live ad SDK or advertising-ID access; free advertising flows are placeholders.
- No Firebase, remote analytics, billing SDK, or publisher game accounts/backend.
- Run analytics stay on-device: off by default in release, on in debug.
- Play Games saves and achievements are implemented but disabled by default until a
  project ID is configured. The policy conditionally describes identity, saved
  progression, lifetime stats, achievement unlocks, and Google's SDK analytics and
  diagnostics.
- Android backups can exist independently of Play Games; local deletion does not
  erase Google-held copies. The paid app imports progress directly on-device.

This site is the single home of every Survivor-X legal page (terms, privacy,
deletion). stasisstate.com only points here. Keep these pages aligned with the
game's Data Safety declaration, and update the declaration and Play Console when SDKs,
permissions, configuration, or data flows change. Recheck the release artifact;
the source declaration anticipates Play Games being enabled. Add a real store link
only after confirming its listing is live.

Preview: `python -m http.server 8081`, then http://localhost:8081/.

## Cinematic homepage

The homepage implements the selected Event Horizon cinematic design: a dark
cyan atmosphere, orbital Vanguard portrait, gameplay loop, hero roster, and
in-game screenshot gallery. `home.css` styles the homepage; `styles.css` remains
the stylesheet for the privacy and data-deletion pages. The design mockups and
their preview assets have been removed.

The four hero portraits in `assets/` are copied from the game's Astral Forge pack:
`portraits/ui_portrait_{vanguard,gunslinger,technomancer}_02.png` and
`frontier/portraits/spr_player_beastbinder_right_01.png`. Keep these aligned with
the game artwork. Images have explicit dimensions; below-fold images load lazily.
The site continues to use no JavaScript dependencies, external fonts, or trackers.

Validation: homepage and both policy pages rendered in isolated Chromium at
320, 375, 768, 1024, and 1440 pixels, with no horizontal overflow, missing images,
or runtime exceptions. Local links and section targets resolve. Availability
buttons still contact the publisher until a verified store listing is supplied.
