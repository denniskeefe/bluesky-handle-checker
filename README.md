# Bluesky Username Enumerator

A single-file, client-side tool that checks a list of usernames against Bluesky and reports which handles exist.

- Queries the public Bluesky AppView API (`app.bsky.actor.getProfile`) directly from the browser; no backend, no data leaves your machine except the lookups.
- Accepts bare names (default suffix `bsky.social`), full handles and custom domains, `@handles`, and `bsky.app/profile/` URLs.
- Accepts email addresses: the part before the `@` is searched, `+tags` are dropped, and dotted names are tried both joined (`johndoe`) and hyphenated (`john-doe`).
- Validates handle syntax per the AT Protocol before sending requests.
- Adjustable concurrency and delay, automatic backoff on rate limits and server errors, and a re-check button for errors or a stopped run.
- Flags accounts the API reports as suspended or deactivated separately from handles that do not exist.
- Results table with display name, bio, DID, follower/post counts and creation date; filter by status.
- Export to CSV (formula-injection safe, Excel-friendly UTF-8) or a PDF report of the current filter.

## Use

Open `index.html` in a browser, paste usernames, and run. No build step.

## Notes

Results reflect the public AppView only; some taken-down or logged-out-hidden accounts may still report as not found. A found handle shows that the name exists, not who owns it. The PDF export uses built-in fonts, so non-Latin characters in display names print as `?`; the CSV keeps them. Use only for lawful, authorized research.
