# Bluesky Username Enumerator

A single-file, client-side tool that checks a list of usernames against Bluesky and reports which handles exist.

- Queries the public Bluesky AppView API (`app.bsky.actor.getProfile`) directly from the browser; no backend, no data leaves your machine except the lookups.
- Accepts bare names (default suffix `bsky.social`), full handles and custom domains, `@handles`, and `bsky.app/profile/` URLs.
- Validates handle syntax per the AT Protocol before sending requests.
- Adjustable concurrency and delay, automatic backoff on rate limits.
- Results table with display name, DID, follower/post counts and creation date; filter by status and export to CSV.

## Use

Open `index.html` in a browser, paste usernames, and run. No build step.

## Notes

Results reflect the public AppView only; taken-down or logged-out-hidden accounts may report as not found. Use only for lawful, authorized research.
