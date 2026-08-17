# Card Beast AR — DR-001 READY

The uploaded `targets (1).mind` has been integrated into the scanner.

## Important fix
The scanner embeds the compiled MindAR target in the HTML and intercepts the `./targets.mind` fetch. This avoids the exact error seen earlier:

`Fetch API cannot load content://.../targets.mind`
`URL scheme "content" is not supported`

So the target file no longer needs to be fetched from the Android Files `content://` URL.

## Test
1. Open `index.html`.
2. Allow camera access if the browser permits it.
3. Point the rear camera at the DR-001 card.
4. Expected: `CARD CONFIRMED • DR-001`.

## If camera is still denied
That is a separate Android `content://` camera restriction. In that case the same `index.html` must be served over HTTPS. The target-loading problem itself is already fixed in this package.

## Current scope
- Real MindAR image target
- Real camera image tracking
- DR-001 detection
- No 3D monster yet
- No cloud upload by our code
